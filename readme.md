- [Readme](#sec-1)
  - [System Overview](#sec-1-1)
- [Broadcast Controller](#sec-2)
  - [Host](#sec-2-1)
    - [States](#sec-2-1-1)
  - [Server](#sec-2-2)
    - [Online/Offline](#sec-2-2-1)
    - [Preroll](#sec-2-2-2)
    - [Host's Voice](#sec-2-2-3)
    - [Play song](#sec-2-2-4)
    - [Change song](#sec-2-2-5)
  - [Listener](#sec-2-3)
    - [Online/Offline](#sec-2-3-1)
    - [Stream](#sec-2-3-2)
- [Host Interface](#sec-3)
  - [Show Controls](#sec-3-1)
  - [Visual Feedback View](#sec-3-2)
  - [Song Gallery](#sec-3-3)
  - [Playlist](#sec-3-4)
  - [Text Chat View](#sec-3-5)
- [Server API](#sec-4)


# Readme<a id="sec-1" name="sec-1"></a>

An easy way to create your own radio show.

## System Overview<a id="sec-1-1" name="sec-1-1"></a>

![img](overview.png)

# Broadcast Controller<a id="sec-2" name="sec-2"></a>

This is a brief description of what kind of functionallity the broadcast controller contains. There are 3 main components: Host, Server, Listener. These share some functionallity with each other, mostly between the Host and Server. The controller will also be time sensitive due to streaming audio.

For now, functionallity is described in point form. There's no flow control map yet, state changes are only described at the moment.

The Host is the radio host or DJ if you will.

The Server is where all the data is pieced together to create the radio show.

The Listener is the viewer that will hear the completed stream.

## Host<a id="sec-2-1" name="sec-2-1"></a>

### States<a id="sec-2-1-1" name="sec-2-1-1"></a>

1.  Online/Offline

    -   Changes Live state for the broadcast

2.  Preroll

    -   if preroll is set
        -   Rolls when broadcast goes online
    -   trigger when finished
        -   host's voice
        -   song playlist

3.  Host's Voice

    -   enable microphone
    -   microphone capture data transfer to server

4.  Play song

    -   disable microphone
    -   no audio data transfer on host's machine

5.  Change song

    -   automated/manual signal

## Server<a id="sec-2-2" name="sec-2-2"></a>

### Online/Offline<a id="sec-2-2-1" name="sec-2-2-1"></a>

-   recieve signal from host to start broadcast
-   start output buffer to Listeners

### Preroll<a id="sec-2-2-2" name="sec-2-2-2"></a>

-   if preshow is set
    -   load preroll
    -   start dataflow
-   signal host's machine on/close to finish of preroll

### Host's Voice<a id="sec-2-2-3" name="sec-2-2-3"></a>

-   dataflow from host's machine

### Play song<a id="sec-2-2-4" name="sec-2-2-4"></a>

-   stop dataflow from host's machine
-   load song
-   output song to output buffer Listeners

### Change song<a id="sec-2-2-5" name="sec-2-2-5"></a>

-   recieve signal from host's machine
-   gather info for the next song
-   start play song state change

## Listener<a id="sec-2-3" name="sec-2-3"></a>

### Online/Offline<a id="sec-2-3-1" name="sec-2-3-1"></a>

-   load listener page

### Stream<a id="sec-2-3-2" name="sec-2-3-2"></a>

# Host Interface<a id="sec-3" name="sec-3"></a>

This is where the DJ creates every part of their radio show.

## Show Controls<a id="sec-3-1" name="sec-3-1"></a>

## Visual Feedback View<a id="sec-3-2" name="sec-3-2"></a>

## Song Gallery<a id="sec-3-3" name="sec-3-3"></a>

## Playlist<a id="sec-3-4" name="sec-3-4"></a>

## Text Chat View<a id="sec-3-5" name="sec-3-5"></a>

# Server API<a id="sec-4" name="sec-4"></a>
