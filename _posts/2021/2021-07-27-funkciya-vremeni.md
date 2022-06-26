---
title: "Функция времени"
categories: 
  - "php"
---

Как в вконтакте или твиттере  

![Функция времени](images/1294343393_untitled-3.jpg "Функция времени")

  
А делается это примерно, так:  

```
<?phpfunction time_stamp($session_time) {     $time_difference = time() - $session_time;     $seconds = $time_difference;     $minutes = round($time_difference / 60 );    $hours = round($time_difference / 3600 );     $days = round($time_difference / 86400 );     $weeks = round($time_difference / 604800 );     $months = round($time_difference / 2419200 );     $years = round($time_difference / 29030400 );         // Секунды        if($seconds <= 60) { echo "$seconds секунд назад";  }        // Минуты        else if($minutes <=60) {            if($minutes==1)  {   echo "одну минуту назад";    }           else   {    echo "$minutes минут назад";    }        }        // Часы        else if($hours <=24)        {           if($hours==1)          {   echo "один час назад";  }          else          {   echo "$hours часов назад";  }        }        // Дни        else if($days <= 7)        {          if($days==1)          {   echo "один день назад";  }          else          {   echo "$days дней назад";   }        }        // Недели        else if($weeks <= 4)        {           if($weeks==1)          {   echo "одну неделю назад";   }          else          {   echo "$weeks недель назад";  }        }        // Месяцы        else if($months <=12)        {           if($months==1)          {   echo "один месяц назад";   }          else          {   echo "$months месяцев назад";   }        }        // Года        else        {          if($years==1)           {    echo "один год назад";   }           else          {    echo "$years года\\лет назад";   }        }} $session_time ="1264326122";//$session_time=time();echo time_stamp($session_time);?>
```
