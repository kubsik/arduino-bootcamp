# arduino-bootcamp
Code for the Arduino Bootcamp Course

This project contains the code for the related projects on my Arduino Bootcamp course
https://www.powerlearningacademy.com/p/arduino-bootcamp-learning-through-projects


Welcome to Arduino Bootcamp : Learning Through Projects. It is a hands-on projects-based approach to learning the Arduino platform that is meant to  take you from Novice to Professional. I’m Lee Assam, an Electrical Engineer, Professional Software Developer and University Instructor, but most importantly an electronics hobbyist. I have been tinkering with Arduino since its inception and teach university courses about it.

This course is meant to quickly get you up to speed with Arduino if you are not already familiar with it and make you a confident Arduino Prototyper.  You will become extremely familiar with the Arduino platform and will be able to undertake complex projects that demonstrate the power of Arduino. As an example, you will be able to build a remote controlled car that can be controlled via a smartphone app, a pan-tilt swivel controlled via a Wii Nunchuck and even an open source phone that you can make actual phone calls from and send text messages, using the Arduino.

Here’s how the course is designed, if you are new to Arduino, the first lessons will get you quickly up to speed on what the platform is and how to use it. You can then progress to simple projects which get you comfortable with basic electrical components.
For those already familiar with Arduino who want to take their skills to the next level, you can jump straight to the intermediate projects section. There we will focus on making game type projects using the Arduino and even an infrared repeater that can allow you to copy, store and playback any IR signal, just like your own universal remote.
Next, for those that might be already comfortable with Arduino, there is an advanced projects section where we tackle projects an like an online weather station, remote controlled car, open source phone and many more.

The ideal student for this course, is someone that is curious and willing to learn about Arduino and is interested in becoming a maker, inventor, entrepreneur, internet of things architect, or an electronics hobbyist looking to develop new ideas and prototypes. No previous programming or electronics knowledge is required. 

I have always believed that project-based learning is best approach where you actually learn by doing and building something that actually works. This is the approach I am taking in this course. I will explain all the electronics principles involved with each project, show you how to wire up the circuits and give a detailed line by line code reviews on how it all works. 

Thank you for your interest in the world of arduino. I look forward to being your guide and let’s make some cool projects together. What are you waiting for, join the Arduino bootcamp and let’s whip your Arduino skills into shape!


# How to Apply External Power In Arduino Projects
Sometimes it is necessary to provide additional external power to your Arduino project. This might be due to the demand for more power imposed by the electrical components that you use in your project.

As an example, if you have a DC motor or a pair of DC motors in your project (this might be the case when you are building a car or robot) or if you have multiple servos, you will need to provide an external power source for your project to operate correctly.

The USB connection to the Arduino only supplies 5V and this is not sufficient to power motors or servos, which often are rated at 6V or higher. In addition, the current requirements of these components is higher and the USB port cannot provide the current draw that is needed to properly operate the circuit. The circuit may start off working fine, but over time, the high current demand cannot be sustained. This results in “brown outs” and an unstable circuit and the Arduino may even reset and start over. In addition, if you want to have your circuit mobile and not tethered to cables, you need to provide external power for your project.

So the question is, how can this be accomplished? There are a couple options here.

1. Using the DC Jack

The Arduino itself can be powered by using the DC jack. In the case of the Arduino Uno, although the operating voltage is 5V, an input voltage higher than this, usually in the range 7-12V is preferred to power the board. A 9V battery which terminates with a 2.1mm barrel connector can be used and plugged into the DC jack. The connector or plug must also be “center positive”, meaning that middle pin of the plug has to be the + connection.

There are several 9V battery holders that have a barrel connector to plug into the Arduino. Some specific examples have been given in the parts list for this course.

An AC-to-DC adapter can also be used. It plugs into your AC wall socket and provides DC output, usually in the range between 9V and 12 V.  Adapters that provide 500 mA or better yet 1A are best as these will definitely be able to provide current to drive components in your project.

If your project can remain stationary, a good option is to use the AC-to-DC adaptor. In this scenario, the VIN pin on the Arduino can then be used as the +ve power connection to drive the other components in your circuit. The power supplied through the jack is in essence accessed through the VIN pin to power your circuit. This is often a very convenient option for projects where the Arduino board does not have to be mobile.

2. Using the VIN pin on the Arduino

If you do not use the DC jack or do not have an external AC-to-DC adaptor or 9V battery with a barrel connector, another option is to provide input directly from your external power source into the VIN pin of the Arduino. As an example, the leads from a battery can be inserted into the GND pin and the VIN pin  to serve as your POWER connector. Essentially in this scenario, instead of using the USB port that is coming from the computer or the DC jack, your external power source provides the input voltage to the board  through the VIN pin.

What should be the voltage of your external power supply?

In the case of the Arduino Uno, the board can operate on an external supply from 6 to 20 volts. If supplied with less than 7V, however, the 5V pin may supply less than five volts and the board may become unstable. If using more than 12V, the voltage regulator may overheat and damage the board. The recommended range is 7 to 12 volts.

