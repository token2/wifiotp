#Source code (Autoit) of WifiOTP Token and Client applications 
[WIFIOTP](http://wifiotp.com): PERVASIVE TWO-FACTOR AUTHENTICATION USING WI-FI SSID BROADCASTS

##WifiOTP Server (Token)
As building or configuring a standalone WifiOTP Token device might be rather complex, in order to ease the validation a Windows application has been created to be used as a WifiOTP Token. Windows application is based on creating computer-to-computer (ad hoc) wireless network using “netsh hostednetwork” command. An application has been created using Autoit that generates and encrypts one-time passwords and passes SSID name as an argument to netsh command. This application can run on any computer equipped with a WLAN network card and a recent Windows operating system (tested on Windows XP, Windows 7, Windows 8.x and Windows 10 Preview). The parameters, such as SSID prefix, secret shared key and encryption key are stored in an ini file.

![WifiOTP Server](https://raw.githubusercontent.com/eminhuseynov/wifiotp/master/img/wifiotpserver.png)

##WifiOTP Client
Standard Windows netsh command is capable of scanning the SSIDs broadcasted (“netsh wlan show networks”) . The parsed SSID data needs to be decrypted and sent to input field requesting OTP, which is then submitted the validation server together with other data. A simple system daemon has been developed using Autoit monitors a specific keyboard shortcut (e.g. Ctrl+Alt+X) to send currently broadcasted OTP to active text input. Optionally, it can send return character together with OTP to minimize user’s interaction: e.g. when user is prompted to enter OTP in a web application, pressing Ctrl+Alt+X will insert the required OTP and submit the current form immediately. A screenshot of a running WifiOTP Client application is shown on the figure below. The window below shows the current OTP for demonstration purposes only; the client application should run silently in the background with only an icon displaying its activity in the tray area.

![WifiOTP Client](https://raw.githubusercontent.com/eminhuseynov/wifiotp/master/img/wifiotpclient.png)

