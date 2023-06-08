### Window management

The main process' primary purpose is to create and manage application windows with the`[BrowserWindow](<https://www.electronjs.org/docs/latest/api/browser-window>)` module. Each instance of the `BrowserWindow` class creates an application window that loads a web page in a separate renderer process. You can interact with this web content from the main process using the window's `[webContents](<https://www.electronjs.org/docs/latest/api/web-contents>)` object.

### Application lifecycle

The main process also controls your application's lifecycle through Electron's`[app](<https://www.electronjs.org/docs/latest/api/app>)`module. This module provides a large set of events and methods that you can use to add custom application behaviour (for instance, programmatically quitting your application, modifying the application dock, or showing an About panel).