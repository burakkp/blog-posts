---
title: "Electron application is startup with white screen!.."
datePublished: Thu Mar 12 2020 08:05:28 GMT+0000 (Coordinated Universal Time)
cuid: ck7ogwby100ar69s1r510w6u7
slug: electron-application-is-startup-with-white-screen
tags: javascript, electron

---

Hi folks,

If you electron application is startup with white screen, look at below.

firstly, You should use this >

```
app.whenReady().then(()=>{

splashScreenWindow = new BrowserWindow({ width: 800, height: 600, frame: false, show: false, webPreferences: { nodeIntegration: true }, icon: path.join(__dirname, 'assets/icon.ico') });

    // main window
    mainWindow = new BrowserWindow({ width: 1280, height: 800, minWidth: 1280, minHeight: 800, frame: false, show: false, titleBarStyle: 'hidden', webPreferences: { backgroundThrottling: false, nodeIntegration: true }, icon: path.join(__dirname, 'assets/icon.ico') });

//This is figuring out white screen issue.
 mainWindow.once('ready-to-show', () => {
                
        mainWindow.show();

    })

})
```