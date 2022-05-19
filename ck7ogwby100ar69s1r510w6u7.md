## Electron application is startup with white screen!..

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