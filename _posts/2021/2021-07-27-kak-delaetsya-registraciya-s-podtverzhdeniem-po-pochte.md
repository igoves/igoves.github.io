---
title: "Как делается регистрация с подтверждением по почте"
date: ""
categories: 
  - "php"
tags: 
  - "email"
  - "verification"
---

Создаем БД  

```
CREATE TABLE IF NOT EXISTS `users` ( `uid` int(11) NOT NULL AUTO_INCREMENT, `email` varchar(300) NOT NULL UNIQUE, `password` varchar(300) NOT NULL, `activation` varchar(300) NOT NULL UNIQUE, `status` enum('0','1') NOT NULL DEFAULT '0',PRIMARY KEY (`uid`) )
```

  
Форма для регистрации будет вот такой  

```
<form action="" method="post"><label>Email</label><input type="text" name="email" class="input" autocomplete="off"/><label>Пароль </label><input type="password" name="password" class="input" autocomplete="off"/><br/><input type="submit" class="button" value="Регистрация" /><span class='msg'><?php echo $msg; ?></span></form> 
```

  
Создаем php файл подключения к бд db.php  

```
<?phpdefine('DB_SERVER', 'localhost');define('DB_USERNAME', 'username');define('DB_PASSWORD', 'password');define('DB_DATABASE', 'database'); $connection = @mysqli_connect(DB_SERVER,DB_USERNAME,DB_PASSWORD,DB_DATABASE); $base_url='http://www.youwebsite.com/email_activation/';?>
```

  
Создаем главную страницу index.php  

```
<?phpinclude 'db.php';$msg = '';if (!empty($_POST['email']) && isset($_POST['email']) && !empty($_POST['password']) && isset($_POST['password'])) {    $email    = mysql_real_escape_string($_POST['email']);    $password = mysql_real_escape_string($_POST['password']);    $regex    = '/^[_a-z0-9-]+(\\.[_a-z0-9-]+)*@[a-z0-9-]+(\\.[a-z0-9-]+)*(\\.[a-z]{2,4})$/';        if (preg_match($regex, $email)) {        $password   = md5($password);         $activation = md5($email . time());        $count      = mysqli_query($connection, "SELECT uid FROM users WHERE email='$email'");        if (mysqli_num_rows($count) < 1) {            mysqli_query($connection, "INSERT INTO users(email,password,activation) VALUES('$email','$password','$activation')");            include 'smtp/Send_Mail.php';            $to      = $email;            $subject = "Email verification";            $body    = 'Прет, <br/> <br/>подтверди почту. <br/> <br/> <a href="' . $base_url . 'activation/' . $activation . '">' . $base_url . 'activation/' . $activation . '</a>';                        Send_Mail($to, $subject, $body);            $msg = "Регистрация прошла успешно";        } else {            $msg = 'Такой ящик уже есть';        }            } else {        $msg = 'Введите верно почтовый адрес';    }    }?><form action="" method="post"><label>Email</label><input type="text" name="email" class="input" autocomplete="off"/><label>Password </label><input type="password" name="password" class="input" autocomplete="off"/><br/><input type="submit" class="button" value="Registration" /><span class='msg'><?php echo $msg; ?></span></form>
```

  
Сам файл Send\_Mail.php который используеться в index.php  

```
function Send_Mail($to,$subject,$body) {require 'class.phpmailer.php'; $from       = "from@yourwebsite.com"; $mail       = new PHPMailer(); $mail->IsSMTP(true);            // use SMTP $mail->IsHTML(true); $mail->SMTPAuth   = true;                  // enable SMTP authentication $mail->Host       = "tls://smtp.yourwebsite.com"; // SMTP host $mail->Port       =  465;                    // set the SMTP port $mail->Username   = "SMTP_Username";  // SMTP  username $mail->Password   = "SMTP_Password";  // SMTP password $mail->SetFrom($from, 'From Name'); $mail->AddReplyTo($from,'From Name'); $mail->Subject    = $subject; $mail->MsgHTML($body); $address = $to; $mail->AddAddress($address, $to); $mail->Send();  }
```

  
activation.php файл в который перейдет пользователь из письма (если код активации проходит то в бд для пользователя меняеться статус с 0 на 1)  

```
<?phpinclude 'db.php';$msg = '';if (!empty($_GET['code']) && isset($_GET['code'])) {    $code = mysql_real_escape_string($_GET['code']);    $c    = mysqli_query($connection, "SELECT uid FROM users WHERE activation='$code'");        if (mysqli_num_rows($c) > 0) {        $count = mysqli_query($connection, "SELECT uid FROM users WHERE activation='$code' and status='0'");                if (mysqli_num_rows($count) == 1) {            mysqli_query($connection, "UPDATE users SET status='1' WHERE activation='$code'");            $msg = "Вы активированы";        } else {            $msg = "Ваш аккаунт уже активирован";        }            } else {        $msg = "Не верный код активации";    }    }echo $msg;?>
```

  
И на последок создаем файлик .htaccess с правилами  

```
RewriteEngine OnRewriteRule ^activation/([a-zA-Z0-9_-]+)$ activation.php?code=$1RewriteRule ^activation/([a-zA-Z0-9_-]+)/$ activation.php?code=$1
```

  
Это значит что ссылки активации будет выглядить не:  
http://website.com/activation.php?code=ACTIVATION\_CODE  
А вот так:  
http://website.com/activation/ACTIVATION\_CODE  
  
Успехов!)
