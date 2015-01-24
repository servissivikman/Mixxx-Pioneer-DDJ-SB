# Pioneer DDJ-SB MIDI Mapping for Mixxx

## Description 

This is a basic mapping for Mixxx for the Pioneer DDJ-SB (2 decks). The code is based on / forked from hrudham's project: Mixxx-Pioneer-DDJ-SR (https://github.com/hrudham/Mixxx-Pioneer-DDJ-SR). I've used the same methods but stripped it a bit so it works for my DDJ-SB and also so the code is understandable to me. I like to understand what I implement. So I might have deleted some cool functionality from the original project ...

* It requires v1.11. Certain functionality will NOT work in previous versions.
* Forum Thread on mixxx.org -> http://www.mixxx.org/forums/viewtopic.php?f=6&t=6886

## How do I use it?

If you just want to get your controller working with with Mixxx without bothering about the details much, then do the following:

1. Download the following two files:
    - [PIONEER-DDJ-SB.midi.xml] (https://github.com/wingcom/Mixxx-Pioneer-DDJ-SB/blob/master/Pioneer-DDJ-SB.midi.xml)
    - [PIONEER-DDJ-SB-scripts.js] (https://github.com/wingcom/Mixxx-Pioneer-DDJ-SB/blob/master/Pioneer-DDJ-SB-scripts.js)
2. Copy these to the `[Mixxx Directory]/controllers` folder. This will probably be one of the following locations:
    - Windows: `C:\Program Files\Mixxx\controllers`
    - Linux: `/usr/share/mixxx/controllers or /usr/local/share/mixxx/controllers`
    - OS X: `/Applications/Mixxx.app/Contents/Resources/controllers/`
3. Make sure your Pioneer DDJ-SB is plugged in and turned on
4. Open (or restart) Mixxx, and enjoy using your (semi-functional) controller

## What's implemented?

I've only implemented what I need and "know of" for now...

- General
    - Cross-fader
    - Volume Control
	Channel, Master and Headphones
    - Manual Filtering
	High, Mid and Low
    - Playlist browsing
    	- Back : switches between Tracklist and Sidebar
    	- RoatrySelector : browses through the Tracklist of the Sidebar
    	- RotarySelectorClick : Expands or Collapses the Sidebar item
    	- Load : loads the selected track in the Left or Right deck
    - Sampler Control
    	- Push : Starts playing the sample from start
    	- Shift-Push : Stop playing the sample
    - Pitch Control 
    	- Inverted. With my current skin I can not get this to work as intended even if I change the setting
- Deck Controls
    - Play / Pause / Cue
    	- Cue: Sets the Cuepoint when not playing, Jumps to Cuepoint when playing
    - Vinyl Mode
    - Keylock
    - Precue'ing
    - Hotcue Control (4 can be set)
    	- Push: Sets the hotcue and lights up the LED of the pushed button.
    	- Push again: Turn of the hotcue point
    - Autoloop Control
    	- 4 Autoloops can be set (no shift use on Performance Pads yet) on: 1 beat / 2 beats / 4 beats and 8 beats
    	- If you want other beatloops you need to change the xml and the LoopInterval Enum in the Init() function
    - Manual loop Control (still buggy)
    	- In   : Sets in point
    	- Out  : Sets out point
    	- Exit : Not working yet. Pretty annoying :)
    	- 1/2  : Cut loop in half
    - Jogwheel Control
	When playing in normal mode, only touching/turning the side will result in pichbend. All other 
	interactions are disabled in this mode.

	- NORMAL MODE (when playing)
		- Pitchbend using the side of the Jogwheel
	- NORMAL MODE (when not playing)
		- Scratching / Seeking when turning the Jogwheel surface
		  I've switched this to Scratchmode, it makes seeking by using the jogwheels quicker.

	For the next mode I've tried to make the DDJ-SB behave like a vinyl as much as I understand of it.
	
	- VINYL MODE (when playing)
		- Brakes when touching the Jogwheel surface, Starts again when releasing.
		- Pitchbend using the side of the Jogwheel
	- VINYL MODE (when not playing)
		- Scratching / Seeking when turning the Jogwheel surface

## What's missing?

- Shift Functions of the Performance Pads
- Manuel loop bug
- Reversed Pitch Control
- Channel Filters
- Crossfader Automatic Filter
- Effects (Not available in Mixxx I think?)
- Decks 3 and 4

I will definitly fix the Manual Loop bug and as I go along and need more stuff I might implement the exta functions (Performance Pads Shifts) same goes with deck 3/4 which, atm, I don't need those.

If I stumble upon good code to do the filtering, I will probably implement that too. Suggestions are welcome.
