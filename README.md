# Wind Blade

A fruit-slicing arcade game played with a recorder. Blow the right note into the microphone and the matching fruit is cut in half.

Wind Blade is part of **Dato Music Lab** (https://datomusiclab.dpdns.org), a working elementary music teacher's studio in Taipei.

## What it is

A recorder lesson has an attention problem: practice is repetitive, and the feedback loop between blowing a note and knowing it was right is slow and mediated by a teacher who can only listen to one child at a time.

Pitch detection closes that loop. The game listens to the actual fundamental frequency coming out of the instrument, so being nearly right is visibly not the same as being right — and a child can hear that for themselves, at their own desk, thirty times a minute.

## Features

**Microphone pitch detection.** An autocorrelation algorithm tracks the recorder's fundamental in real time across Sol, La, Si, Do and high Re.

**A live tuner.** The display shows sharp or flat, which is what turns "wrong" into something a student can actually correct — usually a breath problem, not a fingering one.

**Hold-note fruit.** Large fruit must be sustained to the end of the note before it scores, so duration gets trained alongside pitch.

**Fever mode.** Consecutive slices build energy; filling the bar doubles scoring for a burst.

**Two difficulties.** Tortoise for beginners, hare for speed.

**Sixty-second runs** with a local top-five leaderboard.

**Fills the screen.** 100vw × 100vh, sized for tablets and interactive whiteboards.

## How to use

Download the folder and open `index.html`. Grant microphone access when asked. If the notes are accurate but nothing responds, raise the sensitivity in the settings panel.

| Input | Action |
|:---|:---|
| Blow into the microphone | The main input — play the note to slice that fruit |
| `Z` `X` `C` `V` | Keyboard fallback for Sol, La, Si, Do |
| `Shift` / `B` | Switch difficulty |

## Note reference

| Note | Frequency | Colour |
|:---:|:---:|:---:|
| Sol | 784 Hz | Gold |
| La | 880 Hz | Orange |
| Si | 988 Hz | Red |
| Do | 1047 Hz | Green |
| Re (high) | 1175 Hz | Purple |

## In the classroom

Pitch and breath-control training in recorder lessons; a five-minute warm-up where the class competes on score before the lesson proper; and self-directed practice at home, where the tuner does the job a teacher would otherwise have to do in person.

## Tech

A single HTML file — pure front end, no framework, no backend, no build step. `getUserMedia` feeds an `AudioContext` and `AnalyserNode`; autocorrelation extracts the fundamental; the fruit, effects and particles are all drawn by hand on an HTML5 Canvas; scores persist in `localStorage`.

```
index.html    The whole game, all logic inline
icon.jpg      Cover image
```

## License

Code is MIT — see [LICENSE](LICENSE). Artwork is original work by Yucheng Lin under separate terms; see [NOTICE.md](NOTICE.md).

## More from Dato Music Lab

The same microphone trick flies a plane along a staff in another game, where blowing higher lifts the aircraft to the right line or space. If the class needs duration rather than pitch, there is a rhythm game about squeezing ketchup for exactly the length of each note; and for reading, a two-team sight-reading tug-of-war on one touchscreen. All at **https://datomusiclab.dpdns.org**.
