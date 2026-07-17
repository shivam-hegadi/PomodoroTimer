# PomodoroTimer
Pomodoro Timer for ESP32 CYD for hackclub program

# Project Journal

## Journal 1
I wanted to make Pomodoro timer using my 10$ esp32 CYD. It has a powerful esp32 which can connect to the internet and run powerful UIs. 

## Journal 2
I made a super simple UI for the timer using TFT eSPI. It features the timer and a start and reset button as well as a current timer state and Pomodoro in the top left. I plan on making it portrait mode as well as using LVGL to make the UI look nicer. I also want to add a weather feature but I dont know if I have enough time.
<img width="1440" height="960" alt="image7" src="https://github.com/user-attachments/assets/79e88d3c-35a1-4d0d-8938-8a0f07b599a5" />

## Journal 3
I was having some issues with the touch calibration so I had to get calibration code from Random Nerd Tutorials to calibrate the touch values for the screen. This will allow me to plug it into the code and get an accurate touch points.
<img width="1440" height="960" alt="image4" src="https://github.com/user-attachments/assets/f45273a4-4549-49e2-b5f4-0d1e2e89bac5" />

## Journal 4
I tried to fix the touch logic but it still doesnt work. I am receiving phantom presses when i check the serial monitor. I believe this is an issue with the library that I am using (XPT2046 touchscreen), but i will continue to experiment with the touch logic.
<img width="1440" height="960" alt="image10" src="https://github.com/user-attachments/assets/2b817d2b-5e84-4157-8f8f-9ceed8be241a" />

## Journal 5
I implemented the touch logic from one of my older projects, specifically a dedicated HSPI bus and used the touch_irq pin. All the buttons work perfectly now. However, the screen flashes on and off when it needs to update something on the screen. I need to figure out how to increase the refresh rate.


https://github.com/user-attachments/assets/c2c5d81e-64f9-4ad5-bf66-e732a4140ca5


## Journal 6
I removed the "flicker" that used to occur by only updating the section that needed to be updated, not the entire screen. I also added state tracking to know which state it is in. My next step is to convert it to vertical so it takes up less space on the desk.

## Journal 7
I converted the UI to portrait mode so the physical case takes up less space on the desk. I dont like a lot of clutter on my desk so a more compact profile is right for me.
<img width="1440" height="960" alt="image6" src="https://github.com/user-attachments/assets/aeed8f6f-9bf3-4617-bac2-028019d3ed5a" />

## Journal 8
I centered all of the buttons and text. I used drawstring with MC_DATUM so everything is always centered. I also found an issue where the start and reset text has a black highlight, so i need to fix that. I am also going to try and convert my UI to LVGL, so it looks better. I also want to add a way where you can set your own custom timer.
<img width="1440" height="960" alt="image3" src="https://github.com/user-attachments/assets/fd9f4187-668a-426d-9a4d-95717d77f597" />

## Journal 9
I converted the code to use LVGL. I ran into an issue, however, where my touch is not working again. I need to troubleshoot. I am not receiving any inputs in the serial monitor either. I will also change the background color and add in some more settings.
<img width="1440" height="960" alt="image1" src="https://github.com/user-attachments/assets/97d92781-89a4-4b2c-a42f-dcc1c81ea6f4" />

## Journal 10
I changed the background color to dark blue and fixed the touch by implementing IRQ touch. However, LVGL is crashing due to excessive memory use. I need to fix this.


https://github.com/user-attachments/assets/2b4343d7-6cc0-4b21-8d06-c64ee25ba6c8


## Journal 11
I changed the code to update only the label inside the button with the text instead of creating a new label every time i clicked the button, which was causing the memory leak. I also verified that the timer was correctly counting down and wasnt flickering the screen.


https://github.com/user-attachments/assets/c200b894-1621-44cd-953e-05099fc2bec4


## Journal 12
I added a settings menu that you need to long press to open. Nothing in there works for now, but I will add functions to the buttons in my next revision. I also need to update the ui in the settings menu because some buttons overlap.


https://github.com/user-attachments/assets/e31feacd-ba8f-4d42-88d3-8ca66ac089ba


## Journal 13
I updated the settings menu to take up the whole screen. I also added functionality to the buttons in the settings menu. I also removed the tone feature because I realized the buzzer I had broke. I still need to reposition some buttons in the settings. Also, there is another memory leak when the break button is pressed.

## Journal 14
I fixed the positioning of buttons in the settings UI. I also fixed the memory leak that was happening when i tried to change the time of break. I think i will add 2-3 more useful features that arent a distraction like a longer break every 4 work sessions and a visual flash when its break time and work time.


https://github.com/user-attachments/assets/2b86ccfa-1e94-4afd-ab8b-93c34188c79e


## Journal 15
I updated the settings UI and added a long break feature where after every 4 work sessions you get a longer break. This can be adjusted in the settings menu. However, I ran into another memory leak when the work time was edited. I will fix that in the next (hopefully final) revision. I will also design and 3D print a custom case for the ESP32 CYD.


https://github.com/user-attachments/assets/f7585aa1-0192-462e-b2ae-0b5b4774af75



## Journal 16
This is my last revision. I fixed all possible memory leaks by removing the lv_obj_get_parent and get_child calls, storing label pointers globally, using the update_settings_labels function, and removed string searches.



https://github.com/user-attachments/assets/4d5b32fd-0384-48a7-8633-e0477c642308




## Journal 17
I made a 3D printed case for the ESP32 CYD and assembled it. The final product can be seen here: https://youtu.be/89NieqJ5Dcc (live demo)




## Time Tracking - Total Time: 9.4 Hours
Breakdown : 5 Hours 36 min coding , 3 hours 50 minutes Lapse Hardware
Hackatime proof: 
<img width="736" height="369" alt="Screenshot 2026-07-17 at 8 43 56 AM" src="https://github.com/user-attachments/assets/f01305e8-86ee-420c-959d-c563464714b6" />
Lapse Recording Links:
https://lapse.hackclub.com/timelapse/elaolRf_I7CP
https://lapse.hackclub.com/timelapse/8sCAsRX_WNzi
