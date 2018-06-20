# 31 EDO Retuner plugin for Musescore 2

Musescore plugin to automatically retune notes in [31-EDO](https://en.wikipedia.org/wiki/31_equal_temperament)

## Usage

- To retune the entire score as is, simply run the plugin and click "Retune!"

- If a selection was made prior to clicking "Retune!", only the selected
notes will be affected.

### Accidentals

#### Ups and Downs notation (diatonic enharmonic equivalent)

In ups and downs notation mode, these are the accidentals used by the
plugin. They can be found in the [advanced palette](https://musescore.org/en/handbook/palettes-and-workspaces#workspaces).

| Diesis steps | Accidental |
| ---: | :-----:|
| -5  | ![Double flat](images/bb.png) |
| -4  | ![Sesqui flat](images/db.png)  |
| -3  | ![Flat down](images/bd.png)  |
| -2  | ![Flat](images/b.png)  |
| -1  | ![Down](images/d.png) or ![Flat up](images/bu.png) |
| 0   | ![Natural](images/n.png) |
| +1  | ![Up](images/u.png) or ![Sharp down](images/sd.png) |
| +2  | ![Sharp](images/s.png)  |
| +3  | ![Sharp up](images/su.png) |
| +4  | ![Sesqui sharp](images/ss.png)  |
| +5  | ![Double sharp](images/x.png)  |

> Important: This notation differs from the more conventional meantone notation
> which uses quarter-tone accidentals instead. Meantone notation support is still a WIP.
>
> The benefits of using this notation over meantone is that it allows for proper
> spelling of notes and chords in all transpositions as it still supports enharmonic diatonic-tone equivalents
> by means of the double flat and double sharp accidentals.

#### Meantone (quarter-tone accidentals)

**WIP**

### Custom key signatures

As MuseScore doesn't completely support
[custom key signatures](https://musescore.org/en/handbook/key-signatures#custom-key-signatures),
any custom key signature can't be read by the plugin, at least for now.

Should you want to create a microtonal key signature and have it affect the
playback, you have to explicitly declare the custom key signature using some
super-special accidental code:

| Diesis steps | Accidental code |
| ----: | :----: |
| -5   | `bb` |
| -4   | `db`  |
| -3   | `bv`  |
| -2   | `b`  |
| -1   | `b^` or `v`|
| 0  | Leave blank  |
| 1   | `^` or `#v` |
| 2  | `#`  |
| 3   | `#^`  |
| 4  | `#+`  |
| 5   |  `x` |


There are two ways you can enter the accidental code as shown below

> Note that explicit accidentals will still take precedence over the
> declared custom key signature, behaving exactly the same way a key signature
> would.

#### Method 1: Using the text input fields in the plugin window

![customkeysig](images/2018/06/customkeysig.png)

This method will only allow tuning to one custom key signature at a time,
if there are changes in key signature (whether from custom to standard key, or
custom to custom), each section will have to be tuned independently by selecting
the section to retune before clicking "Retune".

#### Method 2: Using staff text [WIP]





### Note to self / developers:

##### Definitions:

`tpc`
: Tonal pitch class

## TODO:

- Don't hard-code / bruteforce frequencies, just use a dictionary a exponential operations instead
- Hence, supporting other EDOs should be easier.

## Changes:

### 1.2

- Fixed non-naturalised explicit natural accidental in note affected by a custom key signature

### 1.1

- Fixed occassional bug where microtonal accidentals carry over the bar line when it shouldn't
- Attempted to fix UI bug in Windows, haven't tested it yet though :/
