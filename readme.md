HX3 Latest Firmware
===================

#### Final releases for update with HX3 Remote application

**WICHTIG: Bitte entpacken Sie die ZIP-Files in einen Ordner auf Ihrer lokalen Festplatte. Starten Sie HX3 Flash bzw. HX3 Remote aus diesem Ordner. Beim Start direkt im ZIP-Fenster schlägt das Update fehl.**

**IMPORTANT: Be sure to extract all files to a local hard disk folder. Update will fail if started directly from ZIP window.**

### Update Packages for Customers

New: Complete update packages for most common HX3 instruments for a hassle-free update to newest version. 
The ZIPs Flash_XXX.zip contain only the files needed for your instrument. 
You don't need the other HX3 stuff offered here, just make sure you use **only the new files and HX3 Flash utility** contained in dedicated ZIP package. 

For example, if you own a **HX3 MIDI Expander Plexi**, download 
**[Flash_ExpanderPlexi_mk3_4.zip] (https://github.com/keyboardpartner/HX3/blob/master/LATEST/Flash_ExpanderPlexi_mk3_4.zip?raw=true)** and unzip folder to local hard disk.
It countains the new <b>HX3 Flash utility</b> which will run a complete update free of doubt. 
See wiki page **[HX3_Update_Application] (http://wiki.keyboardpartner.de/index.php?title=HX3_Update_Application)** for description. Following update packages are available:

### Firmware #4.22 Update Packages

* **[Flash_DrawbarExpander.zip] (https://github.com/keyboardpartner/HX3/blob/master/LATEST/Flash_DrawbarExpander.zip?raw=true)** - for new HX3 DrawbarExpander
* **[Flash_ExpanderPlexi_mk2.zip] (https://github.com/keyboardpartner/HX3/blob/master/LATEST/Flash_ExpanderPlexi_mk2.zip?raw=true)** - for HX3 MIDI Expander Plexi, older mk2 version (up to 1/2014)
* **[Flash_ExpanderPlexi_mk3_4.zip] (https://github.com/keyboardpartner/HX3/blob/master/LATEST/Flash_ExpanderPlexi_mk3_4.zip?raw=true)** - for HX3 MIDI Expander Plexi USB, current mk3/mk4 versions
* **[Flash_OrganMag.zip] (https://github.com/keyboardpartner/HX3/blob/master/LATEST/Flash_OrganMag.zip?raw=true)** - for MAG custom organs. Has different drawbar tapering

<b>Please note:</b> Standard organ installations will only install default paramaters. 
Please use HX3 Remote (contained in complete firmware package) to setup parameters for your particular application.
Older firmwares may be found on **[ARCHIVED_FIRMW] (https://github.com/keyboardpartner/HX3/tree/master/ARCHIVED_FIRMW)** page.


### Update Packages for OEM/Developers/Technicians/Advanced Users

Copy and unzip HX3_firmw_XXX.zip to a new folder on your hard disk, for example 
E:\HX3\LATEST\. See http://wiki.keyboardpartner.de/index.php?title=HX3_Update_Application for 
details on update procedure. Scroll to bottom of page for file usage.

### Last Build

* HX3 Remote: #4.22 .exe for Windows XP and up
* HX3 Flash: #4.22  .exe for Windows XP and up
* HX3 Tapering	    .exe for Windows XP and up
* AVR:  #4.25      .hex and .eep files, latest firmware for AVR controller
* FPGA: #17042017   .bit configuration file for FPGA update
* SCAN: #33         .dat ScanCore files for MIDI and FATAR

### Changelog

<b>03/17/2017</b> ScanCore for Fatar #35

* Sustain/Sostenuto hardware switches on PL16, switch to ground
* MIDI CCs for Sustain/Sostenuto sent on separate channels
* MIDI Cancel inputs PL 16 Pin 1 (upper) and 2 (lower)
* Sustain inputs PL 16 Pin 4 (lower) and Pin 6 (upper)
* Sostenuto inputs PL 16 Pin 3 (lower) and Pin 5 (upper)
* Corrected behaviour fast key = long click, slow key = short click


<b>04/24/2018</b> ScanCore #23 for XB-2 mk3/4 Kit

* Corrected behaviour fast key = long click, slow key = short click
* Audible key off noise when Contact Damping param > 7

<b>02/07/2018</b> Firmware 4.25 for XB-2 mk3/mk4, FPGA #25042017

* Updated firmware in folder Flash_XB2_mk3 to latest version 
* Problems with secondary MIDI input: Newer FPGAs seem to have stronger internal pull-up 
resistors, so second MIDI input (often used for bass pedals or drawbar 
controller) may not work properly. Please update to FPGA #25042017 if you 
experience this issue. Do not use FPGA #25042017 on older mk2 boards (#24042017 
is OK). 
* Small changes to HX3 Remote to fit small screens (notebook etc.), 
"moved folder" bugfix (resets file info when path to parameter files does no longer exist)

<b>11/05/2017</b> ScanCore #24 for SR44, SR49 and SR61

* "Last note on lower manual distorted" bug fixed for ScanStrip16 and ScanInline61 boards
* Silent Update for Expander/Drawbar Expander mk3/4 Firmware (no new version number): 
* Will accept MIDI CCs for swell and volume on all 3 channels now

<b>04/17/2017</b> Firmware #4.25, FPGA #17042017

* ARGHH! Rotary Sim volume permanently set to 0. Bug fixed. No new version number.
* Slightly changed FPGA 17042017 to match TG Flutter setting of previous versions
* DO NOT USE ZIPs from 04/14/2017!

<b>04/14/2017</b> Firmware #4.25, FPGA #10042017

* Glitches in filter assignment and leakage generation fixed
* internal signal processing with more headroom
* Tuning capability, parameter "TG Gears Tune" on display, A = 433 to 447 Hz
* phase and amplitude noise/leakage improved
* Sustain/sostenuto hardware inputs on MIDI and FatarScan Core, see below
* Sostenuto CC #64 works also on FatarScan if enabled by MIDI CC (*.) menu
* Lowered distortion on TG notes 48 and up, less interference
* Hardware inputs on PL16 for Sostenuto/Sustain pedal connection
* Sostenuto working with MIDI #64 and hardware inputs
* Improved key velocity on MIDI out for FATAR (also available as separate ScanCore update)
* Improved click evaluation in MIDI and FATAR scan cores
* Lowered rounding noise of vibrato scanner, was noticeable with no drawbars pulled and key pressed

Completely revised my old generator design, dating from 2012. There might have been a 
glitch in my old code that assigned wrong LC filter numbers (i.e. their 
simulation) to some generator notes, so some notes were to weak or too loud even 
with "new" tapering. New generator has a smooth response with "new caps" 
selected in menu. Please revise your own tapering files if needed. Also FM/phase 
noise revised, may need readjustment of TG Flutter param to get that "blowing a 
bottle whoosh" (can't describe it better) on each note.

Otherwise empty PL16 on mainboard was only used to output an auxiliary MIDI 
signal for Neo Ventilator speed control on pin 7 and some internal test signals. 
It now uses separate input pins 4 (for lower manual) and 6 (upper) for sustain 
and 3 (lower) and 5 (upper) for sostenuto, working with FATAR and MIDI scan 
cores. Switch pins to ground (pin 10) to activate sustain or sostenuto on 
particular manual. An additional 10-pin header is needed, solder in PL16 
position. If you don't need separate sutain/sostenuto inputs for upper and lower
manuals, just connect both inputs for each function, i.e. 4 and 6 for
sustain and 3 and 5 for sostenuto. Do not bridge all 4 inputs.

NOTE: Hardware input pins only work with FPGA #03042017 and up.

Both are controllable by MIDI CC #64 also (wired by "MIDI CC set" menu
to either sustain or sostenuto). These functions work even on splitted
manuals, so if you have lower on left part of manual, pin 3 affects only
sostenuto on left side. I think this should fit all needs.

<b>03/17/2017</b> Fatar ScanCore #32

* DO NOT USE PRELIMINARY #31 or #32 from 03/15/2017!
* MIDI bugfix
* improved key velocity on MIDI out
* improved click evaluation
* Typo in config.ini, displayed #32 instead of #32

<b>12/20/2016</b> Firmware #4.22, FPGA #10102016

* Wrong config data in Drawbar Expander flash package fixed on 01/10/2017
* Returned to FPGA_10102016 as found in FW 4.11 **without** "TG Gears Tune" tuning option. Tuning ability sacfrified somewhat of sound quality. If you need tuning capability, please use firmware 4.21 with FPGA_26102016.
* Fixed "Split Havoc" bug when changing parameters while playing with split on
* Fixed Master Volume display bug (wrong menu item displayed when changing)

<b>11/18/2016</b> Firmware #4.21, FPGA #26102016

*  New menu "ContEarlyActn" and HX3 Remote Parameter 491, Contact Early Action ON/OFF on FATAR keybeds:
 * If set to ON, organ will close key contacts on 1st FATAR rubber contact and send MIDI ON immediately, but without velocity.
 * If set to OFF ("George Fleury" mode), organ will close key contacts on 2nd FATAR rubber contact and send MIDI ON with velocity.
*  New menu "TG Gears Tune" and HX3 Remote Parameter 488, TG Tuning will fine tune the organ plusminus 100 cent. 
Note: To accomplish this, all TG gears must be changed which may take around 100 ms.
* Audio output config initialisation bug fixed
* "Flickering display on startup" bug fixed
* On organs with 2 DB sets, changes to presets will always be made by right set of DBs (was random before)
* Deleted "Expander Mode" parameter for organ firmwares
* Fixed Common Presets "Live" bug
* Fixed Defaults loading bug (silent update from 11/18/2016)


<b>10/11/2016</b> Firmware #4.11, FPGA #10102016

Only use with FPGA 10102016 due to new parameter handling. 

* Fixed small bugs: Preset (drawbar set) change on lower will no longer interfere with swell volume,
split point and split mode will be restored after Common Preset changed back to "live"
* Vibrato channel volume raised a bit, may require readjustment of V/C params
* Generator impedance revised, will produce more "crisp" attack when playing staccato chords

<b>09/27/2016</b> Firmware #4.10, FPGA #25092016

Firmware 4.10 has a new chorus/vibrato routing, adding new parameters in menu 
and HX3 Remote. Only use with FPGA #25092016. New params are:

* Scanner Gears: Vibrato modulation frequency
* Scanner Leak: Leakage of unmodulated signal on V1/V2/V3
* VibCh AmplMod: Modulation of upper frequency limit of LC linebox
* VibCh Preemphasis: Treble enhancement on Vib/Ch
* VibCh Reflect: Reflections on LC linebox due to aged capacitors
* VibCh Response: upper frequency limit of LC linebox
* Ch LineboxLvl: Vibrato mix on Chorus C1/C2/C3
* Ch BypassLvl: Dry mix on Chorus C1/C2/C3
* V1 ModAmount: Modulation depth on V1
* ...
* C3 ModAmount: Modulation depth on C3
* Adjustable busbar levels for each drawbar

Note: Some advanced parameters are available by HX3 Remote and PREMIUM version 
only. These menu items are visible in menu system, but locked in normal version. 
Obtain a PREMIUM organ licence to make them accessible by menu panel.

<b>06/27/2016</b> FATAR ScanCore #25, MIDI ScanCore #30

* Added separate update package for FATAR/MIDI, will update ScanCore only
* Changed MIDI velocity scaling to triple squared curve in FATAR ScanCore 
* "Missing notes" bug in FATAR ScanCore fixed
* New MIDI ScanCore #30 with 88 key support, full transpose 24 notes, upper manual split +1 and +2 octaves on lower part

<b>05/05/2016</b> Firmware #3.925, HX3 Flash #3.9e

* HX3 Remote Dropdown menu bug on Win XP fixed
* XB2 Kit Transpose with PERCUSSION buttons (SECOND = DOWN, THIRD = UP) when Edit Mode ON
* Easier multiple Common Preset combination select, blinking LEDs when saved
* Updated HX3 Remote and HX3 Flash
* New MIDI and FATAR SCanCores (see above)
* New "AUX Pot" Routing (was TONE pot analog input enable), TONE pot input may be routed to MASTER VOLUME or TONE function by HX3 Remote Parameter 492
* Drawbar 9 MPX switching signals for mk2/mk3 boards provided on pin 6 and 7 of PL5 (see our wiki pages)

<b>04/26/2016</b> Firmware #3.924, HX3 Flash #3.9e

* Severe bug in Drawbar Expander firmware fixed, did not respond to Reverb/Split/AB buttons, was introduced in 3.922 
* Severe bug in Leslie control on extension board fixed, was introduced in 3.922 
* Minor bug in HX3 Flash fixed. Now writes last update time & date to file "hx3_licence_XXXXXX.txt" - open it to view your serial numbers
* Revised boot sequence on unfinalized boards to prevent freezes
* HX3 Flash provides entering of "lost" licence numbers, will create licence info file "hx3_licence_*.txt" and update log file
* HX3 Flash Reboot bug fixed. HX3 board may be reset by power off/on if boot sequence fails
* LCD message for firmware update

<b>04/18/2016</b> Firmware #3.922, FPGA 11042016, ScanCores #23

* Do not use for drawbar Expander, Reverb button and Leslie control bugs introduced
* Fixed bug in "Button Vibrato" version (Drawbar Expander), vibrato LEDs did not change on presets
* Fixed "MIDI Volume" bug in Drawbar Expander, master volume did not change on MIDI CC (although displayed)
* Fixed "weaker lower manual volume" bug
* Separate TONE and AMP potentiometer enables
* "Latching Presets" firmware will now mute on CANCEL key, i.e. jump to preset 11
* Deeper bass pedal sound if pedal sustain off
* Slightly changed AO28 equalizing for more "bottom" and lower mids
* Slightly more generator output for full distortion on simulated rotary amp
* Wider swell pedal range
* Fixed "Note 25" bug on pedal scan routines
* MIDI Sustain by CC #64 introduced on all scan cores

<b>01/29/2016</b> Firmware #3.92, FPGA 27012016, ScanCores #22

* New filter and adder design, less prone to overflow distortions
* Higher bass and organ output levels, lowered rotary defaults parameter #607 to value 150
* New triode simulation in AO28 block - try the AO28 tube age parameter
* Added version for old XB2 mk2 kit. Rotary output jack and headphone amp must be rewired to obtain stereo simulation
* Fixed some bugs in beta FW: Menu entries, defaults saving, factory reset 
* Fixed rounding error on some parameters in MIDI custom CC set
* Extended transpose range plus/minus 2 octaves (FatarScan, MIDI input)
* Foldback for notes outside of 5 octaves keyboard range (FatarScan, MIDI input)
* Fixed MIDI channel bug, only worked on MIDI CH 1

<b>01/10/2016</b>Firmware #3.911

* Vibrato/Chorus display bugfix (XB2 kit only)
* Leakage/Output configuration bugfix (XB2 kit only)
* Corrected hx3_flash_config.ini for mk3/mk4 standard organs (affects Flash_OrganStandard_mk3_4.zip only)
* Added HX3 mk2 versions to firmware 3.91

<b>01/05/2016</b> Firmware #3.91, FPGA 01022016, HX3 Remote #3.91

* New rotor simulation, improved throb and woofer response
* Returned to full menus as some people do not have access to Windows PCs
* Sorted menus in a more convenient order
* Common Presets (available on organs only) save split point, split mode and Reverb/Config/Split tabs
* Added keyboard split options: Lower to Upper +1 or +2 octaves for single manual instruments (for MIDI/FATAR)
* Added parameter and menu for treble boost with Vibrato/Chorus ON
* Added "Tabs saved to Preset" ON/OFF menu entry, percussion and vibrato settings will be saved to upper/lower presets if ON
* Editable split point by menu
* Fixed missing entries in HX3 Remote MIDI Custom CCs (Vibrato etc)
* Fixed "scratching noise" when swell controlled by MIDI
* Cleaned up "Defaults Parameters" save, no longer partly saved to presets - distracted customers
* Added "Sustain via MIDI" feature to FATAR and XB2 ScanCore. "Sustain/Sostenuto via MIDI" available on MIDI ScanCore only.
* Returned to full menus as some people do not have access to Windows PCs
* Fixed a bug that updated user name to "Hans Wurst". Sorry about that!
* Fixed lots of minor bugs and glitches
* Updated HX3 Flash, may be "scripted" and customized by OEM/technicians for own organ projects
* Updated HX3 Remote, fixed some file export/import bugs

TO DO:

* Implementing improved split options in ScanCores for OrganScan61 and Scan16.
* Known bug in HX3 Remote: Sometimes issues an "invalid Integer" error on startup. Just ignore.

<b>12/23/2015</b> Firmware #3.90, FPGA 20122015, HX3 Remote #3.9, HX3 Flash #3.9

* Moved older firmwares to ARCHIVED_FIRMW directory
* Complete update ZIPs for most common HX3 instruments
* Last minor changes to Firmware #3.9
* Fixed several minor bugs in HX3 Remote and HX3 Flash
* Added "Reset File Info" in HX3 Remote to prevent missing files error
* OEM only: HX3 Flash now uses configuration file "hx3_flash_config.ini" which describes files and parameters to change/update. This text file may be customized by OEMs for their instruments and given to customers as complete package.
* OEM only: Added personal serial number file handling for production
* Leslie(R) default file name changed to "_rotary"
* "Master Volume" menu entry, affects all 4 output signals. Available by pressing encoder knob twice.
* MIDI ScanCore #20 provides +1 and +2 octave up of lower manual in upper manual split mode. Will be implemented in other scan cores soon.
* Emphasised "throb" in rotary horn simulation with FPGA #20122015
* Refined rotary modulation parameters. Those in FW #3.85 were a little low, resulting in a somewhat "flat" modulation.
* Less artefacts (see note below)
* Support for HX3 Drawbar Expander. In this firmware TONE pot analog input is mapped to MASTER VOLUME, otherwise it is compatible with HX3 standard firmware for board installations. TONE pot parameter is available as menu entry only.
* Deleted obsolete menu entries for standard firmware
* Rotary stops on front center position for both rotor and horn (phew! That was hard work...)
* "freewheel taper-off" effect when rotary stopped from slow or fast run
* Sostenuto/Sustain selection moved to MIDI CC set entries to make it available through menu system. 6 additional entries with "." will have sostenuto on MIDI CC #64 instead of sustain.

<b>12/04/2015</b> Firmware #3.851, FPGA 27112015, MIDI IN ScanCore #19

* Added "Sustain", "Sostenuto" and "All Notes Off" accepted MIDI commands, MIDI ScanCore #19 only!
* adjustable vibrato scanner gearing, param 488 in HX3 remote (located just before "Vib1 LC age")
* fixed unwanted "feature" in MIDI IN ScanCore #18. Sostenuto CC #66 robbed PERC ON in NI B4 CC set 
* instead, Sustain on CC #64 may be switched to Sostenuto functionality by HX3 Remote param 489 
* new MIDI ScanCore #19 compatible with older FW
* new HX3 Remote organ defaults file
* new FPGA 27112015, uses 16x oversampling
* improved overflow behaviour in busbar adders, somewhat louder bass pedal
* less prone to overflow distortions on loud tapering settings
* higher audio output level on rotary simulation
* rotary simluation delay lines now with 16x oversampling rate, should result in less modulation artefacts
* revised rotary params in firmware
* Simplified "Leslie" default parameters in HX3 Remote
* fixed minor "no VibKnob save on preset 0" bug in MIDI Expander firmware

<b>10/23/2015</b> ScanCore #18 for XB2

* Fixed Split bug, split did not work on #17. Just replace XB2 ScanCore in HX3 Remote.

<b>10/16/2015</b> Firmware #3.841, FPGA #16102015

* Fixed annoying "ticker noise when keys released" bug in vibrato
* Changed reverb algorithm, improved level adjustment
* Reduced granular switching noise in new vibrato
* Reduced Dry/Mix amount
* Raised Bass pedal level by 50%, slightly reduced harmonic content

<b>10/09/2015</b> Firmware #3.84, FPGA #09102015

* Completely re-written scanner vibrato and scanner capacitor blending
* May need some Chorus Dry/Wet and Age param tweaking to your taste
* Bugfix in HX3_tapering.exe concerning "Save All" function, will regard individual level scaling now
* Updated XB2 firmware (HX3 mk3/mk4 only)
* Please update AVR firmware <b>and</b> FPGA

<b>09/04/2015</b> Firmware #3.83c, new tapering

* updated HX3 Remote and HX3 Flash to Windows 8/10 compatility
* new rotary horn FIR filter coeffs for less peaks
* corrected taper_levels files, old tapering tends to overflow distortion
* adjusted output levels for each taperlevels file

<b>08/28/2015</b> Firmware #3.83c

* backup for licence numbers if corrupted EEPROM
* added a warning if HX3 is not finalized, for more reliable update with HX3 Flash on HX3 board installations
* HX3 will not work if not finalized to prevent incomplete updates
* refined lower manual drawbar log curve
* fixed bug in MAG organs firmware (pedal output)
* new optimized tapering files - more punch, less peaks
* more volume on pedal bass 16'
* improvements for HX3 Remote and HX3 Flash
* removed unneccessary messages from HX3 Remote
* Alternate  drawbar set select signal for particular preset number, Parameter 483 in Organ Defaults. HX3 will switch to alternate drawbar set when prset number in parameter 483 is active.
* Single Preset16 is not splitted to 8/8 configuration for upper/lower manual if parameter 484 is "on". All 16 presets are available for upper manual.
* OEMs only: Added production programming for DIAMEX ISP programmer ("Advanced" tab) in HX3 Remote

<b>07/24/2015</b> Firmware #3.822, HX3 Remote #3.82

* Fixed a bug in HX3 Remote, lost licences when updating firmware
* HX3 Flash minor changes for reliability

<b>07/09/2015</b> Firmware #3.822, FPGA #05072015, ScanCores #17

From firmware 3.82 and up, HX3 will not send own MIDI CCs on MIDI OUT when MIDI Option = 3 (RcvSndMgNoCC). 
MIDI Option = 3 is now default on all firmwares except HX3 Expander (which has to accept MIDI CCs). 
This change has been made since the MIDI CCs HX3 sends out may disturb connected MIDI workstations/arrangers.
Note: If send/receive of MIDI CCs is enabled (Option = 1 or 2), 
HX3 will transmit its own CCs (drawbars etc.) always according to NI B4 set, 
independent from selected MIDI CC interpreter. 

Independent from MIDI option selected, HX3 will always send a 3.3V TTL level MIDI signal on 
PL16 pin 8 for controlling Ventilator/Minivent DSP board with synced stop/slow/fast.
Pin 34 of Vent DSP board is MIDI TTL input. Also wire digital ground (PL16 pin 10). 
Ventilator DSP accepts MIDI CC #21 values 0 (stop), 1 (slow), 2 (fast) on channel 1.

* New HX3 Flash application - simple no-hassle updater for mk3 and mk4 boards (public beta)
* Fixed bass pedal drawbar bug on some MIDI CC sets due to flaw in ScanCores
* Fixed erraneous display/saving of AudioJ Conf A/B
* Fixed Percussion mute bug on presets 1..15
* Modified MIDI Option = RcvSndMgNoCC behaviour (see above)
* HX3 now sends MIDI CC #1 and #44 for rotary footswitch when MIDI Option = 1 or 2
* RcvSndMgNoCC option is now default on HX3 firmwares except for HX3 Expander
* Added MIDI CCs for Hamichord/Mojo CC set:
* > #1 = Rotary Slow/Stop/Fast (modulation wheel),
* > #91 = TG Leakage (is "Crosstalk" knob on Mojo), 
* > #92 = TG Cap set (is "Keyclick Length" knob on Mojo), 
* > #95 = Swell Trim Cap (is "Percussion Volume" knob on Mojo)
* Additional TTL MIDI output for controlling Ventilator/Minivent DSP board (see above)

<b>06/29/2015</b> Firmware #3.812, FPGA #29062015

* Linear display mapping (MIDI as well as analog drawbar input) to better match the drawbar numbering
* Drawbar loudness logarithmisation to fit B3 drawbar curve
* Potentiometer/drawbar input hysteresis changed
* Improved V2/V3 vibrato and LC line box "Age" parameter range

<b>06/24/2015</b> Firmware #3.81

* fixed distortions when playing full chord in upper octave (please update FPGA also, use fpga_25042015.bit, installs new TG tapering files)
* fixed missing percussion bug after common preset save
* improved potentiometer/drawbar hysteresis for noise-free operation
* minor changes to HX3 Remote to prevent loss of licence numbers

<b>04/27/2015</b> Firmware #3.806, FPGA #25042015

* Improved reproduction of upper notes leakage
* Pedal added to rotary simulation instead of plain output on "+B" audio configs

<b>03/10/2015</b> Firmware #3.74, FPGA #1003015, HX3 Remote #3.74, ScanCores #16

* Working copy for evaluation - not final!
* Common Presets save current keyboard split mode and split point
* Binary combinations of Common Presets allowed (pressing two or more preset buttons at one time)
* 4 TG capacitor sets from 1955 to 1972 plus "Recapped" (more aggressive)

* Not fixed yet: Display of output configurations A/B may be erraneous

<b>01/10/2015</b> Firmware #3.72, FPGA #09012015, HX3 Remote #3.7, ScanCores #14

* Some changes in Hammond MIDI CC set for XK3c (relocated reverb and lower vibrato ON buttons), see HX3 Expander User Manual (directory DOCS_PDF) for details.
* Fixed Bug in ScanCores OrganScan61 and Strip16, Bass Split was not working
* Fixed small bug in percussion drawbar muting (#3.721)
* Fixed bug in common presets assignment
* Fixed bug in single drawbar versions which prevented pots AmpVol and TonePot from working
* Several menu entries no longer skipped on non-Expander versions
* FPGA #09012015 with appropriate level adjustment for Bass on Leslie signal
* Streamlined firmware to fit into 60 kByte; firmware 3.63 update did not work due to memory overlap
* Auto-Restore feature for Licence numbers in HX3 Remote 3.7
* Common Presets save Percussion/Vibrato/Efx tab settings and Upper/Lower Preset numbers (default 1..4)
* Manual presets only save drawbar settings on HX3 standard firmware; Expander and single drawbar versions save tabs on presets
* Added repair program (ZIP archive) to recover non-working HX3 to usable condition

<b>10/22/2014</b> Firmware #3.62

* Please Note: #3.6x update procedure did not work due to memory overlap
* Changed directory structure on Github repo, all files available as packed ZIP for easy download 
* Revised swell curve with more accurate frequency response on FW 3.63
* Adjustable minimal swell volume down to zero by menu or parameter 482 (see HX3 Remote). Needs FPGA configuration #22102014 and, if applicable, HX3 Remote 3.63 
* AO28 amplifier noise without digital artefacts

<b>06/13/2014</b> Firmware #3.55 

* New HX3 Remote with improved MIDI CC assignment. In conjunction with firmware 3.55, it will display and select received MIDI CCs for easier assignment of custom MIDI CC sets.
* MIDI Route-Thru to HX3 Remote. Small bug fixed in Voce MIDI CC setup, added controllers 87 (Treble Equ/Tone) and 88 (Bass Equ).

<b>06/04/2014</b> 

* Fixed small bug in ScanCores which would have shown up later
* Added FIR Upload to HX Remote
* Added ScanCore for Scan16, 61 Keys

<b>05/28/2014</b>

* Added FPGA #28052014 with better treble response on Leslie sim
* HX3 Remote had a small bug in "Write Basics" function that transmitted "1" instead of "255" value with Booleans (Enables etc.) of value "true".  Fixed with version 1.09 (online).
* Fixed small bug in HX3 firmware that prevented saving of Amp122 resp. Leslie Volume Pot Enable by MenuPanel.

<b>05/20/2014</b>

* Bugfix on HX_remote.exe, organ param list, last parameter Amp122 Volume Enable was missing

<b>05/19/2014</b>

* Bugfix on HX_remote.exe, EEPROM programming was faulty
* Bugfix on FPGA configuration, fixed sporadic crackling noise on right Leslie channel
* Experimental custom MIDI CC set, editor added to HX3_remote

<b>05/01/2014</b>

* Stereo Leslie simulation with improved modulation
* New vibrato algorithm with delay line "aging" parameter
* Pedal is fully polyphonic with "dry" original sound or "Trek II string bass". Last note played fades out
* Output jacks are mono on new board, but configurable by menu parameter, i.e. you may get organ, amp122 sim, pedal or leslie L/R on any jack. Separate jack extension board (or plug "rings" on HX3 mk2) carries "other" signals
* Lower octave foldback is configurable by menu parameter: Foldback with full level, foldback with muted level, no foldback ("all way down") with full level or muted level
* Reverb amount may be adjusted for each of three tab settings separately
* Bass and Treble tone controls have wider range 
* Virtual key contacts have "mutual resistance" now which yields a more "decent" click response
* New remote parameters 400..481 directly access 81 params like menu selection by MenuPanel
* Deleted obsolete remote params 500..563 despite some for compatibility (519..524)

### Files

Flash files for serial upload via AVRdude or HX3 Remote. Each .HEX file has a corresponding .EEP file. Versions for mk2 
and mk3 version boards are in separate ZIP archives. Please update only the file appropriate for your product. 
<b>Note:</b> For operation with firmware 3.5 and up, remove jumpers JP7 and JP8 which may still sit on your board from 
factory programming. These jumpers are only required for updating the reverb DSP (no need to update unless noted).

<b>HX3mkX_std.hex</b> Standard version, mainboard with button presets, Preset12 or Preset16<br>
<b>HX3mkX_expander.hex</b> MIDI expander box version<br>
<b>HX3mkX_latching.hex</b> Mainboard with latching presets on Preset12<br>
<b>HX3mkX_preset24.hex</b> Mainboard with presets on external Preset24<br>
<b>HX3mkX_mag.hex</b> Special version for MAG custom organs<br>
<b>HX3mkX_single.hex</b> Mainboard with button presets or Preset16, single manual drawbar assignment<br>
<b>HX3mkX_single_bv.hex</b> Mainboard with button presets or Preset16, single manual drawbar assignment, button vibrato on Panel16<br>
<b>HX3mk3_xb2.hex</b> HX3 Retrofit Kit for XB2 (mk3 only)<br>

<b>HX_xxx.dat</b>  Scan cores for different scan boards or MIDI input<br>
<b>fpga_DDMMYYY.bit</b>  FPGA configuration (Sound Engine), creation date (version) encoded DDMMYYYY<br>
<b>dsp_rev.bin</b>  Spin-FV1 Reverb DSP program<br>

<b>HX3_avr_repair.ZIP</b>  Repair tool (command line batch) to restore corrupted firmware - see README in archive<br>

Please also regard installation instructions on http://wiki.keyboardpartner.de!

AdaBoot by Adafruit, modified for ATmega644P(A)06/2012 by Carsten Meyer, cm@ct.de
