GoatTracker v2.65 Stereo
------------------------

Editor by Lasse Öörni (loorni@gmail.com)
Uses reSID engine by Dag Lem.
Uses 6510 crossassembler from Exomizer2 beta by Magnus Lind.
Uses the SDL library.
GoatTracker icon by Antonio Vera.

Distributed under GNU General Public License
(see the file COPYING for details)

Covert BitOps homepage:
http://covertbitops.c64.org


Differences to normal version: (refer to normal GT2 for full documentation)

- Only buffered write playroutine without zeropage ghostreg support can be used.

- To play sound effects on the second SID, use channel indexes 21, 28 and 35 for
  voices 1-3 respectively (in the X register)

- Command line differences:

  /Lxx (SID address parameter) takes addresses of both sids written one after
       another, right SID in the high word, for example D500D400
  /Hxx (use hardsid) is in hexadecimal format. High nybble specifies right
       hardsid ID and low nybble left hardsid ID. If right hardsid ID is omitted
       it is assumed to be left+1. For example 21 tells to use ID 1 for right &
       ID 0 for left.

- Songdata is otherwise same as normally, but there are 6 orderlists for each 
  subtune.

- Submit a patch if there are bugs in the stereo hardsid output, I have no means
  to test it.


Changelog so far:

v2.59     - Fixed channels 4-6 not setting global tempo.
          - Added missing channel 4-6 playback start checks to the editor
            playroutine.
          - Mono songs can be loaded (detection relies on checking song order-
            list validity and is not 100% certain.)
          - Vertical resolution increased.

v2.6      - Fixed channel 4-6 filter commands.
          - Fixed help screen mouse scrolling.
          - Fixed pattern default length selection display when decrementing 
            from a value of 100 or higher.
          - Fixed mouse selection of pattern when adjusting an adjacent channel.
          - Fixed help screen instructions.
          - Changed resolution to 800x600 (pattern display tightened.)
          - Changed speed of page up/page down scrolling to be faster.
          - Optimized text output routines.

v2.61     - Fixed SHIFT+channel number in orderlist edit mode (swap orderlists)
            to work with channels 4-6.
          - Fixed muting.
          - Added the backquote key (top-left on keyboard) to select channel
            in pattern edit mode, and to select table in table edit mode. Use
            with SHIFT to go backwards.
          - Added SHIFT+channel number to mute channels in pattern edit mode.

v2.62     - Added possibility for realtime calculated note independent (hifi)
            portamento & vibrato. Warning: has potential for huge rastertime
            increase.
                        
v2.63     - Fixed note independent portamento & vibrato to use the last note
            set in wavetable for calculations, instead of the last note in
            patterndata.
            
v2.64     - Fixed paste in table (SHIFT+V) working also without SHIFT pressed.       

v2.65     - Fixed raw keycodes over 511 interpreted as some other keys in the
            0-511 range.
