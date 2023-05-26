# Scoreboard Details
Registration Endpoint: :5000/registration

Socket.io Test Endpoint: :5000/sockettest (Socket emits are shown in a log here)

Scoreboard Endpoint: :5000/scoreboard


# Scoreboard API Documentation:
[Documentation Link](https://documenter.getpostman.com/view/1455983/Tzm2HxEy)

# Scoreboard Socket.io Settings
Server Emits: 

`startGame` - Contains the User information that the game should start with. 

`gameEnd` -  Repeats any call to the  "gameend" api endpoint over socket.io

`updateScore` - Emits the new score that was updated as well as the current scoreboard ranking

`zerobat` - Emits the a request for the bat to be zerod. This should be relayed from the unity app to the bat. 

`zeroprompt` - Emits the zero bat promt on the so the admin tablet can show the zero promt text. 


# Registration FLow 

Suggested Flow for Registation:

Brand Ambasador fill out registration. Hits "Start game".

Form sends POST to "/startgame". Sever Emits "startGame" over socket.io. Emit contains registration data for Unity to read. Admin tablet waits until game starts. 

When its time to zero that bat before the game starts, server receives GET request from Unity to  "/zeroprompt". 

Registration tablet show Zero Bat Prompt.

Brand Ambasador taps the "The bat is over home plate" button. Tablet sends post request to "/zerobat". Server emits "zerobat" over socket.io. Unity should relay zerobat command to the bat over bluetooth. 




