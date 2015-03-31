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
    require('class.func.php');
    try {
        // Instantly download a YouTube video (using the default settings).
        $ytNew = new YoutubeAvailible()
        $ytNew->process('http://www.youtube.com/watch?v=aahOEZKTCzU');
    }
    catch (Exception $e) {
        die($e->getMessage());
    }
?>
```

Thank's: for get ID Video from URL `https://github.com/eyecatchup/php-yt_downloader` to use this options
`$ytNew->process("http://www.youtube.com/watch?v=aahOEZKTCzU");` is identical to new

`$ytNew->process("https://www.youtube.com/watch?feature=related&v=aahOEZKTCzU");` is identical to new

`$ytNew->process("aahOEZKTCzU");`
