## Basics

```javascript
// Import the Electron module
const electron = require('electron');

// Create a BrowserWindow
const { app, BrowserWindow } = electron;
let mainWindow;

app.on('ready', () => {
  mainWindow = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true,
    },
  });
  
  mainWindow.loadFile('index.html');
});
```

## Interacting with the Main Process

```js
// In renderer.js (web page)
const { ipcRenderer } = require('electron');

// Sending a message to the main process
ipcRenderer.send('message', 'Hello from renderer');

// In main.js (main process)
const { ipcMain } = require('electron');

ipcMain.on('message', (event, arg) => {
  console.log(arg); // "Hello from renderer"
});
```

## Dialogs

```js
const { dialog } = require('electron');

// Open file dialog
dialog.showOpenDialog(mainWindow, {
  properties: ['openFile'],
  filters: [{ name: 'Text Files', extensions: ['txt'] }],
}).then(result => {
  console.log(result.filePaths);
});

// Message box
dialog.showMessageBox(mainWindow, {
  type: 'info',
  title: 'Information',
  message: 'This is an information message.',
  buttons: ['OK'],
});
```

## Menu

```js
const { Menu } = require('electron');

const template = [
  {
    label: 'File',
    submenu: [
      { label: 'Open', accelerator: 'CmdOrCtrl+O', click: () => { /* open file */ } },
      { type: 'separator' },
      { label: 'Exit', accelerator: 'CmdOrCtrl+Q', role: 'quit' },
    ],
  },
];

const menu = Menu.buildFromTemplate(template);
Menu.setApplicationMenu(menu);
```

## Notifications

```js
const { Notification } = require('electron');

const notification = new Notification({
  title: 'Notification Title',
  body: 'This is a notification message.',
});

notification.show();
```

## System Tray

```js
const { Tray, Menu } = require('electron');

const tray = new Tray('icon.png');
const contextMenu = Menu.buildFromTemplate([
  { label: 'Open', click: () => { /* show/hide app */ } },
  { label: 'Exit', click: () => app.quit() },
]);

tray.setToolTip('My App');
tray.setContextMenu(contextMenu);
```

## Auto-Updater

```js
const { autoUpdater } = require('electron-updater');

autoUpdater.checkForUpdatesAndNotify();
```

## Packaging and Distribution

Use tools like `electron-builder` or `electron-packager` to package and distribute your Electron app.

```bash
npm install electron-builder --save-dev
```

# Advanced

## Communication between Renderer Processes

```javascript
// In renderer.js
const { ipcRenderer } = require('electron');

ipcRenderer.on('message-from-main', (event, args) => {
  // Handle data from the main process
});

ipcRenderer.send('message-to-main', data);
```

## Webview Tag for Embedded Web Content

```js
<!-- In HTML -->
<webview src="https://www.example.com"></webview>
```

## Native Node.js Modules in Renderer

```js
// In renderer.js
const os = require('os');

console.log(os.platform());
```

## Global Shortcuts

```js
const { globalShortcut } = require('electron');

app.whenReady().then(() => {
  globalShortcut.register('CommandOrControl+Alt+K', () => {
    // Perform action
  });
});
```

## Secure Communication with `contextBridge`

```js
// In preload.js
const { contextBridge, ipcRenderer } = require('electron');

contextBridge.exposeInMainWorld('api', {
  sendToMain: (data) => {
    ipcRenderer.send('data-to-main', data);
  },
});

// In renderer.js
api.sendToMain(data);
```

## Native Menus and Custom Shortcuts

```js
// In main.js
const { Menu, globalShortcut } = require('electron');

const template = [
  {
    label: 'My Menu',
    submenu: [
      { label: 'Custom Action', accelerator: 'CmdOrCtrl+Shift+C', click: () => { /* action */ } },
    ],
  },
];

const menu = Menu.buildFromTemplate(template);
Menu.setApplicationMenu(menu);

app.whenReady().then(() => {
  globalShortcut.register('CmdOrCtrl+Shift+K', () => {
    // Perform custom shortcut action
  });
});
	```

## Single Instance Application

```js
const gotTheLock = app.requestSingleInstanceLock();

if (!gotTheLock) {
  app.quit();
} else {
  app.on('second-instance', (event, commandLine, workingDirectory) => {
    // Handle second instance launch
  });
}
```

## Custom Protocols for Deep Linking

```js
// In main.js
app.setAsDefaultProtocolClient('myapp');

// In renderer.js
const { shell } = require('electron');

document.getElementById('open-link').addEventListener('click', () => {
  shell.openExternal('myapp://open/link');
});
```

## GPU Acceleration and Hardware Acceleration

To enable GPU and hardware acceleration, Electron apps use hardware acceleration by default and utilize the system's graphics hardware.

Check the documentation for more details: [https://www.electron.build/](https://www.electron.build/)

>[!Note]
>This cheat-sheet covers some essential concepts and features of Electron.js.