
## Requirements

- all kind of budos
- human body puppet (could be generalized to any puppet)
- customizable (opponents of different size, shape, gender)
- footwork
- kamae (stances)
- strikes / punchs / kicks
- throwing weapons (arrow, shuriken, etc)  
- simultaneous moves of different characters
- extensible: reuse already defined component/moves/arts to overwrite then
- licenses? npm licenses?

### Concepts

- characters / roles (typically 2 but has to stay open)
- weapons
- clothes, armor
- kamae: postures
- strikes: attack a target with(out) weapon (or barehand)

### Behavior vs representation

Like HTML vs CSS, one file will describe the behaviour (data like HTML) and another one will provide the representation (CSS).
Maybe there could be a possibility to include some CSS into the HTML (inline style).

### Human puppet (kugutsu)

Hierarchy represents the articulation (joints) of the puppet.
Ex: forearm is moving around the elbow, based on the arm position.

- root/body
  - neck (throat/nape)
    - head
      - forehead
      - month
      - eyes
      - ears
  - torso / back
  - shoulder/armpit: arms
    - elbow (in/out): forearm
      - wrist: hand
        - fingers
        - thumb
  - hips
    - thighs
      - knee/kneepit(aka hough) : legs
        - ankle/heel: feet
    - groin/crotch

All parts and joints can be targeted by strikes.

## Implementation proposal

### Language: Javascript?

### Repo: npm?

### Representation

Defines anything required to render/visualize a kata:
- puppets: size, weight, gender, etc
- colors

#### implementation?

- SVG SMIL animation
- CSS animation
- Engine JS: 2d, 3d?
