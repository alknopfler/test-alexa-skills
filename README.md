# Alkalarm-alexa-skills

This is the alexa skill for the alkalarm system project integration.

The main idea of this project is create an integration using alexa skills and the echo device
to control the "alkalarm" home security system.

![Alarm System ](./images/schema.jpg)


For example, we could manage the alarm system using:

_**Alexa, open the alarm system, and activate it, after 30 second**_

_**Alexa, open the alarm system, and activate it just for the perimeter**_

_**Alexa, open the alarm system, and stop it**_

_**Alexa, tell me the alarm system state**_



## Alexa Skills Voice Processing Architecture

Just to keep in mind the steps that we have to do in order to create and integrate custom skills with the alkalarm
project, we're gonna review the main architecture of alexa skills processing:

![Alexa Architecture](https://cdn-images-1.medium.com/max/1600/1*2K8S9Zjh2ZQVyRE3gBHK-A.jpeg)

As you can see, we have to define 3 things:

1-. Create your voice user interface for Alexa skill

2-. Create the skills definition in AWS Alexa development console.

3-. Create the lambda code to response the skills questions integrating that with your service.


## Create your voice user interface for alexa skills

First of all, reading the aws alexa development documentation you could find the voice structure in order to create the skill.
It's important to define a human language to make easy interact with Alexa without forcing the language.
In our skill we're gonna explain in two language (currently english and spanish), but the idea is the same for both of them:

![Voice schema](./images/voice-schema.jpg)

The fields are:
 * **control word**: It's the main wake up word for alexa devices
 * **On Launch**: It's quite rare the first time, but if you're not developing an special built-in skill, you have to create OnLaunch 
 intent to "open" the skill with alexa. It was the most un-happpy thing that I've discovered, but if you define something like "open" make sense for the human language perspective.
 * **Invocation Name**: It's the name which alexa will use to know as the reference to your skill. It's recommend something that make sense and also with good pronunciation.
 At this point, the first approach was "alkAlarm", but doing tests, I discovered that it has a non-natural pronunciation in spanish for alexa. I changed it to "alarm system" which is more easy to understand for alexa.
 * **Utterances**: That's the most important part because it's your own creation to interact with the system. I recommend to create over 10 or more examples with synonymous 
 * **Slots**: It's so important if you want to create different behaviours of your system based on time, date, size, and so on.

## Create the Skill in AWS Alexa development console

