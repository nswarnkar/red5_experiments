Simple Live Streaming Example( RTMP)
-----------------------------
A. Setting up Red5 Server
1. Download red5 server from the home site:
$wget https://github.com/Red5/red5-server/releases/download/v1.0.10-M4/red5-server-1.0.10-M4.tar.gz
$ tar -xvzf red5-server-1.0.10-M4.tar.gz
2. Changed to extracted directory
$ cd red5-server

3. Run red5 server
$ nohup sh red5.sh &

B. Setting up Publisher
Install ffmpeg
$ sudo apt-get install ffmpeg
Publish the camera stream
$ ffmpeg -f video4linux2 -i /dev/video0 -s 320x480 -f flv -f flv rtmp://localhost/oflaDemo/stream_nsw_2

C. Setting up Viewer
$ ffplay 'rtmp://localhost/oflaDemo/stream_nsw_2 live=1'

Please note that video4linux should be installed on your system.
