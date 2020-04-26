# Mini-Player for Discord

I was thinking about a smaller footprint Discord display, along the lines of the iTunes mini-player. A quick search brought me to the following Reddit thread: [It'd be nice to have a simple always-on-top, mini-discord without the need for injection into the video layer or other API trickery.](https://www.reddit.com/r/discordapp/comments/7pzbe6/itd_be_nice_to_have_a_simple_alwaysontop/)

I realize there is a Discord overlay, but that takes focus and is not helpful in the middle of a game. I have since learned about pinning in the overlay, which is much better. But this project may be worth pursuing nonetheless.

## Electron Transparent Window

```javascript
function createWindow () {
  // Create the browser window.
  mainWindow = new BrowserWindow({
    width: 800,
    height: 600, 
    transparent: true,
    frame:false
  })

  // and load the index.html of the app.
  mainWindow.loadURL(`file://${__dirname}/index.html`)

  // Open the DevTools.
  //mainWindow.webContents.openDevTools()

  // Emitted when the window is closed.
  mainWindow.on('closed', function () {
    // Dereference the window object, usually you would store windows
    // in an array if your app supports multi windows, this is the time
    // when you should delete the corresponding element.
    mainWindow = null
  })
}
```

## References

1. [How to create a transparent window with Electron Framework](https://ourcodeworld.com/articles/read/315/how-to-create-a-transparent-window-with-electron-framework)
1. [Games Overlay 101](https://support.discordapp.com/hc/en-us/articles/217659737-Games-Overlay-101)