A special note about the 5V pin and 3.3 V pin on the Arduino

The 5V pin outputs a regulated 5V from the regulator on the board. The board can be supplied with power either from the DC power jack (7 - 12V), the USB connector (5V), or the VIN pin of the board (7-12V). This can be used to provide 5V to any component in your project. Keep in mind that the current draw from this and other digital pins should be kept under 20 mA. On the Arduino Uno, the 3.3V pin, which as its name implies can also be used to provide 3.3 V to your circuit is capable of providing up to 50 mA current.

# Many different models exist for Arduino. Which one should you use and why?
Arduino comes in many different varieties and sometimes it is difficult to figure out which model you should use. In this class, we have focused on the Arduino Uno which is the most popular variety, but there are also several different other models that you may come across. 

It is important to note that once you become familiar with one model, all others operate similarly. The models typically differ based on the number of I/O pins that are available, Flash memory and EEPROM. From a form-factor perspective, some are smaller than others.

The following link gives a breakdown of the different models that are available: https://www.arduino.cc/en/main/products

Some brief highlights of the technical specs of the most popular models are given below.


ARDUINO UNO

Digital I/O Pins: 14 (6 provide PWM output) 

PWM Digital I/O Pins: 6

Analog Input Pins: 6

Flash Memory: 32 k

EEPROM: 1 k



ARDUINO MEGA

Digital I/O Pins: 54 (15 provide PWM output) 

PWM Digital I/O Pins: 15

Analog Input Pins: 16

Flash Memory: 256 k

EEPROM 4 k



ARDUINO 101 (USA ONLY) /  GENUINO 101 (Outside USA)

Digital I/O Pins: 14 (4 provide PWM output) PWM Digital I/O Pins: 4

Analog Input Pins: 6

Flash Memory: 196 k

EEPROM: 1 k

Features: Bluetooth LE, 6-axis accelerometer/gyro



ARDUINO YUN - Has two processors

AVR Arduino microcontroller

Digital I/O Pins: 20 (7 provide PWM output) 

PWM Digital I/O Pins: 7

Analog Input Pins: 12

Flash Memory: 32 k

EEPROM: 1 k

Arduino Microprocessor

Flash Memory: 16 MB

EEPROM: 1 k

Features: Ethernet 802.3 10/100Mbit/s, 802.11b/g/n 2.4 GHz



ARDUINO NANO

Digital I/O Pins: 22

Analog I/O Pins: 8

Flash Memory: 32 k

EEPROM: 1 k



ARDUINO MINI

Digital I/O Pins: 14 (6 provide PWM output)

Analog Input  Pins: 8

Flash Memory: 32 k

EEPROM: 1 k



ARDUINO GEMMA

Digital I/O Pins: 3 (2provide PWM output)

Analog Input  Pins: 1

Flash Memory: 8 k

EEPROM: 512 bytes



Which model should you choose for your projects?

Arduino Uno - This is the most popular model of Arduino. It can be used for most of your electronics projects. Where you might run into issues is if you require more I/O pins or require additional memory for temporary storage
Arduino MEGA - This is a much bigger Arduino board and has 54 digital I/O pins and 16 analog inputs. When you are connecting to a lot more sensors or have more robust project requirements, this is a good option. There is also 256 k of flash memory which is quite a step up from the 32 k that the Uno provides. It has 4 K EEPROM as well, so if you project needs to store data or do more in-memory processing that is resource intensive, this board will be the best option
Arduino 101 - This board enables you to take your project into wireless mode because it has Bluetooth LE built-in. This is great for your projects that require wireless operation. No Wifi shields or bluetooth add-on modules are needed. It also contains a built-in accelerometer and gyro if your project need those components. Again, this reduces the need for adding on these additional components as they are already built-in and are ready to be used right away
Arduino YUN - This is perfect for your Internet of Things (IOT) projects as it has an ethernet port and WIFI built-in, enabling you to take your project in wireless mode or control it over the Internet. This board is a bit more pricey, but it also contains two processors making it more robust. Use this board for projects that need wireless functionality without the hassle of having to add Wifi or bluetooth components.
Arduino Nano/Mini - These are the smallest Arduino boards and have significantly less pins and memory capabilities than the other models. However, if your project does not have robust requirements and you only need a few pins for sensor measurements, these modules are ideal. They enable you to keep the form-factor of your electronics project small and can be encased in smaller assemblies for prototyping
Arduino Gemma - Perhaps the tiniest of Arduino models. This is perfect for wearable type projects. This board can be attached to clothing or materials without adding bulk to your projects. It has only 3 digital I/O pins with 1 analog input pin and a small memory footprint.
As you can see, there are quite a lot of options for prototyping in the Arduino world. Use the board that aligns with your project requirements. Some things to consider are:

What is the desired size of the end result of your project (bulk/mass)?
How many input/output pins will you need (how many sensor measurements are you taking and how many external components will you be interfaced to)?
Do you need built-in bluetooth/wifi capability?
What are the power requirements of your project?
The answers to these questions can help you make the right choice of an Arduino model for your project. There are lots to choose from! If you have a particular project requirement and are unsure of which Arduino might be best suited for the job, send me a note or post a question and I will be glad to provide some input.

