# LWJGL legacy
Though most of this is deprecated as of now I’ve decided to learn it because Minecraft 1.8 uses the fixed function pipeline that 2.9 supports.

## The Display
This video was all about creating a display and game loop to update that display. The display in this case was handled in the `Start.main` function. To create a display you need to …

* Set the display mode (width and height)
* Set the displays title (optional)
* Call the displays create function

```kotlin
Display.setDisplayMode(DisplayMode($width, $height))
Display.setTitle("title")
Display.create()
// throws exception | put with any game init code 
```

Game loop is operated by a Display boolean of `isCloseRequested` which is updated when the player attempts to close the window. On each tick the following things must happen.

* Displays update function should be called 
* Displays sync function should be set the desired frame rate
* Game rendering should take place 

```kotlin
while (!Display.isCloseRequested()) {
Display.update()
Display.sync($frameRate)
// update game }  
```

After the loop is exited and the game should close the `Display.destroy` function needs to be called in order for the window to disappear  
