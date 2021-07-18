# Fullname

Andrei Fiodarau

# My Contacts
* Email: fedor608@gmail.com
* WhatsApp: +491786016039
* Discord: fandre11 #7488

# About me

  One year ago i started working as a .NET Developer. Mostly i worked i WPF and WinForms, UI frameworks that creates desktop client applications. I understood that i like to create and design my own aplications. Now i started learning Web Development, what will help me to understand how Web Aplications work and to level up my skills. My strong point is that I can immerse myself in the topic of the task, independently understand the issue and solve the task on my own.

# My Skills

* Python
* C#
* XAML
* WPF
* WF

# Code example

### Example of JS file of chrome app, that realise TCP Communication.

```javascript
window.onload = function ()
{
  let divText = document.querySelector("#textcontainer");
  let socketId;
  let TCPPort = 834;
  let IP = "192.168.75.2";
  let msg = "0A 00 03 08 FF 00 10 00 D2 08";

  document.querySelector("#disconnect").addEventListener("click",
      function () {
          chrome.sockets.tcp.disconnect(socketId);
          chrome.sockets.tcp.close(socketId);
          divText.innerText += "\n" +"Disonnected"
      }
  );

  document.querySelector("#write").addEventListener("click",
      function () {
          transfer();
      }
  );

  function read(){
      chrome.sockets.tcp.onReceive.addListener(function(info) {
          if (info.socketId !== socketId)
              return;

          let rx = new Uint8Array(info.data.slice(0, info.data.byteLength));
      });
  }
 
  function transfer()
  {
      try
      {
          chrome.sockets.tcp.create({}, function(createInfo)
          {
              socketId = createInfo.socketId;
              chrome.sockets.tcp.connect(createInfo.socketId, IP, TCPPort, function ()
              {
                  chrome.sockets.tcp.send(createInfo.socketId, stringToByteArray(msg), function (){
                      read(); });
              });
          });
          chrome.sockets.tcp.disconnect(createInfo.socketId);
          chrome.sockets.tcp.close(createInfo.socketId);
      }
      catch{}
  }

  function stringToByteArray(stringOfHex) {
      var strSplited = stringOfHex.split(" ");
      var ints = new Int8Array(10);
      for(var i = 0; i < ints.length; i++)
      {
          ints[i] = "0x" + strSplited[i];
      }
      return ints;
  }

  function arrayBufferToByteArray( buffer ) {
      let sliced = new Uint8Array(info.data.slice(0, info.data.byteLength));
  }
}
```
# Work experience

  * Experience in developing desktop applications in WPF, WF and C# backend. 
  * Development of TCP, UDP, USB, Serial communication with Python. 
  * Also small experience in development of chrome-apps and extensions.

# Educationhui

 * BNTU - faculty of Engineering and Pedagogy, specialty Vacuum and compressors technology.
 * Online Udemy - Programming in C#

# English

### Level
* B2
### Experience
* European voluntary year in Germany