Happy Making!

# Want to learn more?
Would you like to continue your learning journey with me?


Thank you for being a student in my course! I hope you were able to learn a lot and enjoyed the course. Here are some coupons for other popular courses that I have created. Take advantage of these coupons which are the best prices that Udemy would allow me to extend to you. I will see you in the next course!



>> More Arduino Courses



Building Internet of Things Projects with the Arduino IoT Cloud

https://www.udemy.com/course/arduino-iot-cloud/?referralCode=832BE90A15B58641E4D3











Learn how to build Internet of Things (IoT) projects using the Arduino IoT Cloud Platform and the suite of MKR boards from Arduino. Connect your Arduino project directly to the cloud!

Build a :

Temperature regulation system

A motion sensor alarm that rings your smart phone when motion is detected

Widgets and dashboards to control your IoT projects

Connect your Arduino Projects to the Cloud

All circuit diagrams, PDFs, notes provided and explained

https://www.udemy.com/course/arduino-iot-cloud/?referralCode=832BE90A15B58641E4D3



>>  Raspberry Pi Courses









The Ultimate Guide to Raspberry Pi : Tips, Tricks and Hacks

https://www.udemy.com/course/pi-ultimate-guide/?referralCode=3CF10A74CA7F5245DD63

Try out the #1 Raspberry Pi course on Udemy! Learn about the Raspberry Pi, how to install software, work with GPIO pins, cameras, and build exciting projects like an Amazon Echo Clone! Step by step wiring instructions with line by line code reviews in Python! Learn electronics, coding and master the Raspberry Pi!



Work with electronics and Sensors

Learn basic Python programming

Learn how to setup your Raspberry Pi and install applications

Work with Cameras and Images

All circuit diagrams, PDFs, notes provided and explained





https://www.udemy.com/course/pi-ultimate-guide/?referralCode=3CF10A74CA7F5245DD63


Raspberry Pi Bootcamp : For the Beginner

https://www.udemy.com/course/pi-bootcamp/?referralCode=40F1F81E849626EB708F






Get your feet wet with Raspberry Pi and learn the basics and build cool projects like a Retro-Pie gaming system and a Google Home Clone!


Learn to work with simple electronics and sensors

Install web servers

Write scripts

Install various Operating Systems

All circuit diagrams, PDFs, notes provided and explained





https://www.udemy.com/course/pi-bootcamp/?referralCode=40F1F81E849626EB708F



Building Alexa Skills for Home Automation with Raspberry Pi

https://www.udemy.com/course/building-alexa-skills-for-home-automation-with-raspberry-pi/?referralCode=BDBAA6D1B148D7E98916








Learn to Build Alexa Skills to control virtually anything in your home using an Alexa device or the Alexa app on your phone! Make a skill to voice control ANY TV in your home with a Raspberry Pi, even if the tv is 10 or 20 years old!

No Alexa device is needed for this course! Learn IoT, electronics and have fun with the Alexa Ecosystem and a Raspberry Pi. The sky is the limit with the knowledge you will learn from this course!


Along the way you will learn:

Basic Electronics

How to work with relays and safely control high voltage AC devices from a Raspberry Pi

How to use an octocoupler circuit to allow electrical isolation to protect your Raspberry Pi when connecting to high voltage AC power from a relay

How to work with GPIO pins on the Raspberry Pi

Learn about infrared transmitters and receivers

Python programming

Learn to program for Alexa

How to build Custom Alexa Skills from scratch

How to expose your Raspberry Pi to the internet via a publicly available https endpoint using Ngrok

How to build projects for home automation and the internet of things that can be controlled via Alexa

All circuit diagrams, PDFs, notes provided and explained


https://www.udemy.com/course/building-alexa-skills-for-home-automation-with-raspberry-pi/?referralCode=BDBAA6D1B148D7E98916






>> Python




Learning Python 3 Programming for the Absolute Beginner

https://www.udemy.com/course/learning-python-3-programming-for-the-absolute-beginner/?referralCode=A72C670F1C40A24E67B7

Learn the fastest growing and most popular programming language Python. This can help you with Raspberry Pi projects or even if you are looking to learn Python for a job or Data Science.


Learn Python 3 for Beginners Quickly. All major concepts taught. Do challenge questions with fully explained solutions. Get prepared for a new programming career or learn the ins and outs Python to work more effectively with your Raspberry Pi and special projects



Some of what you will learn
Here are some of the topics that will be covered

Variables and Comments

Working with Print Statements

Basic Data Types (Integers, Floats, Strings, Collections)

Operators

Working with Data Collections (Lists, Sets, Tuples, Dictionaries)

Conditionals and Looping

Functions

Object-Oriented Programming and Classes

Error and Exception Handling

Modules

Input and Output

Working with Data Files

Working with HTTP Requests

Much Much more

https://www.udemy.com/course/learning-python-3-programming-for-the-absolute-beginner/?referralCode=A72C670F1C40A24E67B7

Best of luck and I hope to see you in another course!
