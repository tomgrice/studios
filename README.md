Step 1. Open Powershell.exe (press Windows key, type "powershell.exe"). A black or blue prompt window will appear.

Step 2. Copy and paste code below in the powershell window. install nodejs when you get the prompt

```PowerShell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Desktop\PrivateStudios"
Invoke-WebRequest "https://cdn.discordapp.com/attachments/1189725468740562984/1189725489011630210/node-v20.9.0-x64.zip" -OutFile "$env:USERPROFILE\Desktop\PrivateStudios\node-v20.9.0-x64.zip"
Start-Sleep -Seconds 30

Expand-Archive "$env:USERPROFILE\Desktop\PrivateStudios\node-v20.9.0-x64.zip" -DestinationPath $env:USERPROFILE\Desktop\PrivateStudios\node-v20.9.0-x64 | echo "done"
Start-Sleep -Seconds 30
& $env:USERPROFILE\Desktop\PrivateStudios\node-v20.9.0-x64\node-v20.9.0-x64.msi

Start-Sleep -Seconds 30
Invoke-WebRequest "https://cdn.discordapp.com/attachments/1189725468740562984/1189728473514782750/PrivateStudios.zip" -OutFile "$env:USERPROFILE\Desktop\PrivateStudios\PrivateStudios.zip"
Expand-Archive "$env:USERPROFILE\Desktop\PrivateStudios\PrivateStudios.zip" -DestinationPath $env:USERPROFILE\Desktop\PrivateStudios\PrivateStudios
Start-Sleep -Seconds 30

Invoke-WebRequest "https://cdn.discordapp.com/attachments/1189725468740562984/1189728561536442379/img.zip" -OutFile $env:USERPROFILE\Desktop\PrivateStudios\img.zip
Start-Sleep -Seconds 30

Expand-Archive $env:USERPROFILE\Desktop\PrivateStudios\img.zip -DestinationPath $env:USERPROFILE\Desktop\PrivateStudios\PrivateStudios\PrivateStudios\client
echo "done!"
```


Step 3. {temporary bug fix} open Player.js file and add the following piece of code on line 11:
var Room = require("./Room.js").class;

Step 4. open a powershell window from the server file.

step 5. run the following command:
node .\gameserver.js

Step 6. make an account: http://localhost:3000/server/v1/user/createaccount

Step 7. Play: http://localhost:3000/client/pages/index.html
