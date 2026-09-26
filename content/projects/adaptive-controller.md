---
slug: adaptive-controller
title: "Adaptive Controller for Hemiparesis"
subtitle: "Product Engineer, Team PlayMakers"
dates: "Jan 2026 - Apr 2026"
location: "University of Michigan, ENGR 100"
hero: "images/adaptive_hero.jpg"
tags: ["Accessibility", "Onshape CAD", "3D Printing", "Woodworking", "User Testing", "Team Project"]
description: "A three-person adaptive game controller designed for a user with hemiparesis: right-hand-primary controls, one large low-force acceleration button for the weakened left hand, and a flat wooden case that rests on a table."
---

## The Problem

Standard game controllers require full two-hand operation. For our user, Morgan, that is a hard barrier: hemiparesis has left her left arm and hand significantly weakened, to the point that she cannot use a standard controller. She wanted to play Mario Kart with her family.

That gave our team, PlayMakers, three constraints to design around:

- The controller has to be fully functional using only the right hand.
- It has to rest on a surface, because she cannot lift and hold it.
- It only needs the buttons Mario Kart uses. We did not have to cover every game.

## Design Criteria

We turned Morgan's needs into three requirements and translated each into something we could measure.

| Requirement | Specification |
| --- | --- |
| Primarily right-hand control | Two buttons within 2 cm of each other; joystick within 9.5 cm of the two-button cluster |
| Accessible left-hand button | Minimum radius 2-3 cm, at least 2 cm positional tolerance, no more than 2 N actuation force |
| Stability | A flat base that stays put on a surface without tipping or sliding |

The specifications follow directly from the requirements. Right-hand control means keeping every control inside the natural reach of one hand. An accessible left-hand button means it has to be easy to press in both size and force. Stability is the most straightforward of the three: a box with a smooth, flat base.

## Design Overview

The controller has three parts: the right-hand control system, the left-hand input, and the base structure.

![Labeled control layout: acceleration, drift, item, and steering](images/adaptive_layout.png)

The right hand covers the joystick plus the drift and item buttons, grouped close enough together that the user never has to change grip. The left hand gets a single large acceleration button that she can rest her hand on top of and press without any precision at all. And because Mario Kart has an auto-acceleration option, even that button is optional. The controller can be played one-handed if she wants.

We 3D printed all the buttons ourselves so we had direct control over hitting our specifications and over fitting the printed caps onto the actual switch and stick hardware.

![Inside the case: Pro Micro board, joystick module, key switches, and the acceleration button](images/adaptive_internals.jpg)

## Right-Hand Inputs

Two custom parts sit under the right hand: a concave stick cap and two keycaps.

![Stick cap side profile](images/cad_stick_side.png)

The stick cap is concave, 10 mm in radius and 8.4 mm tall, so the user's thumb has something to rest inside of instead of sliding off mid-race. Grooves on the stick add more grip.

![Keycap bottom face](images/cad_keycap_bottom.png)

The keycaps were the hardest parts to get right. The cavity has to match the switch stem almost exactly or the cap will not seat, and that was difficult even with the precision CAD gives you. We chose keycaps over other button types because we wanted buttons that are simple to press repeatedly with a single finger, which is what makes comfortable one-handed play possible. Each cap is 17 mm on a side and 11.1 mm tall.

## Acceleration Button

![Acceleration button, top face](images/cad_accel_top.png)

The left-hand button is 25.5 mm in radius and 35.4 mm tall, with a rectangular cutout in its base so it fits around the support holding the switch. We sized it to be just large enough to cup a hand around, so the hand rests naturally on it during play. We tried going bigger and found it did not actually make the button easier to use, while costing a lot more print time and material.

## Supports and Case

Three 3D-printed supports hold each component in place and raise it far enough to stick out through the lid. From the key buttons to the control stick to the acceleration button, they are 35 mm, 30 mm, and 15 mm tall. The acceleration support is much shorter to account for how that button has to sit inside the case. All three were attached to the base with super glue.

![Case side profile with the cable pass-through](images/adaptive_case_side.jpg)

We built the foundation out of wood. It has the right weight for the job and it is easier to work with than metal, and printing a case this size would have been an enormous print for a very simple shape. The walls were screwed together and glued to the base, the lid screwed into the top of the walls, and a hole drilled through for the cord. The acceleration and stick holes were cut with a circular drill bit; the keycap holes were done with a hand saw.

The interior is 4.25 cm deep, with intended exterior dimensions of 35 cm x 25 cm x 5 cm.

## Verification Testing

We measured against every specification in the table above using rulers and calipers.

![Measuring button spacing and joystick distance](images/adaptive_verification.jpg)

The spacing between the right-hand buttons came in under 2 cm, and the joystick was confirmed within 9.5 cm of the button cluster.

![Force gauge reading 0.96 N on the acceleration switch](images/adaptive_force_test.jpg)

The acceleration button measured a 2.5 cm radius and an actuation force of 0.96 N, comfortably under the 2 N ceiling.

Stability is not something you can put a number on, so we tested it through actual gameplay. The controller stayed in place consistently, and even rough movements from the user had little to no effect on it. The wooden base helps here.

## Usability Testing

We had five participants use the controller for roughly 20 minutes each, then asked them to assess it. We counted a trial as successful if the participant could use the controller intuitively while staying inside our requirements, and we watched how smoothly the major functions went: accelerating, steering, drifting, and using items.

![A participant's hands on the controller](images/adaptive_usability.jpg)

All five participants were able to operate the main functions. Most reported that the button placement felt comfortable and within reach, and several said that separating the major functions across the board made it easier to learn which control did what.

The feedback we got was specific and useful:

- The surface could use some cushioning.
- The distance between the joystick and the right-hand buttons felt too large for some users, with some strain on the right hand.
- There was some confusion about how to place a hand on the acceleration button.

Despite those issues, every participant adapted quickly and used the controller effectively.

## What Worked and What Didn't

The design is functional. The prints came out solid, and the specifications produced a control scheme that is genuinely comfortable and accommodating. It can be used one-handed, the left hand is optional, and it rests flat and stable. Playing with it feels exactly the way we intended, and the usability test backed that up.

The case is the disappointment. Precision woodcutting is clearly not a skill you acquire quickly. The dimensions listed above were the intended ones; the actual case came out closer to 34.5 cm x 24.25 cm x 5 cm, and even that is generous, because our imprecision produced a slight trapezoid rather than a rectangle. None of the pieces fit together as well as we wanted. The lesson is to build the case first: most of the trouble came from working fast to get something usable rather than something presentable.

## Recommendation

Taking a step back, the design accomplishes the task but it is also just a box, which does not distinguish it much from the Xbox Adaptive Controller. Aside from arriving preassembled in one configuration, it does not do anything explicitly better.

The button layout is the strongest part of what we made. If another team picks this up, they should go back to the layout and diversify from there, and push harder on isolating the left hand from the one-handed controls. Simplicity is not a bad thing, but here it is underwhelming next to what the idea could have been.

## What I Took Away

This project is where I learned that a requirement is worth very little until you turn it into a number you can measure with a tool in your hand. "Easy to press" became 0.96 N on a force gauge. "Within reach" became 9.5 cm on a ruler.

It also taught me to respect the fabrication step as much as the design step. Our CAD was good. Our woodcutting was not, and the final object is judged on both.
