# php-youtube_getvideo
 *  ==========================================================================
 *  
 * ##PHP class to get the file location of Youtube videos, mp3 audio download the video
 * Get file mp3
 * Get file 3gp
 * Get file flv 
 * Get file mp4 (720p, Ultra HD, 2K, 4K Video)
 *  ==========================================================================
 *  Introduction

##This PHP class takes a YouTube URL (or YouTube Video-ID) and downloads the video, mp3 audio download the video to your computer.

##UI Demo

For an example integration, try the demo: `https://youtubeservice.herokuapp.com/view.php#`
Or Master Example with download Ultra HD with include Audio. :`http://360.horusvr.com`

##Download

The latest stable version can be downloaded from the downloads tab, or using the following link:

##Basic Usage

##Usage is pretty straight forward:
<h3>Anazyne Youtube Video and audio </h3>
```php
<?php
    require('class.youtube.php');
    $hydro->process($_POST['url'])){
    echo $hydro->toJson(); 
?>
```
<h3>Anazyne Youtube Mage Video and audio to one file</h3>
```php

/**
 * (c) Copyright 2015 Hoang Hieu. All Rights Reserved.
 */
require('anazyne.php');
header('Access-Control-Allow-Methods: POST');
header('Content-Type: application/json; charset=UTF-8');
// Downloading HD Videos may take some time.
ini_set('max_execution_time', 0);
// Writing HD Videos to your disk, may need some extra resources.
ini_set('memory_limit', '64M');
$Gbyt = new GbYoutube();
if (getRequest('yturl') && getRequest('mp3url') && getRequest('videoId') && getRequest('itag') && getRequest('title') && getRequest('token')) {
    $token = md5(base64_encode(md5(getRequest('yturl') . getRequest('title') . getRequest('itag') . getRequest('videoId'))));
    if (getRequest('token') == $token) {
        $mertTitle = 'Out_youtubeid_' . getRequest('videoId') . '_' . getRequest('itag');
        if (!file_exists('outvideos/' . $OutTitle . '.mp4')) {
            $mp3Title = $Gbyt -> audioToServer(getRequest('mp3url'), getRequest('videoId'));
            $videoTitle = $Gbyt -> videoToServer(getRequest('videoId'), getRequest('yturl'), getRequest('itag'));
            if ($mp3Title && $videoTitle) {
                try {
                    $mertTitle = $Gbyt -> mergingAudio($videoTitle, $mp3Title);
                    echo json_encode(array('url' => $mertTitle, 'msg' => 'successful'));
                } catch(exception $err) {
                    json_encode(array('msg' => $err -> getMessage(), 'status' => 'error'));
                }
            } else {
                echo json_encode(array('msg' => "Download file failed", 'status' => 'error'));
            }
        } else {
            echo json_encode(array('url' => $mertTitle, 'msg' => 'successful'));
        }
    } else {
        echo json_encode(array('msg' => "Invalidate token", 'status' => 'error'));
    }
} else {
    echo json_encode(array('msg' => "Invalidate request", 'status' => 'error'));
}

<?php 
    
?>
```

Thank's: for get ID Video from URL `https://github.com/eyecatchup/php-yt_downloader` to use this options

`$ytNew->process("http://www.youtube.com/watch?v=aahOEZKTCzU");` is identical to new

`$ytNew->process("https://www.youtube.com/watch?feature=related&v=aahOEZKTCzU");` is identical to new

`$ytNew->process("aahOEZKTCzU");`
