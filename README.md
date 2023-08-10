# EXIF_GPS_Gallery3
This page will tell you how to fix EXIF_GPS model and let it work in 2023
Model link: http://galleryproject.org/node/94762

## 1. open dir
`/modules/exif_gps/views`

## 2. edit file
open `exif_gps_static_sidebar.html.php`
and copy and place
```
<?php defined("SYSPATH") or die("No direct script access.") ?>
<?
  $map_api_key = "";
  if (module::get_var("exif_gps", "googlemap_api_key", "") != "") {
    $map_api_key = "&key=" . module::get_var("exif_gps", "googlemap_api_key");
  }
?>
<iframe width="205" height="214"  scrolling="no" src="https://maps.google.com/maps?q=<?=$latitude; ?>,<?=$longitude; ?>&hl=zh_tw&z=<?= module::get_var("exif_gps", "sidebar_zoom"); ?>&amp;output=embed" loading="lazy">
 </iframe>

```
