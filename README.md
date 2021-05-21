# budo script

A specification (and hopefully implementation soon) of a language to describe kata
and to represent them visually.

The scripting is split into different files for different purposes:
- kata scripts: human readable / natural language for a practitioner of the art (but abstract for computers)
- art dictionary: technical details: describes how to reproduce each move/strike (but still relative, no absolute distance for ex)
- visualization: provides settings to represent it as an animation (avatars, weapons look, etc)
  - needs the art dictionary to render a kata script

Disclaimer: this is absolutely not a way to replace martial art teachers, but merely a tool to help with memorizing sequences and avoid transmission mistakes.

Description and representation will always be approximative and can't describe all the details and feelings that comes in real life.

### Example Kenjutsu

Example kata of kenjutsu:
```yaml
art: 'org.budoscript.kobudo:kenjutsu:latest'
name: example kata
init:
  roles:
    P1: katana
    P2: katana
  distance: 2 tatamis
  stance:
    *: seigan
steps:
  -
    P1: gedan
  - 
    P2: men-uchi
    P1: te-ura-gasumi
  -
    P1: men-uchi
    P2: gedan
```

In short P2 strikes men, P1 counter-attacks.

That example implies that kamae/strikes (seigan, gedan, men-uchi) are defined by `org.budoscript.kobudo:kenjutsu`.

