# budo script

A specification (and hopefully implementation soon) of a language to describe kata
and to represent them visually.

Disclaimer: this is absolutely not a way to replace martial art teachers, but merely a tool to help with memorizing sequences and avoid transmission mistakes.

Description and representation will always be approximative and can't describe all the details and feelings that comes in real life.

## Requirements

- all kind of budos
- human body puppet (could be generized to any puppet)
- customizable (opponents of different size, shape, gender)
- footwork
- kamae (stances)
- strikes / punchs / kicks
- throwing weapons (arrow, shuriken, etc)  
- simaltenous moves of different characters
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

### Human puppet

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

## Specification


### Example Kenjutsu

org.budoscript.kobudo:katori:
```yaml
roles:
- student:
  aka: 
    - KK: Kiri Komi
    - UK: Uchi Komi
- teacher
  aka: 
    - UD: Uke Dachi

units:
  - shaku: 30.30 cm
  - jo: 10 shaku
  - sun: shaku / 10
  - hiro: 6 shaku # human wingspan ~1.818m
  
weapons:
- katana
  - tsuka (right hand)
    - tsuka-kashira (left hand)
  - tsuba
  - nagasa
    - kissaki
    - mono-uchi

kiai:
  - ei
  - ya
  - to

kamae:
  - salute:
      feet:
  - migi:
      feet:
        # F=Forward, B=Backward, R=Right, L=Left
        # relative to gravity center (hips)
        # or 0.4,0.1 (F/R == positive) ?
        # direction/angle: -180/+180? or NW==-45?
        # unit? step? shoulders width?
        right: F0.4,R0.1,A0
        left: B0.6,R0.1,A-60
  - seigan: extends migi

distance:
  - chika-ma # 1 tatami
  - ma # 2 tatami
  - to-ma # 4 tatami
    
timing:
  sen: # as soon as opponent shows intention
  go: # opponent preparing attack
  tai: # opponent's moving (tai sabaki)
  machi: # opponent has almost finished his strike

moves:
  - ayumi-ashi:
      - if rightFoot > leftFoot:
          hips: +0.5s
          leftFoot: +1s
      - if leftFoot > rightFoot:
          hips: +0.5s
          rightFoot: +1s
  - tuski-ashi:
      ...
  - maki-uchi:
      - prepare:
          leftFoot: +1s
      - strike:
          rightFoot: +1s
          kissaki: opponent.head

kata-groups:
  - iai:
      KK: katana
  - kenjutsu:
      KK: katana
      UD: katana
  - bojutsu:
      UK: bo
      UD: katana
  - nagijutsu:
      KK: naginata
      UD: katana
          
```

Kata 
```yaml
```


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
