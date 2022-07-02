---
title: "jupeter/clean-code-php - список принципов хорошего кода php"
categories: 
  - "php"
---

Плохо

```
function showDeveloperList($developers) {
    foreach($developers as $developer) {
        $expectedSalary = $developer->calculateExpectedSalary();
        $experience = $developer->getExperience();
        $githubLink = $developer->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];
        
        render($data);
    }
}

function showManagerList($managers) {
    foreach($managers as $manager) {
        $expectedSalary = $manager->calculateExpectedSalary();
        $experience = $manager->getExperience();
        $githubLink = $manager->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];
        
        render($data);
    }
}
```

  
Хорошо

```
function showList($employees) {
    foreach($employees as $employe) {
        $expectedSalary = $employe->calculateExpectedSalary();
        $experience = $employe->getExperience();
        $githubLink = $employe->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];
        
        render($data);
    }
}
```

  
[https://github.com/jupeter/clean-code-php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2p1cGV0ZXIvY2xlYW4tY29kZS1waHA%3D)
