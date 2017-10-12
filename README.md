![alt text](https://github.com/BioMakers/01_A-cell-free-sensor-for-arsenic-in-drinking-water./blob/master/Banner.png)

## Synopsis

Arsenic contamination of drinking water is a global issue affecting in the region of 150 million people.  Arsenic poisoning  is highly prevalent in countries surrounding the Himalayas such as India, Nepal, Bangladesh and Pakistan and arises from natural contamination of shallow tube wells.  Currently, drinking water is predominantly tested via chemical sensors, which require toxic reagents, technical expertise and only produces qualitative results. Developments in synthetic biology have shown that biological components can be engineered for heavy metal detection, but methods are limited by GM contamination risks and only provide qualitative readouts. As such, an opportunity has been identified to develop a first-of -kind cell-free quantitative arsenic sensor which uses the synthesis of an electroactive metabolic enzyme for amperometric quantification of arsenic concentrations.  This project was for a first proof of concept of such a sensor.
The system proposed will use a genetic circuit consisting of a promoter responsive to arsenic and a downstream reporter which produces an electroactive enzyme. The enzyme concentration will then be measured using amperometric detection methods allowing a quantitative measurement of arsenic concentration to be determined.



## Sensor Overview

The Figure xx summarises the sensor and its development.  The sensor is based on two genetic constructs.  The first construct provides an inhibiting protein which, when bound to the promoter of the second construct, is sensitive to the presence of arsenic regulating the production of the redox enzyme, glucose oxidase (GOx), by the reporter.  The enzyme concentration is measured using amperometric detection, with a potentiostat, to provide a quantitative measurement of arsenic concentration which is then shared to a central database.  Thus far the different aspects of the sensor have been developed and tested in isolation and modelling used to consider their interactions.

It is envisaged, that if fully developed the sensor would consist of disposable test strips with printed electrodes and freeze dried cell free extract, genetic circuits and electrochemical reagents.  The measurements would be taken via a potentiostat.  When the water sample potentially containing arsenic is added, it rehydrates the system allowing amperometric detection.  

## Synthetic Biology
Figure xxx shows the interactions of the genetic constructs.  The repressor Pars arsR plasmid used was from the international Genetically Engineered Machines Competition (iGEM) registry with a pSB1C3 backbone.  A number of different variations of the repressed/activated plasmid Pars GOx were developed through cloning.  Pars GOx Mvenus was developed for testing with the production.  Testing in the presence of arsenic was conducted first in vivo, within ecoli cells, then in TX-TL cell free extract in vitro as would be used for the final sensor.  Testing resulted in the genetic constructs producing GOx correlated to sample arsenic concentrations.

## Electrochemistry
The arsenic sensor is based on the same principles and electrochemical readout as well-established glucose sensors but applied in reverse to detect GOx concentrations.  

As such, such a system was adapted to a glucose oxidase sensor with fixed quantities of glucose and varied glucose oxidase.  Different detection methods were trialled, interference tests were then undertaken with cell free extract, iron (III), arsenic and Nepal well water and lastly improvements in terms of limit of detection and sample volume were investigated.  

Figure xxx summarises the different trailed techniques for detection of the GOx enzyme.


## Electronics

Figure xxxx is a block diagram of the key components of the developed potentiostat.  In summary, the required redox potential is set by the user.  This is converted into an analogue voltage by signal processing via a digital to analogue converter which is then applied to the potentiostat block.   The potentiostat then sets this voltage to the electrochemical cell and can be considered as a single Op amp.  The IV converter monitors the currents of the working electrodes and converts them into corresponding voltages by an current-to-voltage converter which is fed into the signal processing in which an analogue to digital converter is used to translate the voltage into a measurable signal corresponding to the cell current.

Figure xxx shows the user interface developed in Python QT designer.  The system is platform independent developed to run on a Raspberry Pi, can be powered by two 9V batteries and has four current ranges of 250nA, 2.5μA, 25μA, 250μA.  The developed system can measure currents in the pico amp range with an accuracy of 0.2% of range.  

## Datasharing
The key objective for Data Sharing was to provide a platform for which measured arsenic readings, taken in rural remote locations, could be transmitted to a central database and displayed online.  The system was developed with the consideration of the end users in mind being those who are using the sensor system to test water in countries such as Nepal/Bangladesh and those accessing the data such as NGOs, governments and scientists.  

Figure 14 shows a diagram of different aspects of the implemented system.  The system required developments in both software and hardware.  Both the transmitter and receiver are based on open source Arduino technologies with a Adafruit FONA 808 shield - mini cellular GSM + GPS for Arduino, plug and play shield to provide a GPS location and the ability to transmit the data, by text, over GSM.  The system then processes the text in Python to upload it into a SQLite database which is then mapped in Google maps.  The system’s capabilities were tested by sending texts with readings from different locations in Cambridge.  The cost of the system is currently \pounds130 but is estimated that this could be reduced to $\approx$\pounds22 if manufactured.


## License

A short snippet describing the license (MIT, Apache, etc.) you have chosen to use
