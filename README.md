![ ](Aspose.Words.ac0c99e2-122b-4000-9d42-e099a3181967.001.png)    JR6001 Voice Module Instructions V 2.1

————————————————————————————————

1. **Module characteristics**

1、Support MP3 and WAV, high quality audio format and beautiful voice.

2、24-bit DAC output, dynamic range 90 dB, signal ratio 85 dB

Supporting two-wire serial port control and AD control

3. USB updates voice files, without installing drivers, without installing software, directly copy, fast and convenient. Support XP system, WIN7, WIN8, WIN10 system

5、Support the following function control mode ：Last song, next song, play, pause, stop, song selection

6、Supporting Free Combination Playing

7、Support for 30-level volume adjustment

8、Support for 30-level volume adjustment

9、Dedicated BUSY signal output indication.

10、Mature instructions and instruction parsing to make the application more stable

11、Dedicated matching host computer, quick to get started, easy to debug, automatic command generation

**B.Applied to the following locations**

\1. Industrial control field: industrial equipment, control equipment, etc.

\2. Intelligent transportation equipment: toll station, parking lot, car voice prompt;

\3. Advertising and propaganda industry: advertising language broadcasting;

\4. Access control, attendance: the door has been opened, verified and passed, etc.

\5. Security industry: human body induction prompts, safety voice prompts, warm prompts;

\6. Game industry: swing machine, bumper car, basketball machine, etc.

\7. Medical Electronics: Callers, excluding call machines, etc.

\8. Educational Communication: Educational Equipment, Communication Electronics;

**C、Update voice description**

This module has its own USB interface, which can flexibly replace the voice content in SPI-flash. It saves the trouble of installing the upper computer to replace the voice in the traditional voice chip. SPI FLASH is directly simulated as a U-disk, which is very convenient as copying a U-disk.Any computer system can support it，Other common solutions can only support XP and WIN7 systems to update voice.

USB data line connection module, plug in the computer, the computer will automatically identify, as shown in the following figure:![](Aspose.Words.ac0c99e2-122b-4000-9d42-e099a3181967.002.png)And then double-click on the new disk and copy the sound you want to place.

4. **Hardware parameter**

|<h1>Name</h1>|<h1>Parameter</h1>|
| :-: | :-: |
|<h1>MP3、WAVMP3 file format</h1>|<h1>Support rates 8-48K  and 8-320kbps  audio decoding</h1>|
|<h1>USB port</h1>|<h1>2.0 Standard (Supports any computer operating system)</h1>|
|<h1>UART port</h1>|<h1>Standard serial port, 3.3 TTL level, baud rate 9600</h1>|
|<h1>Input voltage</h1>|<h1>DC3.6-5.2V（Recommend 4.2V）</h1>|
|<h1>Rated current</h1>|<h1>` `working current：10MA</h1>|
|<h1>PCB Size</h1>|<h1>19\*25 mm</h1>|
|<h1>Work temperature</h1>|<h1>-40℃~85℃</h1>|
|<h1>Humidity</h1>|<h1>5%～95%</h1>|

# **E、 Module pin description**
# ![](Aspose.Words.ac0c99e2-122b-4000-9d42-e099a3181967.003.png)

|<h1>Pin NO.</h1>|<h1>Pin name</h1>|<h1>Function description</h1>|
| :-: | :-: | :-: |
|<h1>1</h1>|<h1>GND</h1>|<h1>ground</h1>|
|<h1>2</h1>|<h1>VCC</h1>|<h1>Modular power supply pin,DC 3.6-5.2V</h1>|
|<h1>3</h1>|<h1>RX</h1>|UATR Serial Port Data Input|
|<h1>4</h1>|<h1>TX</h1>|UATR Serial Port Data Output|
|<h1>5</h1>|<h1>BUSY</h1>|<h1>Busy signal, output high level when playing voice</h1>|
|<h1>6</h1>|<h1>SPK+</h1>|<h1>Accept the horn, regardless of positive or negative</h1>|
|<h1>7</h1>|<h1>SPK-</h1>||
|<h1>8</h1>|<h1>AD\_KEY</h1>|<h1>AD port, the resistance with different parameters has different functions. Refer to the circuit diagram in detail.Refer to the circuit diagram for details.Refer to the circuit diagram for details</h1>|
|<h1>9</h1>|<h1>DACR</h1>|<h1>Audio Right Channel Output</h1>|
|<h1>10</h1>|<h1>DACL</h1>|<h1>Audio Left Channel Output</h1>|
#
# **F、AD key usage instructions**
`	`The AD\_KEY pin of the module is reserved for external control keys. A total of 5 control keys can be added. Functions are as follows: volume decreases, volume increases, the last song, the next song, play/pause.To use this function, additional circuits are needed as follows:![](Aspose.Words.ac0c99e2-122b-4000-9d42-e099a3181967.004.png)

` `The R7-R10 four resistors are constructed with 1% precision resistors

**G、Serial Communication Instructions**

1.Communication Mechanism

\1. As slave processing, we default to wait for power on. All playback operations are initiated by the host.

\2. Slave computers will not initiate communication on their own initiative. All communications are initiated by the host.

\3. Serial port is 3.3V TTL level. If the host system is 5V level, please put 1K resistance in the middle string.

\4. All data in the protocol are ASCII codes.

2.Agreement

The following data definitions are identifiable by the core

Playback status: the system is powered on in a stop state

Disk Character Definition: Stop after Switching Disk Characters

USB:00 TF:01 FLASH:02 NO\_DEVICE:FF

Volume: Volume is 31, 0-30, power-on default is 20.

Play Mode Definition: Power-on defaults to single stop

Whole Circle (00): Play the whole track in sequence, and then play it in circle after playback.

