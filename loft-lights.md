<!-- TITLE: Loft Lights -->
<!-- SUBTITLE: A quick summary of Loft Lights -->

The Led strips on the Loft in the center room can be controlled by navigating to:
http://10.0.1.107/

or

http://loft.queer/

and using the Red, Green, Blue, White, and Blacklight values limited by 0 and 1023, and pressing the Color button.

You can also connect to the websocket directly at port 7777 (ws://loft.queer:7777/) and send the stringified JSON:
```
["CMD", "lights", [r, g, b, q, p]]
```

where r, g, b, w, p are in range [0,1023]