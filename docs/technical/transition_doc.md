# Transition Document

## Anfri's Resend on failed transmission

Functionality and improvements:
On failed transmission cached to local on sd
On successful transmission pops of 3 transmission from failed file
Operates like First In Last Out (FILO) stack – Would have better to operate like First In First Out (FIFO) stack, Could be changed to fifo stack to ensure transmission order. This is because when using FILO the transmitted cached at same time as un-cached, transmissions are by definition out of order

Truncation after successful transmission is O(N) which is extremely in-efficient. This means that it would have been better suited to have to been written native c due to the lack of F-Truncate in micro-python. This would prevent having to read write entire file contents to truncate

Meets requirements

## Liam's Rain gauge filter

When it calls the should-transmit, a conditional statement to see when it's raining. If it is it changes the send-interval

There was mention of record intervals. It is supposed to record far more quickly, down to about 1 second. Rain-gauge should have a separate record interval that activates far more quickly. This change can be made in the conditional.

Next step:

Record interval needs to be toned down to 1 second
Hooked up with bucked and tested
Simulated tests should be checked/written

This meets the requirements

## Liam Sara-4 to asyncio

Out of scope: 2 weeks

## Anfri to Micro-Python

Massive undertaking, out of scope
Update to an even later version of Micro-Python
Current issue expired
Consider pros and cons
Next steps: Dedicated time to work on it
Potentially evaluate changing platforms to C/MicroPython/Rust

## SDI 12 complience

Out of scope
3 Weeks of investigation
Config:

## Vedaanth: RTC Evaluation

Requirements:
One of the things was to evaluate the drift
Created a separate thread so that it is always active and does not drift
The drift was 5 seconds per hour which was impactful: Really bad
Project long
Meets requirement

## Micro-Python

Will and Anfri decided was out of scope:
Will refactoring config:
Config works as is specified
Remember that type-setting does not exist in micro-python 1.14

## Dom, Neldo & Will MMW

Look at my commits
Will: Dialogue with web-app
4 - weeks

## Alex Pipeline and some modem stuff

Pipeline is very reliant on the config files
An important addition could be

Next steps:
Get clarification to stakeholders to specific needs
Using record interval to send different grouped sensors at different times to send in sync, rather than just on the arbitrary system it currently works under.

## Battery fuel gauge Vedaanth

Did discovery on battery fuel gauge
Hardware blocked this as they decided it was too resource intensive.
Telemetry Dom & Neldo & WILL
Four weeks of discovery
We attempted mattermost integration by adding web-hook, currently failing
Have not requirement

Next steps:
Physically test in field
Test on data-recorder

Get rid of MQTT for sending data
For implementing sending straight to mattermost: Find out how to send with https, current set up is wrong for setting up https.The [Comment](https://gitlab.ecs.vuw.ac.nz/course-work/engr301/2023/group3/data-recorder/-/issues/97#note_373841) on this branch goes more in depth. On what to do

## William worked on config

Created an object storing variables
Created sensible defaults so that device will work without jsons
Created a read method to pull data from json, save to different json
Next steps:
Implement config changes to be used in device

---
