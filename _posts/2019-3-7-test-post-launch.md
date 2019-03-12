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
  z-index: 2;
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
  z-index: 2;
  background-size: 100% 2px, 3px 100%;
  pointer-events: none;
}
.crt {
  animation: textShadow 1.6s infinite;
}
```

