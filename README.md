# twitchchess

An implementation of neural network chess written while livestreaming.

<img width=600px src="https://raw.githubusercontent.com/geohot/twitchchess/master/screenshot.png" />

Stream
-----

https://www.twitch.tv/tomcr00s3

Usage
-----

```
 pip3 install python-chess torch torchvision flask
 # then...
 ./play.py   # runs webserver on localhost:5000
```

TODOs
-----

* Roll out search beyond 1-ply
* Make trainer multi GPU
* Train on more data
* Add RL self play learning support

Implementation
-----

twitchchess is a simple 1 look ahead neural network value function. The trained net is in nets/value.pth. It takes in a serialized board and outputs a range from -1 to 1. -1 means black is win, 1 means white is win.

Serialization
-----

We serialize the board into a 8x8x5 bitvector. See state.py for how.

Training Set
-----

The value function was trained on 5M board positions from http://www.kingbase-chess.net/

