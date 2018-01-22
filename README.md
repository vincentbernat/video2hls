# video2hls

A simple tool to convert a video to a set of files to play it using
HLS. HLS is an adaptive bitrate streaming protocol: the video is
sliced in small chunks and made available at a variety of different
bit rates. Depending on current network conditions, the player
automatically selects the appropriate bitrate to download the next
segment.

The script needs Python 3.6 and you can run it with `--help` to get
more information about it.

Some browsers may not support natively HLS. In this case, one can use
[hls.js][] to get appropriate support. Many video players also support
this format.

[hls.js]: https://github.com/video-dev/hls.js/
