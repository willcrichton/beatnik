# beatnik
* * *
### Purpose ###
Beatnik is a Javascript framework to aid in the analyzation/processing of music. It uses the new [Web Audio API](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html) to abstract most of the difficult stuff and makes it easy to do what you want. Perfect for that music visualizer you've always wanted to make (which, by the way, if you're interested in, I've got this great framework for easy WebGL rendering called [Glen](http://www.github.com/willcrichton/glen/), also on Github).

### Features ###
* XMLHttpRequest loading of music and impulse responses
* Play/stop functionality
* Access to FFT Table
* Beat detection (needs improvement)
* Song information: current position, total duration
* Volume control
* Speed control
* [Impulse responses](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html#Convolution-section): applying sound effects (e.g. talking in a concert hall or underwater)
* [3D Spatialization](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html#Spatialization-section): positioning sound in 3D space relative to listener (e.g. hearing it from top or left)

### Issues ###
**My page freezes every time it loads a song and/or I can't show a loading image while the song is loading.**  
As far as I know, when the XMLHttpRequest is fetching the song resource, the page waits until the request is complete before allowing the user to do anything else. The best solution is to have a static "loading" image or text displayed before the request is sent.

**I get the error "XMLHttpRequest cannot load [local file name]. Cross origin requests are only supported for HTTP." and "Uncaught Error: NETWORK_ERR: XMLHttpRequest Exception 101".**  
This is an issue with Chrome where accessing songs through the Webkit Audio API is apparently not allowed. Unfortunately, this means you can't test it just by using regular file:// URLs. However, it will work if you host the file(s) on a server, either an actual server or something like [WAMP](http://www.wampserver.com/).

### Credits ###
Thank you to Charles Cliffe with CubicFX for the beat detection algorithm.