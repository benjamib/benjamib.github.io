---
layout: post
title: "Tutorial 1: Terminal UI"
date: 2019-03-7
description: "Emulating an old school terminal with HTML and CSS"
---

One of the key design elements to command-ui is the look and feel of the basic UI. The game is focused on the pilot of a spacecraft interacting with the ship systems and AI through an old school crt-like terminal. Capturing this
retro terminal feel was the first task that I took on as part of creating the game.

The game itself is written entirely in HTML, CSS, and Javascript. The terminal UI is accomplished purely with CSS.

To start I assign my "crt" class to the entire body of the HTML page.

```
<body class="crt">
  
</body>
```
The "crt" class contians the following CSS.

```
.crt::after {
  content: " ";
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background: rgba(18, 16, 16, 0.1);
  opacity: 0;
  pointer-events: none;
}
.crt::before {
  content: " ";
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
  background-size: 100% 2px, 3px 100%;
  pointer-events: none;
}
```

The ".crt::after" creates a nearly black background positioned absolutely on the screen.

The ".crt::before" creates a repeating background image that is a linear gradient. The linear gradient is what adds the scan line effect to the text that makes it look like an old school crt display.

To add a little extra crt-iness to the dispaly, I added a CSS animation that adds misconvergence to the display. This is the effect of the different color channels not always lining up.
The effect is created by animating a text-shadow that isolates the RGB colors at different intensities and positions.

```
@keyframes textShadow {
  0% {
    text-shadow: 0.4389924193300864px 0 1px rgba(0,30,255,0.5), -0.4389924193300864px 2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  5% {
    text-shadow: 2.7928974010788217px 0 1px rgba(0,30,255,0.75), -2.7928974010788217px 2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  10% {
    text-shadow: 0.02956275843481219px 0 1px rgba(0,30,255,0.5), -0.02956275843481219px 2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  15% {
    text-shadow: 0.40218538552878136px 0 1px rgba(0,30,255,0.75), -0.40218538552878136px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  20% {
    text-shadow: 3.4794037899852017px 0 1px rgba(0,30,255,0.5), -3.4794037899852017px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  25% {
    text-shadow: 1.6125630401149584px 0 1px rgba(0,30,255,0.75), -1.6125630401149584px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  30% {
    text-shadow: 0.7015590085143956px 0 1px rgba(0,30,255,0.5), -0.7015590085143956px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  35% {
    text-shadow: 3.896914047650351px 0 1px rgba(0,30,255,0.75), -3.896914047650351px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  40% {
    text-shadow: 3.870905614848819px 0 1px rgba(0,30,255,0.5), -3.870905614848819px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  45% {
    text-shadow: 2.231056963361899px 0 1px rgba(0,30,255,0.75), -2.231056963361899px -2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  50% {
    text-shadow: 0.08084290417898504px 0 1px rgba(0,30,255,0.5), -0.08084290417898504px -2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  55% {
    text-shadow: 2.3758461067427543px 0 1px rgba(0,30,255,0.75), -2.3758461067427543px -2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  60% {
    text-shadow: 2.202193051050636px 0 1px rgba(0,30,255,0.5), -2.202193051050636px -2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  65% {
    text-shadow: 2.8638780614874975px 0 1px rgba(0,30,255,0.75), -2.8638780614874975px -2px 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  70% {
    text-shadow: 0.48874025155497314px 0 1px rgba(0,30,255,0.5), -0.48874025155497314px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  75% {
    text-shadow: 1.8948491305757957px 0 1px rgba(0,30,255,0.75), -1.8948491305757957px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  80% {
    text-shadow: 0.0833037308038857px 0 1px rgba(0,30,255,0.5), -0.0833037308038857px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  85% {
    text-shadow: 0.09769827255241735px 0 1px rgba(0,30,255,0.75), -0.09769827255241735px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  90% {
    text-shadow: 3.443339761481782px 0 1px rgba(0,30,255,0.5), -3.443339761481782px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  95% {
    text-shadow: 2.1841838852799786px 0 1px rgba(0,30,255,0.75), -2.1841838852799786px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
  100% {
    text-shadow: 2.6208764473832513px 0 1px rgba(0,30,255,0.5), -2.6208764473832513px 0 1px rgba(255,0,80,0.53), 0 0 3px;
  }
}
```

This CSS animation is added to the "crt" class.

```
.crt {
  animation: textShadow 4.6s infinite;
}
```

This takes care of the basic styling for the page. The next step is to create a place to dispaly the terminal output. To hadle this I use a text area with some basic styling.

```
<textarea class="output"></textarea>

.output {
  background-color: transparent;
  color:rgb(50,255,0);
  font-family:"VT323",monospace;
  border: none;
  height:650px;
  width: 1200px;
  outline: none;
  box-shadow: none;
  padding: 0;
  letter-spacing: .1em;
    font-size: 24px;
    -webkit-font-smoothing: none;
    line-height: 1.2;
}
```

The green text color is a vibrant retro terminal green and the font is a monospaced terminal-style font keeping with the overall design aesthetic. I also removed all borders and padding.

The final step is to create the input text box with the prompt.

```
    <div><span>root@SAM </span></div>
      <div><span>$</span>&nbsp;
        <input class="command"/>
      </div>
    </div>
    
```

The "command" class is very similar to the "output" class, but just contains different sizing.

```
.command {
  background-color: transparent;
  color:rgb(50,255,0);
  font-family:"VT323",monospace;
  border: none;
  width: 90%;
  outline: none;
  box-shadow: none;
  padding: 0;
  letter-spacing: .1em;
    font-size: 24px;
    -webkit-font-smoothing: none;
    line-height: 1.2;
  
}
```

The final result is a very cool looking retro terminal.

![alt text](https://benjamib.github.io/assets/Screenshot 2019-03-11 at 11.08.42 PM.png "Retro Terminal")