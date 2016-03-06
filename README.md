# BionicSheep_v2.0

Prototype 2 of ultrasound regulator component
technical execution by Paolo Cavagnolo, Maker

*January 2016*

## Description
The goal of this prototype is to understand the capability of ultrasonic soundwaves to keep wolves away from flock of sheep. The ultimate idea could be the designing of a collar that protect the sheep wherever it is, but in order to achieve this goal it is important to understand the real potential of ultrasonic soundwaves to traumatize a hungry wolf.


## State of the art
*11 Sep 2010* -  Fabien Matter, a student of infotronics at the University of Applied Sciences for Western Switzerland, based in Sion, canton Valais, was involved in a team to study a possible chemical solution for keeping the wolf away from sheep. He gave an [interview to swissinfo.ch](http://www.swissinfo.ch/eng/swiss-design-anti-wolf-collar-for-sheep/28312534).

*6 Ago 2012* - [Alert via text message when a sheep is been attacked](http://www.bbc.com/news/technology-19147403)

## Wolf behaviour and auditory range
https://www.admin.ch/cp/f/3b4195c2_1@fwsrvg.bfi.admin.ch.html
http://www.wwf.ch/de/hintergrundwissen/biodiversitaet/arten/portraets/wolf.cfm
http://www.kora.ch/en/index.php?id=86&L=3
https://ukwct.org.uk/


   I have not researched the auditory range of wolves but 40 kHz seems pretty high, I know that dog whistles are around 18-22kHz.
\cite{jones.1967Stewart Breck, Ph.D.
Research Wildlife Biologist
National Wildlife Research Center}


“from 25 to 80 kHz”   -  http://www.runningwiththewolves.org/Anatomy.htm

“around 45 kHz, for dog”  - http://www.lsu.edu/deafness/HearingRange.html


Context

[approfondire parte su Parco Nazionale Nord espania - inland campo dentro - 2004 - 10 anni di scuola di pastori ]


Approach
Once collect the preliminary information about the constraints of the project (frequency range, environment characteristics, wolf behaviour, …) the process to design the ultrasonic collar is defined as follow:

Step 0: build a simple system to measure the frequency and the pressure of ultrasonic sound waves
Step 1: build a system to generate different kind of pulses
Step 2: test the pulses on wolves

From the results of the step 2 will depend the further steps.

The full process will be made from a DIY perspective and all the results will be shared as open data.



Step 0
Measure ultrasonic soundwaves


Theory
Gli ultrasuoni sono così definiti perché escono dal range delle frequenze udibili dall’orecchio umano. Quando si lavora con essi è quindi importante dotarsi di mezzi per poterli valutare, questi possono essere:
valutazione grafica dello spettro in frequenza della pressione sonora
trasformazione degli ultrasuoni nel campo dell’udibile

Entrambe queste metodologie suggeriscono che la registrazione di questi suoni su dispositivi portatili potrebbe essere un buon punto di partenza.
Paramentro molto importante per la registrazione digitale (più comoda e accessibile) è la frequenza di campionamento della scheda audio, dato che la massima frequenza sonora gestibile da una scheda audio corrisponde alla metà della frequenza di campionamento.
Fortunatamente quasi tutte le schede audio moderne arrivano a 384 kHz come massima frequenza di campionamento, portando a 192 kHz la massima frequenza registrabile, ben al di sopra del limite sonoro superiore del lupo.

Risolto il problema del supporto per la registrazione, dobbiamo trovare un microfono che riesca trasdurre tali frequenze nel corrispettivo segnale elettrico. Se si osserva la risposta in frequenza di un normale microfono (fig. 1) si nota che superati i 20 kHz la risposta scende drasticamente sotto i -10 dB,


fig. 1 Risposta in frequenza di un microfono tradizionale


Se si sceglie un microfono apposta per le alte frequenze, come questo ad esempio:


fig. 2 Esempio di microfono per frequenze ultrasoniche

Si troverà una risposta in frequenza adatta alle esigenze:


fig. 3 Risposta in frequenza di un microfono adatto agli ultrasuoni

Il microfono appena mostrato si può trovare qui:
http://www.avisoft.com/usg/cm16_cmpa.htm

Ad un prezzo netto di 850€.

Da una breve analisi del mercato sono stati selezionati i seguenti microfoni:

Nome / marca
Max freq.
Prezzo
Link
Sennnheiser MKH 800
50 kHz
3000 €
http://goo.gl/dzJlrh
Avisoft CM16 / CMPA
150 kHz
850 €
http://goo.gl/bS2U0I
Ultramic 200K
100 kHz
200 €
http://goo.gl/U62zW9


Un’altra possibile strada è quella del fai da te: recuperare semplicemente le capsule microfoniche, creare una struttura e collegarle al computer. Si possono trovare diversi tutorial sull’autocostruzione di microfoni a partire da capsule, quello scelto come riferimento è il seguente:

http://www.wildlife-sound.org/equipment/technote/micdesigns/index.html

Le capsule selezionate sono le seguenti:

Nome / marca
Max freq.
Prezzo
Link
Ultrasonic MEMS Sensor SPM0404UD5
100 kHz
15 €
http://goo.gl/TOQ8gN
WM61A
~60 kHz
10 €
http://goo.gl/pG1Cb3


The chosen mic is the Ultramic 200K, manufactured by an Italian company:



The microphone seems works really well for frequencies below 100kHz.


Altri link di riferimento:
http://www.wildlife-sound.org/equipment/technote/micdesigns/index.html
http://www.linkwitzlab.com/sys_test.htm
http://micbooster.com/primo-microphone-capsules/12-stereo-microphone-kit-of-parts-with-primo-em-172-z1-capsules.html
http://www.zachpoff.com/diy-resources/low-noise-binaural-mics-primo-em172/
http://www.digikey.com/en/articles/techzone/2011/may/ultrasonic-mems-sensor-spm0404ud5

2x capsula EM172 http://www.ebay.it/itm/Primo-EM172-Z1-Microphone-Capsule-/301329833023?hash=item4628a85c3f:g:EBgAAOSw7NNUJdAC

2x capsula WS61A
http://www.ebay.it/itm/Electret-Condenser-Microphone-Cartridge-Mic-Element-Various-Cardioid-and-Omni-/120807337827?var=&hash=item1c20adaf63:m:mLoqLTMYbPVO43fPDl5RQ4w


Step 1
Generate ultrasonic soundwaves

In order to produce the right

Arduino:












http://www.soundlazer.com/product/large-ultrasonic-speaker-array/ 400 €

http://diyaudioprojects.com/Drivers/40-1310/40-1310.htm

http://www.ndt.net/article/ultragarsas/58-2006-vol.1_06-l.svilainis.pdf
