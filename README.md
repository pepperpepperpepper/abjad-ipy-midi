Abjad-MIDI IPython Extension
============================

[1]: http://ipython.org/notebook.html
[2]: http://www.projectabjad.org/
[3]: http://sourceforge.net/apps/trac/fluidsynth/
[4]: http://sourceforge.net/apps/trac/fluidsynth/wiki/SoundFont
[5]: https://github.com/tiagoantao/abjad-ipython

This is an [IPython][1] module that renders [Abjad][2] expressions as
HTML5 `<audio>` tags inside Notebooks. Rendering relies on [Fluidsynth][3]
and a SoundFont, which you can find [here][4] or you can source your own. It
works by replacing the top-level `play()` method in Abjad.

The module can be loaded into your own notebooks using the example code below:

```python
from abjad import *
%load_ext abjad_midi.ext.fluid
loadSoundFont('path/to/soundfont.sf2', 'gm')

pitch_numbers = 4 * [0, 2, 4, 9, 7]
duration = Duration(1, 8)
notes = scoretools.make_notes(pitch_numbers, duration)
staff = Staff(notes)
play(staff)
```

This project was inspired by the wonderful work of [Tiago Antao][5], which
was recently integrated into the Abjad project. 

### Prerequisites

[ipy]: http://ipython.org/install.html
[jp]: https://github.com/ctsdh-luc-edu/jpatterns
[fs]: http://sourceforge.net/projects/fluidsynth/files/

This project requires installations of [IPython][ipy], [Abjad][2] and
[Fluidsynth][3]. You can follow the instructions on [Jazz Patterns][jp]
repository for a proper install of Abjad in a virtual environment. Fluidsynth is
easily available in most packages managers, or directly from their
[Sourceforge][fs] project page, just make sure that the binary is within your
`PATH`.

## Installation

This project uses `setuptools`, so installation is as easy as:

```
git clone https://github.com/ctsdh-luc-edu/abjad-ipy-midi
cd abjad-ipy-midi
python setup.py install
```