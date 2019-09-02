# SantaWhoop
Firmware for JJRC H67 and Eachine e011c

This repository is based on the work of notFastEnuf's derivate of the silverware Firmware for Quadrocopter style remote cntrolled objects.
It was created due to specific requirements for JJRC H67 and Eachine e011c whoops which is mainly the christmas music, which used to be playing all the time and made generations of FPV lovers go crazy (or remove the speaker).
Actually the music is quite usefull for finding your crashed whoop, so we created the version dedicated to the SantaWhoop:
 a. no need to cut off the speaker
 b. switch the music on/off together with the LEDs
 c. do not loose the warning LED-flashlights (low battery etc.) with no music playing
 d. solid rates and PIDs for exactly this whoop with a standard FPV cam mounted and the brick-Santa and the cover removed.
 
If you just want to go with the preconfigured Santa-firmware, do the following. In all other cases feel free to go with the source code attached or even (what I would recommend) with the original code of NFE: https://github.com/NotFastEnuf/NFE_Silverware and the all original silverware: http://sirdomsen.diskstation.me/dokuwiki/doku.php.
So here the processing for getting the preconfigured code onto your tiny whoop:
 
     1. Hardware required: a santa whoop, a programmer (ST-Link V2, e.g. from Banggood for ~2$)
     2. Download STM32 ST-LINK Utility: https://www.st.com/en/development-tools/stsw-link004.html
     3. Download the hex-File within this repository (either for multi-module or the original toy TX)
     4. Connect the programmer with your whoop:
          There are 4 open pins in the front of the board if you look on the quad with the plastic 
          cover removed. Looking in flying direction it is to be connected from left to right: 
          SWDIO, SWCLK and GND. The 4th is VCC which should not be connected to prevent any damage 
          to the board or your programmer due to any shortcuts or over-current.
     5. Open ST-Link utility (from step 2) for further use in step 7.
     6. Having the programmer connected to your PC and the programming port connected to your quad 
        (I usually only put some cables in there without soldering - works much better than I 
        initially thought) your finally connect the battery. The x-mas songs will immediately start 
        :) now you have to be very quick with the next step to establish a connection (2 sec or so)
     7. Press the connect button within ST Link utility - an error will pop up
     8. Press ctrl-b and change level from 1 to 0
     9. Press ctrl-e to erase the chip
     10. Press ctrl-p and select the hex-file from step 3, than press flash

This is how your "new" quad works
   With the original TX (the toy-remote):
   - Arming/Disarming: trim button underneeth the left throttle stick
   - Switch on/off the beloved x-mas music and the LEDs for better atmosphere and to find your lost 
     quad: trim button under the right stick
   - To change to acro mode use gesture with the rigt stick when the quad is disarmed: left-left-down
   - To callibrate the sensors use gesture: down-down-down
   With the multi module:
     Ch1 - Ail
     Ch2 - Ele
     Ch3 - Thr
     Ch4 - Rud
     Ch5 - Chose a switch for arming
     Ch6 -  " for acro/level mode change
     Ch10 - " for turning on/off music (I configured it inverted so it starts without music playing)

Now you can have fun with your tiny SantaWhoop without going crazy :)
