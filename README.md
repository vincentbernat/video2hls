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

## Examples

Convert using default parameters (MPEG2-TS with many resolutions):

    ./video2hls TearsOfSteel.mp4

Add an overlay to distinguish the different resolutions:

    ./video2hls --mp4-overlay '{resolution}p, progressive' --video-overlay '{resolution}p, HLS' \
       TearsOfSteel.mp4

Use fragmented MP4:

    ./video2hls --hls-type fmp4 TearsOfSteel.mp4

Specify more bitrates:

    ./video2hls --video-bitrates 8000 4000 2000 1000 \
                --video-widths 1920 1920 1280 854 \
                --video-names '1080p high' '1080p low'
       TearsOfSteel.mp4
