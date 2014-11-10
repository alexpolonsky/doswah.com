---
layout: post
title: "Why Is There Never A Big Red Button?"
description: "Using a big red button to trigger a photobooth."
modified: 2014-08-24 19:58:26 -1000
category: []
tags: []
image:
  feature: 
  credit: 
  creditlink: 
comments: true
share: true
---
We all want the obvious answer. 
When faced with a decision, we want that big red button because we all like
to emphasize the moment we come to a decision. There's just something sexy about it. 
It's simplicity and boldness makes deciding much easier (even for Time Lords).
<figure>
	<img src="/images/Button/doctor-who.png">
	<figcaption>Doctor Who</figcaption>
</figure>

## A Photobooth Trigger

An application of such a button is to take pictures with a photobooth. 
You're about to take an epic selfie with your friends, so why not?
<br><br>
The idea is to use a button paired with an [Arduino Micro](http://arduino.cc/en/Main/ArduinoBoardMicro) 
to emulate a mouse click to start a Photobooth application. The Micro is the perfect microprocessor because of it's size and the built-in USB communication. So after ordering a 
[dome button from Karlsson Robotics](http://www.karlssonrobotics.com/cart/big-dome-push-button-red/)
I began programming.
<figure>
	<img src="/images/Button/button.jpg">
</figure>
By using the Karlsson Robotics [tutorial](http://play.karlssonrobotics.com/tutorials/circuits/wire-big-dome-button/), 
I understood the reasoning behind a normally open (NO) or normally closed (NC) switch. 
In terms of digital logic, a NO switches from a 0 to 1 and a NC switches from a 1 to 0.
<br><br>
Since we are essentially powering an LED, the Arduino operating voltage (5V) is sufficent 
to power the button as well. Initializing the mouse button functionality is as simple as
adding this to the setup function:

{% highlight html %}
pinMode(mouseButton, INPUT);
Mouse.begin();
{% endhighlight %}

After connecting the NO pin to a digital input on the Arduino Micro, I setup the Arduino so 
whenever the big red button is pressed, I can emulate a particular mouse click. I triggered a mouse left-click by adding:

{% highlight html %}
if (clickState == HIGH) {
    Mouse.press(MOUSE_LEFT); 
}
{% endhighlight %}

It's as simple as that. Even the doctor himself thinks it's cool.

<figure>
	<img src="http://28.media.tumblr.com/tumblr_lofhnlEdGv1qmm6ylo1_500.gif">
	<figcaption>Doctor Who</figcaption>
</figure>

The process is pretty straight-forward. There are a lot of USB functions you could set up such as 
mouse movement or triggering keyboard keys. The possibilites are only limited to your imagination!  I'll post a circuit schematic and video soon.