Mono Loop (01): Always Loop the Current Track

Single Stop (02): Stop playing the current track once

Total Random (03): Random Play of Tracks in Characters

Catalog Loop (04): Play the tracks in the current folder in sequence, and play them in a loop after playing. The catalog does not contain subdirectories.

Random Directory (05): Play in the current directory randomly, the directory does not contain subdirectories

Catalog sequential playback (06): Play the tracks in the current folder in order, stop after playback, the directory does not contain subdirectories

Sequential Play (07): Play the whole track in sequence and stop after play.

Definition of Combination Play: Combination Play is a combination of file names. File requirements are stored in the "ZH" folder. The name of the file to be combined can be changed to the name of two bytes, usually expressed in numbers. For example: 01.mp3, 02.mp3 

[](https://fanyi.baidu.com/translate?aldtype=16047&query=7%E8%B7%AF%E8%AF%AD%E9%9F%B3%E8%A7%A6%E5%8F%91%E7%BA%BF%E8%83%BD%E8%AE%BE%E7%BD%AE%E6%B2%BF%E8%A7%A6%E5%8F%91%E6%88%96%E7%94%B5%E5%B9%B3%E8%A7%A6%E5%8F%91%EF%BC%88%E8%83%BD%E5%AE%9E%E7%8E%B0%E8%A7%A6%E5%8F%911%E6%AC%A1%E6%92%AD%E6%94%BE%E8%AE%BE%E5%AE%9A%E7%9A%84%E6%AC%A1%E6%95%B0%E5%90%8E%E8%87%AA%E5%8A%A8%E5%81%9C%E6%AD%A2%EF%BC%8C%E6%88%96%E8%A7%A6%E5%8F%91%E9%87%8D%E5%A4%8D%E5%BE%AA%E7%8E%AF%E6%92%AD%E6%94%BE%EF%BC%8C%E8%A7%A6%E5%8F%91%E7%94%B5%E5%B9%B3%E4%B8%8D%E5%AD%98%E5%9C%A8%E5%90%8E%E5%81%9C%E6%AD%A2%EF%BC%89&keyfrom=baidu&smartresult=dict&lang=auto2zh###)3.Communication instruction

1. Play(A2)

Directive：    A2

Note: Any time this command is issued, the current track will be played from scratch.

2、Pause(A3)

Directive：    A3

3、Stop(A4)

Directive：    A4

Return :null

4、Next(A5)

Directive：    A5

5、Last（A6)

Directive：    A6

6、Designated tracks(A7)

Directive：    A7:00001

E.g     A7:00008 Specifies to play a file named 00008 in the current memory.

Number of tracks from 00001-99999

7、Specify Disk Character, Specify Path Play(A8)

FLASH Directive：	：A8:02+Path

TF Directive：	：A8:01+Path

U Directive：	：A8:00+Path

The instructions require MP3 file names loosely, both in English and Chinese, but only 8 bytes at most. 

e.g1:To play the 00005.MP3 file in the FLASH root directory，A8:02/00002\*???

` `A8:02    A8 is Directive NO.，02 is a express FLASH， 

/00002\*???    Is the path format

e.g2:To play the apple.MP3 file recorded by MUSIC in FLASH,Directive:

A8:02/MUSIC\*/APPLE\*???

A8:02    A8 is Directive NO.，02 is a express FLASH， 

/MUSIC\*/APPLE\*???      is Path format 

8、End play(AE)

Directive：AE

Note: This instruction can terminate the current operation ahead of time, will terminate the current play, if it is in the plug-in, etc., will end the plug-in ahead of time and return to the original state.

9、Volume Setting(AF)：

Directive：AF:XX

For example:AF:20 Set the volume to level 20

10、Volume plus(B0)：

Directive：B0

11、Volume minus (B1)：

Directive：B1

12、Setting cycle mode(B4)：

Directive：B4:XX

For example:Set to Mono Stop : B4:01

13、Combination play(B7) 

Composite playback can only play files in the ZH folder, and the file names in the folder need to be two digits.

Directive：B7:XXXX  （Follow the file name in the ZH folder directly behind the colon） 

For example:B7:01020504，Files named 01, 02, 05, 04 in ZH folder will be played in this order 

14、End Combination Play(B8)

Directive：B8

Note: End the combination playback and return to the pre-combination playback status

With special debugging tools, the instructions can be automatically generated to facilitate debugging and quickly start. The following figure shows: ![](Aspose.Words.ac0c99e2-122b-4000-9d42-e099a3181967.005.png)




**H、Module Packaging Size Diagram**

![](Aspose.Words.ac0c99e2-122b-4000-9d42-e099a3181967.006.png)

**I、Asked questions frequently** 

For the first time, it is suggested to use the matching "serial debugging tool", which can debug the functions of the module and obtain the corresponding functional instructions.

1. How to judge the quality of the module?

TX and RX of PC serial port need to be crossed and connected with module, that is, RX of PC serial port to module and TX of PC serial port to module.

The IO level of this chip is 3.3V. If the IO of the single chip computer connected to it is 5V, it is necessary to connect a 1K resistance between the TX of the single chip computer and the RX of the module. Otherwise, the module may work abnormally.

\2. Is the serial connection correct but cannot be played?

After the module connects to the computer through the USB cable, it is in the U-disk mode. At this time, it does not accept any control instructions. Please switch to other power supply.


——————————————————————————————————————

Shenzhen Jiaren Science&Technology Co., Ltd.     Address:Office 712, Weiteng Technology Building, 91 Jingnan Road, Buji Subdistrict, Longgang District,Shenzhen City,Guangdong Province,China  Tel：0755-28685464   Tel：+8615816591967(Wechat)    QQ：769503664

