---
title: "Смена графики в зависимости от времени года"
categories: 
  - "php"
---

```
<?phpfunction current_season() {       $icons = array(               "spring" => "images/spring.png",               "summer" => "images/summer.png",               "autumn" => "images/autumn.png",               "winter" => "images/winter.png"       );       $day = date("z");       $spring_starts = date("z", strtotime("March 21"));       $spring_ends   = date("z", strtotime("June 20"));       $summer_starts = date("z", strtotime("June 21"));       $summer_ends   = date("z", strtotime("September 22"));       $autumn_starts = date("z", strtotime("September 23"));       $autumn_ends   = date("z", strtotime("December 20"));       if( $day >= $spring_starts && $day <= $spring_ends ) :               $season = "spring";       elseif( $day >= $summer_starts && $day <= $summer_ends ) :               $season = "summer";       elseif( $day >= $autumn_starts && $day <= $autumn_ends ) :               $season = "autumn";       else :               $season = "winter";       endif;       $image_path = $icons[$season];       echo $image_path;}?>
```

  
![\"\"](\"\")
