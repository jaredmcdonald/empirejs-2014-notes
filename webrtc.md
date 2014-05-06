# webrtc

[http://www.webrtc.org/]()

Chats, and other P2P-type interactions, needing to go through (often distant) servers is not a model that makes a lot of sense. Why can't we cut out the server component?

It's hard. We need it to be secure, and fast.

Enter **WebRTC**: peer-to-peer video, audio, and data in the browser. A set of APIs.

    var connection = new RTCPeerConnection({ config })

    // do some stuff...

    connection.createOffer(function(offer){ ... })


Need a signaling server to configure connections.

`STUN`, `TURN`, `ICE` - getting around `NAT`



## getUserMedia

[http://shinydemos.com/getUserMedia]()

Pretty simple, theoretically, but...

[http://iswebrtcreadyyet.com]()


## libraries to make it easier

peerjs - library [http://peerjs.com/]()

simpleWebRTC

rtc.io
