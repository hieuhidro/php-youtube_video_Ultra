# php-youtube_getvideo
 *  ==========================================================================
##PHP class to get the file location of Youtube videos, mp3 audio download the video
 *  ==========================================================================
 *  Introduction

##This PHP class takes a YouTube URL (or YouTube Video-ID) and downloads the video, mp3 audio download the video to your computer.

##UI Demo

For an example integration, try the demo:

##Download

The latest stable version can be downloaded from the downloads tab, or using the following link:

##Basic Usage

##Usage is pretty straight forward:
```php
<?php
    function sendRequest($data, $url) {
        $data = http_build_query($data);
        $context_options = array('http' => array('method' => 'POST', 'header' => "Content-type: application/x-www-form-urlencoded\r\n" . "Content-Length: " . strlen($data) . "\r\n", 'content' => $data));
    
        $context = stream_context_create($context_options);
        $result = file_get_contents($url, false, $context, -1, 40000);
        return $result;
    }
    
    $data = array(
        'keyConnect'=>"sg4yucpdinusy4pw14c1byxszn5zpuhorusglass@rng.vn",
        'url' => 'http://www.youtube.com/watch?v=aahOEZKTCzU'
    );
    $request = json_decode(sendRequest($data,"http://youtubeservice.herokuapp.com/")); 
    $title = $request->title;
    $thumbnail = $request->thumbnail;
    $files = $request->data;   
?>
```

Thank's: for get ID Video from URL `https://github.com/eyecatchup/php-yt_downloader` to use this options

`$ytNew->process("http://www.youtube.com/watch?v=aahOEZKTCzU");` is identical to new

`$ytNew->process("https://www.youtube.com/watch?feature=related&v=aahOEZKTCzU");` is identical to new

`$ytNew->process("aahOEZKTCzU");`
