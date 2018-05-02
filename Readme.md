# What is this project? [](@description Pitch/Intro of the project)

This project has a specific target of providing a __low-cost, open source technological kit to allow scientists, academics, hackers, makers or OSHW fans to hack their way to ultrasound imaging__ - below 500$ - at home, with no specific equipment required. For complementary sources of information, you can visit:

* the [github repo](https://github.com/kelu124/echomods/), for the source files, raw data and raw experiment logs;
* the [online manual/book](https://www.gitbook.com/book/kelu124/echomods/details) for a easily readable and searchable archive of the whole work;
* the [hackaday page](https://hackaday.io/project/9281-murgen-open-source-ultrasound-imaging), where I tried to blog day-to-day experiments in a casual format;
* an [article summarizing the experiment on the Journal of Open Hardware](http://openhardware.metajnl.com/articles/10.5334/joh.2/) - [DOI:10.5334/joh.2]( http://doi.org/10.5334/joh.2);
* the [slack channel if you want to discuss](https://join.slack.com/usdevkit/shared_invite/MTkxODU5MjU0NjI1LTE0OTY1ODgxMDEtMmYyZTliZDBlZA);
* the Tindie store for the [analog processing unit](https://www.tindie.com/products/kelu124/ultrasound-imaging-analog-processing-module/) and the [pulser](https://www.tindie.com/products/kelu124/ultrasound-imaging-pulser-module/) or [the motherboard](https://www.tindie.com/products/kelu124/ultrasound-modules-motherboard/).

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.377054.svg)](https://doi.org/10.5281/zenodo.377054)

* __Disclaimer #0__: __This is not a medical ultrasound scanner__! It's a development kit that can be used for pedagogical and academic purposes - possible immediate use as a non-destructive testing (NDT) tool, for example in metallurgical crack analysis. As in all electronics, be [careful](/WordOfCaution.md).
* __Disclaimer #1__: though an engineer, this project is the first of its sort, I never did something related. It's all but a finalized product.
* __Disclaimer #2__: Ultrasound raises questions. In case you build a scanner, use caution and good sense!
* __Disclaimer #3__: This project is not part of echopen.



## What are the arduino-like ultrasound module ?

__Creating modules to facilitate ultrasound hacking__ : the principles of the echOmods is to enable a full chain of ultrasound image processing and hardware control.

We have chosen to use a module approach to make sure that each key component inside ultrasound image processing can easily be replaced and compared with another module, while providing logical _logic blocks_ and corresponding interfaces for these modules to communicate. There's a module for [high-voltage pulsing](/retired/tobo/), one for the [transducer](/retroATL3/), one for the [analog processing](/goblin/), one for [data acquisiton](/retired/toadkiller/), ... and many more!

## What images does it give ?

![](/elmo/data/arduinoffset/LineImageEnveloppe.jpg)

## What does it look like?

The modules sit on a breadboard, and communicate through the tracks laying below. The configuration represented below show the Basic dev kit.

![](/doj/images/doj_v2_notes.jpg)

and used in a wider context:

![](/elmo/data/arduino/setup.png)

# What does it cost?

##  Raspberry Dev Kit

Using a simpler linux-enabled controler (the all-powerful Pi in its RPi 0 or Pi W) for the dev kit. Cost of materials aims at being as low as possible, below the 500$.


* Simply the servo and transducer module ([cletus](/cletus/)) -- get for _80$_ (Where? Recycling a transducer from ebay, servo from anywhere ([Amazon?](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Dtoys-and-games&field-keywords=%22SG90+9G%22)))
* The Pi Heart of the echOmods ([tomtom](/tomtom/)) -- get for _10$_ (Where?  Get the Pi W from [plenty of sources](https://www.raspberrypi.org/products/pi-zero-w/))
* Using a dual ADC raspberry pHAT for 20Msps+ acquisition ([elmo](/elmo/)) -- get for _75$_ (Where? OSHPark, MacroFab, Tindie)
* Goblin: a TGC-Envelop-ADC module ([goblin](/goblin/)) -- get for _149$_ (Where? Custom made, get the [Gerbers](/goblin/source/), or [buy it preassembled on Tindie](https://www.tindie.com/products/kelu124/ultrasound-imaging-analog-processing-module/), or contact @kelu124)
* Tobo: the HV-pulser ([tobo](/tobo/)) -- get for _120$_ (Where? Custom made, get the [Gerbers](/retired/tobo/source/), [buy it preassembled on tindie](https://www.tindie.com/products/kelu124/ultrasound-imaging-pulser-module/) or contact @kelu124)


_Total cost of the set: 434$_

##  echOmods emulated

uC pings emulator and streams feedback


* This is the module which emulates the signal coming from the analog processing chain. ([silent](/silent/)) -- get for _35$_ (Where? Get from [Adafruit](https://www.adafruit.com/products/3056))
* The acquisition heart of the echOmods ([croaker](/croaker/)) -- get for _35$_ (Where? Get Feather from [Amz](http://amzn.to/2eGzlbG ) or [Adafruit](https://www.adafruit.com/products/3056). [OLED at Amz](http://amzn.to/2gi0vHl))
* Mogaba, the power supply ([mogaba](/mogaba/)) -- get for _5$_ (Where? Anywhere, or eg [Amazon?](https://www.amazon.com/s/ref=nb_sb_noss?url=node%3D667846011&field-keywords=3.3V+5V+Power+Supply+Module+Breadboard+))
* The motherboard of the echomods ([doj](/doj/)) -- get for _5$_ (Where? Anywhere for [stripboard](https://www.amazon.com/s/ref=nb_sb_noss_2?url=node%3D667846011&field-keywords=stripboard&rh=n%3A667846011%2Ck%3Astripboard). Or PCB from [OSHPark](https://oshpark.com/shared_projects/2taE6p4M) if you can order by 3. Or [straight from Tindie](https://www.tindie.com/products/kelu124/ultrasound-modules-motherboard/).)
* Goblin: a TGC-Envelop-ADC module ([goblin](/goblin/)) -- get for _149$_ (Where? Custom made, get the [Gerbers](/goblin/source/), or [buy it preassembled on Tindie](https://www.tindie.com/products/kelu124/ultrasound-imaging-analog-processing-module/), or contact @kelu124)


_Total cost of the set: 229$_

##  Wireless Dev Kit

The default setting for the sets


* Simply the servo and transducer module ([cletus](/cletus/)) -- get for _80$_ (Where? Recycling a transducer from ebay, servo from anywhere ([Amazon?](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Dtoys-and-games&field-keywords=%22SG90+9G%22)))
* The acquisition heart of the echOmods ([croaker](/croaker/)) -- get for _35$_ (Where? Get Feather from [Amz](http://amzn.to/2eGzlbG ) or [Adafruit](https://www.adafruit.com/products/3056). [OLED at Amz](http://amzn.to/2gi0vHl))
* Mogaba, the power supply ([mogaba](/mogaba/)) -- get for _5$_ (Where? Anywhere, or eg [Amazon?](https://www.amazon.com/s/ref=nb_sb_noss?url=node%3D667846011&field-keywords=3.3V+5V+Power+Supply+Module+Breadboard+))
* Goblin: a TGC-Envelop-ADC module ([goblin](/goblin/)) -- get for _149$_ (Where? Custom made, get the [Gerbers](/goblin/source/), or [buy it preassembled on Tindie](https://www.tindie.com/products/kelu124/ultrasound-imaging-analog-processing-module/), or contact @kelu124)
* Tobo: the HV-pulser ([tobo](/tobo/)) -- get for _120$_ (Where? Custom made, get the [Gerbers](/retired/tobo/source/), [buy it preassembled on tindie](https://www.tindie.com/products/kelu124/ultrasound-imaging-pulser-module/) or contact @kelu124)


_Total cost of the set: 389$_

##  The Beaglebone version, along with an hacked probe

Some stuff, unexpensive to buy, to build a ultrasound testing kit, totalling less than _500$_.


* Retrohacking the ATL Access 3 probe ([retroATL3](/retroATL3/)) -- get for _75$_ (Where? Recycling a probe from [ebay](http://www.ebay.fr/sch/i.html?_odkw=%22atl+access%22+probe&_osacat=0&_from=R40&_trksid=p2045573.m570.l1313.TR0.TRC0.H0.X%22atl+access%22+.TRS0&_nkw=%22atl+access%22+&_sacat=0))
* This is the module to get high-speed (40Msps) signal acquisition. ([toadkiller](/toadkiller/)) -- get for _79$_ (Where?  A bundle at 169$ from [Groupgets](https://groupgets.com/manufacturers/getlab/products/prudaq) or as a [standalone](https://store.groupgets.com/#!/p/68936091) at 79$ )
* Mogaba, the power supply ([mogaba](/mogaba/)) -- get for _5$_ (Where? Anywhere, or eg [Amazon?](https://www.amazon.com/s/ref=nb_sb_noss?url=node%3D667846011&field-keywords=3.3V+5V+Power+Supply+Module+Breadboard+))
* Goblin: a TGC-Envelop-ADC module ([goblin](/goblin/)) -- get for _149$_ (Where? Custom made, get the [Gerbers](/goblin/source/), or [buy it preassembled on Tindie](https://www.tindie.com/products/kelu124/ultrasound-imaging-analog-processing-module/), or contact @kelu124)
* Tobo: the HV-pulser ([tobo](/tobo/)) -- get for _120$_ (Where? Custom made, get the [Gerbers](/retired/tobo/source/), [buy it preassembled on tindie](https://www.tindie.com/products/kelu124/ultrasound-imaging-pulser-module/) or contact @kelu124)
* The motherboard of the echomods ([doj](/doj/)) -- get for _5$_ (Where? Anywhere for [stripboard](https://www.amazon.com/s/ref=nb_sb_noss_2?url=node%3D667846011&field-keywords=stripboard&rh=n%3A667846011%2Ck%3Astripboard). Or PCB from [OSHPark](https://oshpark.com/shared_projects/2taE6p4M) if you can order by 3. Or [straight from Tindie](https://www.tindie.com/products/kelu124/ultrasound-modules-motherboard/).)
* One-eye, the controler ([oneeye](/oneeye/)) -- get for _10$_ (Where? from [Adafruit](https://www.adafruit.com/product/2000))


_Total cost of the set: 443$_




## Ultrasound hardware structure

[](@description Short description of the organization of modules)

To produce an image, the modules have to create a [high voltage pulse](/retired/tobo/), which excites a [transducer](/retroATL3/). Echoes coming from the body are amplified using a [TGC + LNA](/goblin/), which cleans the analog signal, which itself [gets digitalized](/retired/toadkiller/). 

The diagram is represented below:

![](/include/images/blockdiagram.gif)




# The modules organization 

![Graph](/include/sets/basic.png) 

# A recap of our modules 


| ThumbnailImage | Name | In | Out |
|------|-------|----|------|
|<img src='https://github.com/kelu124/echomods/blob/master/wirephantom/viewme.png' align='center' width='150'>|**[wirephantom](/wirephantom/Readme.md)**: Just a phantom for calibrated signals|<ul><li>na</li></ul>|<ul><li>na</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/elmo/viewme.png' align='center' width='150'>|**[elmo](/elmo/Readme.md)**: The aim of this module is to achieve 20Msps, at 9bits or more. |<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-19_3.3V</li><li>ITF-12_RPIn</li></ul>|<ul><li>Signal Digitalized</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/doj/viewme.png' align='center' width='150'>|**[doj](/doj/Readme.md)**: Getting a motherboard: that's fitting all the modules in an easy way, with an easy access to all tracks. See this for the Kicad files.|||
|<img src='https://github.com/kelu124/echomods/blob/master/matty/viewme.png' align='center' width='150'>|**[matty](/matty/Readme.md)**: The aim is to summarize all modules in a all-inclusive board. Fast ADC, good load of memory, good SNR.. the not-so-DIY module, as it comes already assembled with nothing to do =)|||
|<img src='https://github.com/kelu124/echomods/blob/master/retroATL3/viewme.png' align='center' width='150'>|**[retroATL3](/retroATL3/Readme.md)**: The aim of this echOmod is to get the mechanical movement of the piezos. Salvaged from a former ATL3.|<ul><li>ITF-A_gnd</li><li>ITF-F_12V</li><li>ITF-N_cc_motor_pwm</li><li>ITF-mET_Transducer</li><li>Motor</li><li>Tri-Piezo Head</li></ul>|<ul><li>Motor</li><li>ITF-mET_Transducer</li><li>Tri-Piezo Head</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/goblin/viewme.png' align='center' width='150'>|**[goblin](/goblin/Readme.md)**: The aim of this echOmod is to get the signal coming back from a transducer, and to deliver the signal, analogically processed, with all steps accessible to hackers. |<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-7_GAIN</li><li>ITF-4_RawSig</li><li>ITF-3_ENV</li><li>ITF-18_Raw</li><li>ITF-mET_SMA</li></ul>|<ul><li>ITF-4_RawSig</li><li>ITF-3_ENV_signal_envelope</li><li>ITF-mEG_SPI</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/lite.tbo/viewme.png' align='center' width='150'>|**[lite.tbo](/lite.tbo/Readme.md)**: The aim of this echOmod is to get the HV Pulse done.|<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-9_Pon</li><li>ITF-10_Poff</li><li>ITF-19_3.3V</li><li>ITF-mET_Transducer</li></ul>|<ul><li>ITF-18_Raw</li><li>ITF-mET_SMA</li><li>ITF-mET_Transducer</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/silent/viewme.png' align='center' width='150'>|**[silent](/silent/Readme.md)**: The aim of this echOmod is to simulate a raw signal that would come from the piezo and analog chain.|<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-17_POff3</li></ul>|<ul><li>ITF-18_Raw</li></ul>|


# Experiments

 * 2016-08-09: [Goblin tests](/include/experiments/auto/20160809a.md): Testing the goblin board with the silent emulator. _(20160809a)_
 * 2016-08-14: [RPi](/include/experiments/auto/20160814a.md): Testing the acquisition with the BeagleBone DAQ. _(20160814a)_
 * 2016-08-22: [BBB+Probe](/include/experiments/auto/20160822a.md): Images acquired from a BeagleBone black with a probe _(20160822a)_
 * 2016-12-17: [Croaker](/include/experiments/auto/20161217a.md): Testing the acquisition with the croaker module. _(20161217a)_
 * 2017-06-11: [Croaker](/include/experiments/auto/20170611a.md): Testing the acquisition with the croaker module. _(20170611a)_
 * 2017-07-13: [Elmo](/include/experiments/auto/20170713a.md): Testing the new DAQ with two ADCs. _(20170713a)_
 * 2017-07-15: [RetroATL3 acquisition](/include/experiments/auto/20170715a.md): Getting an image from the retroATL3 probe. _(20170715a)_
 * 2017-09-30: [Alt.tbo](/include/experiments/auto/20170930a.md): Testing new pulser again 1/4 _(20170930a)_
 * 2017-10-01: [Alt.tbo](/include/experiments/auto/20171001a.md): Testing new pulser again 2/4 _(20171001a)_
 * 2017-10-01: [Alt.tbo](/include/experiments/auto/20171001b.md): Testing new pulser again 3/4 _(20171001b)_
 * 2017-11-11: [Alt.tbo](/include/experiments/auto/20171111a.md): Testing new pulser again 4/4 _(20171111a)_
 * 2017-11-12: [Probe](/include/experiments/auto/20171112a.md): Testing new probe with new pulser _(20171112a)_
 * 2017-11-24: [Impedance matching](/include/experiments/auto/20171124a.md): Doing some tests for impedance matching. _(20171124a)_
 * 2018-01-03: [Felix experiment](/include/experiments/auto/20180103a.md): Testing Felix setup with previous Bomanz module. _(20180103a)_
 * 2018-01-15: [Matty](/include/experiments/auto/20180115a.md): Receiving the first matty. _(20180115a)_
 * 2018-02-16: [Alt.tbo and Elmo](/include/experiments/auto/20180216a.md): Testing alt.tbo and elmo new boards. _(20180216a)_
 * 2018-02-17: [Alt.tbo and Elmo](/include/experiments/auto/20180217a.md): Testing alt.tbo and elmo new boards for pulser issues (there is not positive and negative pulse, only goes in direction). _(20180217a)_
 * 2018-02-24: [Matty speed tests](/include/experiments/auto/20180224a.md): Testing matty s acquisition at different speed, 12Msps to 24Msps. _(20180224a)_
 * 2018-02-24: [Matty Gain](/include/experiments/auto/20180224b.md): Testing matty's fixed gain settings. _(20180224b)_
 * 2018-02-25: [Matty and RetroATL3](/include/experiments/auto/20180225a.md): Acquisition of a probe image with matty. _(20180225a)_
 * 2018-03-10: [Matty DAQ](/include/experiments/auto/20180310a.md): testing the programmation of matty DAC control for the TGC. _(20180310a)_
 * 2018-04-03: [Voltage checks](/include/experiments/auto/20180403a.md): Testing matty at different voltages. _(20180403a)_
 * 2018-04-03: [Matty TGC test](/include/experiments/auto/20180403b.md): Testing matty 's TGC, including playing with the gain DAC and pulse control. _(20180403b)_
 * 2018-04-03: [Tomas first acq](/include/experiments/auto/20180403t.md): Tomas, a user, is getting a first image from a NDT setup with a block of steel. _(20180403t)_
 * 2018-04-15: [Test of new batch 1/2](/include/experiments/auto/20180415a.md): Testing the goblin board with silent, then test of the new lite.tbo pulser with a piezo. _(20180415a)_
 * 2018-04-15: [Test of new batch 2/2](/include/experiments/auto/20180415r.md): Testing the lite.tbo, goblin and elmo boards done at the fab - on a doj v2 motherboard. _(20180415r)_
 * [20180417a](/include/experiments/auto/20180417a.md)
 * 2018-04-30: [JSON and Servo](/include/experiments/auto/20180430a.md): Better file management and servo control using Matty. _(20180430a)_


# Progress on building the modules 


## Module-wise 


Note that the 'BONUS!' represents something that _could_ be done, and does not count as a strict TODO.


| Name of module | ToDo | Done |  Progress |
|------|-------|----|-----|
|wirephantom|<ul><li>None</li></ul>|<ul><li>All</li></ul>|50% |
|elmo|<ul><li>None</li></ul>|<ul><li>Write the <a href="/elmo/QuickStart.md">Quickstart</a></li><li>Getting a board an soldering some ADCs</li><li>Understand GPIO <a href="/elmo/data/20170609-NewADC.ipynb">mem mapping</a></li><li>Get raw data with <a href="/elmo/data/arduinoffset/20170612-ArduinoFFTed.ipynb">offset vref/2</a></li><li>Tests with a single ADC at 11Msps</li><li>Produce a batch of <a href="/elmo/source/v2/elmov2_altium.zip">rev2 elmo</a></li></ul>|85% |
|doj||<ul><li><a href="https://oshpark.com/shared_projects/2taE6p4M">PCB on OSHPark</a></li><li>Having the list of strips accessible</li><li>Design</li><li>Change the viewme</li><li>Assemble it</li><li>Test it</li><li>Adapt power supply from v2 - smaller board footprint</li><li>Add a level shifter been Pon 3.3 and 5 and Poff 3.3 and 5</li><li>A bit more space around the Pi0/PiW headers</li><li>Proper silkscreening around the Pi0 headers (they are reversed)</li><li>Jumper for the ADC in.. and selector (enveloppe and amplified signal) (either to Feather or to ADC .. and dedicated pin on Rpi)</li><li>SPI from RPi to Oled... or SPI to screen (to be checked in both case) .. or both kept, there are two SPI</li></ul>|100% |
|matty|<ul><li>See the <a href="/matty/nextsteps.md">next steps</a></li><li>Having it work with a <a href="/retroATL3/">retroATL3</a></li></ul>|<ul><li>Getting some signals!</li></ul>|33% |
|retroATL3|<ul><li>See the <a href="/matty/nextsteps.md">next steps</a></li><li>Having it work with a <a href="/retroATL3/">retroATL3</a></li></ul>|<ul><li><em>BONUS!</em> Get RealTime acquisition</li><li>Finding the pins mapping</li><li>Acquire and build ultrasound pictures =)</li><li>Motor in action</li><li>Refill Oil</li><li>Test echoes</li><li><a href="https://hackaday.io/project/9281-murgen-open-source-ultrasound-imaging/log/42113-testing-murgen-with-a-market-probe">Make and insert a video: there</a></li></ul>|77% |
|goblin|<ul><li>Test Goblin v2</li></ul>|<ul><li>Check the power consumption</li><li><a href="/retired/toadkiller/data/test_enveloppe/">Testing the in and out signals</a> of the board with the prudaq.</li><li>Specs to write</li><li>Agreeing on the strips </li><li>Check if 5V and 3.3V are stable</li><li>Defining the ICs to use</li><li>Getting schematics</li><li>Send microcircuits to Edgeflex</li><li>Receive the module</li><li>Publish the sources in KiCAD (@Sofian maybe?)</li><li>CANCELLED - Test it with the <a href="/retired/hannin/">EMW3165</a></li><li>Plug it to a <a href="/elmo/">RPi0</a> or <a href="/retired/toadkiller/">BBB</a> or <a href="/retired/croaker/">STM32</a></li><li>Connect the ADC to a RPi0</li></ul>|92% |
|lite.tbo|<ul><li>Review a bipolar design (originally alt.tbo -- but double the components and hence the price)</li></ul>|<ul><li>Preliminary testing</li></ul>|50% |
|silent||<ul><li>Feather: <a href="/silent/software/featherWICED/SignalGenerator.ino">work with an interrupt</a></li><li>Write code for feather WICED</li><li>Publish this code</li><li>Remove Signal Bias</li><li>Validated with a Feather WICED (<a href="/silent/software/featherWICED/SimpleSignalGenerator.ino">code</a>).</li><li>Feather: remove the average value before inputing in Goblin</li><li><a href="/silent/2016-08-09-SilentPlusTobo.md">Check output with Goblin</a></li></ul>|100% |


## Shopping list

Here's a couple of things we're working on, for which you could help as well.

* Boosting the [6Msps croaker](/retired/croaker/) acquisition (see Wayne?) to the full 6Msps 

### Todos from Modules
* None (in [wirephantom](/wirephantom/))
* See the <a href="/matty/nextsteps.md">next steps</a> (in [matty](/matty/))
* Having it work with a <a href="/retroATL3/">retroATL3</a> (in [matty](/matty/))
* Test Goblin v2 (in [goblin](/goblin/))
* Review a bipolar design (originally alt.tbo -- but double the components and hence the price) (in [lite.tbo](/lite.tbo/))


### Todos from worklog
* add Visa, possibly Pouya and Thomas as contributors
* map interested (green) 
* Add a documentation server
* Display IP on the OLED.
* Need to have a look at this RPI GPIO DMA - https://github.com/hzeller/rpi-gpio-dma-demo
* Include some cletus remarks (sourcing) on gitbook
* add some ideas for [the pulser](https://electronics.stackexchange.com/questions/212667/ultrasound-transducer-excitation-frequency-transistor-type?rq=1) to the alt.pulser board
* remove gitbook MD files from the log
* link to files in the log (python)
* Main readme as TPL
* test some compressed sensing using [golay codes](/include/20170325/PulseCode.pdf) on a single element piezo
* _senjak_ 15:07 In Which a PDF is a Git Repository Containing its own Latex Source and a Copy of Itself -- https://github.com/ESultanik/PDFGitPolyglot/blob/master/make_polyglot.sh
* 20171111a and 20171112b Readmes
* impedance matching -- [see more](/include/impedance/ipm.pdf) -- Butterworth-Van-Dyke or [here](https://electronics.stackexchange.com/questions/245915/picking-source-resistance-for-impedance-matching). [Tuning Filter](https://i.stack.imgur.com/96XMb.png).
* list other initiatives
* classifier articles with link Article: =)
* a page sumarizing the experiments (as in the __Experiments__ page in the gitbook)
* Brainstorm for @senjak information design:
* un0rick site to have plenty of stuff
 * Publish first drafts on un0rick GH / GH-pages / gitbook
* create v2 release once gob.v2 and corrected/working alt.tbo v2 are ready.
* use [General Design Procedure for Free and Open-Source Hardware for Scientific Equipment](http://www.mdpi.com/2411-9660/2/1/2/htm) as a reference
* compare [old pulser](/retired/alt.tbo/20171111a/20171111-pulses.ipynb) (pulser) and [new acs](/matty/20180224b/20180221b-Client.ipynb) for matty readme
 * for matty [Rip this intro?](https://qspace.library.queensu.ca/bitstream/handle/1974/6235/Wall_Kieran_A_201012_PhD.pdf?sequence=1&isAllowed=y)
* clean all repos for a v2 release of modules 
 * decrypt the connector =)
 * Script to check IMGs URL matches path
 * reorganise
Loved Nasa: add to un0rick
* change path of images when they have changed
* Create detailed pages for the community in the gitbook
* Create detailed pages for each probe [I've played with](/include/probes/Readme.md) in the gitbook
* add dp location
* listing experiments of others
* before reclean full repo, create release "Full Dev Resources" and get corresponding version (v1.9 + hash)!
 * : Add Full GitBook PDF to it before
* Sort the list of experiments, shortnames in SUMMARY
* Community: list the contributors in a page + add the experiment. Individual page to point to experiment.
* Page on documentation
* Edit [history](https://kelu124.gitbooks.io/echomods/content/Chapter1/history.html) page to add Matty.
* Rewrite the Chapters Readme -> "This chapter is dedicated to the brain_dumps "
* Do a Doj (LOW PRIORITY)
* Redo a usable alt.tbo (LOW PRIORITY)
* Clean Modules list (keep lite.tbo, goblin, cletus, doj, elmo, matty) + add "CNprobe"
 * Make 7 clean QuickStarts for remaining modules // copy them on Tindie.
 * Get "ShortNames" in JSON
* Put alt.tbo, tobo, loftus, tomtom, croaker, retroATL3 and wirephantom in retired modules + add "PU3090" phantoms in retired
* Remove sets in doc
* Remake homepage in autodoc
* Clean obsolete versions in repos
* contact the [author](https://repository.tudelft.nl/islandora/object/uuid%3A8784cc2b-10a1-47e7-a87f-ce25062d456f) !




# A recap of our retired modules 


| ThumbnailImage | Name | In | Out |
|------|-------|----|------|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/sleepy/viewme.png' align='center' width='150'>|**[sleepy](/retired/sleepy/Readme.md)**: The aim of this echOmod is to encase the whole modules object in a neat case, making it transportable.|<ul><li>None</li></ul>|<ul><li>None</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/tobo/viewme.png' align='center' width='150'>|**[tobo](/retired/tobo/Readme.md)**: The aim of this echOmod is to get the HV Pulse done.|<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-9_Pon</li><li>ITF-10_Poff</li><li>ITF-19_3.3V</li><li>ITF-mET_Transducer</li></ul>|<ul><li>ITF-18_Raw</li><li>ITF-mET_SMA</li><li>ITF-mET_Transducer</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/alt.tbo/viewme.png' align='center' width='150'>|**[alt.tbo](/retired/alt.tbo/Readme.md)**: The aim of this echOmod is to get the HV Pulse done.|<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-9_Pon</li><li>ITF-10_Poff</li><li>ITF-19_3.3V</li><li>ITF-mET_Transducer</li></ul>|<ul><li>ITF-18_Raw</li><li>ITF-mET_SMA</li><li>ITF-mET_Transducer</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/cletus/viewme.png' align='center' width='150'>|**[cletus](/retired/cletus/Readme.md)**: The aim of this module is to interface the transducer and the servo, aka the physical parts, to the analog part of the modules chain. More to come with the <a href="/retired/loftus/source/s3/Readme.md">Loftus head</a>.|<ul><li>ITF-A_gnd</li><li>ITF-B_5v</li><li>ITF-N_cc_motor_pwm</li><li>ITF-S_3_3v</li><li>ITF-mET_Transducer</li><li>ITF-mET_Piezo</li></ul>|<ul><li>ITF-mET_Piezo</li><li>ITF-mET_Transducer</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/tomtom/viewme.png' align='center' width='150'>|**[tomtom](/retired/tomtom/Readme.md)**: The aim of this echOmod is to digitalize the signal, and to control the pulser, servo, ...|<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-3_ENV</li><li>ITF-15_GPIO21</li></ul>|<ul><li>ITF-16_POn3</li><li>ITF-16_POn3</li><li>ITF-17_POff3</li><li>ITF-14_PWM</li><li>Wifi</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/oneeye/viewme.png' align='center' width='150'>|**[oneeye](/retired/oneeye/Readme.md)**: The module aims at making a microcontroler, for the moment the <code>ArduinoTrinketPro</code>, usable with the motherboard and the set of modules.|<ul><li>ITF-3_ENV</li><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li></ul>|<ul><li>ITF-7_GAIN</li><li>ITF-9_Pon</li><li>ITF-10_Poff</li><li>ITF-14_PWM</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/croaker/viewme.png' align='center' width='150'>|**[croaker](/retired/croaker/Readme.md)**: The aim of this echOmod is to receive the signal and process it, then stream it over wifi. |<ul><li>ITF-3_ENV</li><li>ITF-10_Poff</li><li>ITF-9_Pon</li><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li></ul>|<ul><li>ITF-19_3.3V</li><li>ITF-mED-TFT-Screen</li><li>ITF-mED-OLED-Screen</li><li>ITF-mEC-WiFi-UDP-Stream</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/toadkiller/viewme.png' align='center' width='150'>|**[toadkiller](/retired/toadkiller/Readme.md)**: The aim of this echOmod is to simulate the enveloppe (or maybe soon the raw signal) that would come from the piezo and analog chain.|<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-19_3.3V</li><li>ITF-3_ENV</li></ul>|<ul><li>WiFi UDP Stream</li><li>ITF-mED-TFT-Screen</li><li>ITF-9_Pon</li><li>ITF-10_Poff</li><li>ITF-14_PWM</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/retro10PV/viewme.png' align='center' width='150'>|**[retro10PV](/retired/retro10PV/Readme.md)**: The aim of this echOmod is to get the mechanical movement of the piezos. Salvaged from a former <a href="http://echopen.org/index.php/ATL_Access_10PV">ATL10PV</a>.|<ul><li>ITF-A_gnd</li><li>ITF-F_12V</li><li>ITF-N_cc_motor_pwm</li><li>ITF-mET_Transducer</li><li>Motor</li><li>Tri-Piezo Head</li></ul>|<ul><li>Motor</li><li>ITF-mET_Transducer</li><li>Tri-Piezo Head</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/loftus/viewme.png' align='center' width='150'>|**[loftus](/retired/loftus/Readme.md)**: The aim of this module is to recycle a previous head|<ul><li>ITF-A_gnd</li><li>ITF-B_5v</li><li>ITF-N_cc_motor_pwm</li><li>ITF-S_3_3v</li><li>ITF-mET_Transducer</li><li>ITF-mET_Piezo</li></ul>|<ul><li>ITF-mET_Piezo</li><li>ITF-mET_Transducer</li></ul>|
|<img src='https://github.com/kelu124/echomods/blob/master/retired/mogaba/viewme.png' align='center' width='150'>|**[mogaba](/retired/mogaba/Readme.md)**: The aim of this echOmod is to get 3.3V and 5V done.|<ul><li>ITF-mEM_Alimentation</li></ul>|<ul><li>ITF-1_GND</li><li>ITF-2_VDD_5V</li><li>ITF-19_3.3V</li></ul>|


# Interfaces table for the motherboard

| Name | Title | Amplitude | Raspberry GPIO | 
|------|-------|-----------|-----------|
|`ITF-1_GND`|_Ground_|[0V]||
|`ITF-2_VDD_5V`|_5V alimentation_|[5V, 5V]||
|`ITF-3_ENV`|_Enveloppe of the signal_|[0V, 2.5V]||
|`ITF-4_RawSig`|_Amplified filtered signal_|[0V, 2.5V]||
|`ITF-5_RENV`|_Raw signal envelope_|[VREF, 2.5V]||
|`ITF-6_P6`|_ OLED SDA_|[0V, 3V]|  GPIO 02 |
|`ITF-7_GAIN`|_Amplifier gain control_|[0V, 1V]||
|`ITF-8_P8`|_-Pi OLED SCL_|[0V, 3V]| GPIO03|
|`ITF-9_Pon`|_Pulse on_|[0V, 5V]| Jumper to connect to GPIO 23 |
|`ITF-10_Poff`|_Pulse off_|[0V, 5V]| Jumper to connect to GPIO 24 |
|`ITF-11_OffSig`|_Signal offset by Vref/2_|[0V, 3.3V]||
|`ITF-12_RPIn`|_Pi ADC DAQ_|[0V, 3.3V]|GPIO 05|
|`ITF-13_P13`|_Unused_|||
|`ITF-14_PWM`|_Servo PWM_|[0V, 3.3V]|GPIO 06|
|`ITF-15_GPIO21`|_GPIO21 connection_|| GPIO 21|
|`ITF-16_POn3`|_Pulse On 3V_|[0V, 3.3V]| GPIO 23|
|`ITF-17_POff3`|_Pulse Off 3V_|[0V, 3.3V]| GPIO 24|
|`ITF-18_Raw`|_Raw signal fro transducer_|[-5V, 5V]||
|`ITF-19_3.3V`|_3.3V alimentation_|[3.3V, 3.3V]||

# Interfaces for Raspberry Pi

```
-> Core
#define ADC_CLK	 4
#define RPIn	 5
#define PWM	 6
#define Puls_ON	 23
#define Puls_OFF 24
#define TRACKER	 21
-> Optional
#define oled_sda 2
#define oled_sdc 3

//ADC 1
#define BIT0_PIN 16
#define BIT1_PIN 17
#define BIT2_PIN 18
#define BIT3_PIN 19
#define BIT4_PIN 20
#define BIT5_PIN 22
#define BIT6_PIN 25
#define BIT7_PIN 26
#define BIT8_PIN 27

//ADC 2 (leaves SPI0 free)
#define BIT0_PIN 7
#define BIT1_PIN 8
#define BIT2_PIN 9
#define BIT3_PIN 10
#define BIT4_PIN 11
#define BIT5_PIN 12
#define BIT6_PIN 13
#define BIT7_PIN 14
#define BIT8_PIN 15
```

# License

## echOmods 

The [echOmods project](https://github.com/kelu124/echomods) and its prototypes are open hardware, and working with open-hardware components.

Licensed under TAPR Open Hardware License (www.tapr.org/OHL)

Copyright Kelu124 (kelu124@gmail.com) 2015-2018

## Based on 

The following work is base on a previous TAPR project, [Murgen](https://github.com/kelu124/murgen-dev-kit) - and respects its TAPR license.

Copyright Kelu124 (kelu124@gmail.com) 2015-2018

## Disclaimer

This project is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. 



[](@autogenerated - invisible comment)