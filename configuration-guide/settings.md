---
description: Configuration with the user interface.
---

# Settings

The settings window is divided into sections, which you can navigate between with the side menu. Below, the individual settings will be categorized by which section they fall under.

## Interface

### **Save the width of the sidebars between restarts? \(Boolean\)**

You many want to enlarge or shrink the sidebars in the interface, to see more options or to give an image more screen real estate. However, by default, these changes are saved between restarts, which may not be what you want.  
**Enabled \(default\):** If you change the width of a sidebar and restart, that width will persist between restarts.  
**Disabled:** Immediately when you disable this setting, TagViewer will stop saving the sidebar widths. However, this does not mean that they will reset to default. Instead, the widths you had them set to before disabling this setting will become the default, and, after every restart, the sidebars will reset to that width. For this reason, you should first set the widths that you want to become the default, and then disable this setting. To clarify, you are still able to resize the sidebars, however after you restart the application, the widths will go back to their defaults \(i.e., what you had them set to before you disabled this setting\).

## General

### Offer the previously open TagSpace on the landing page?

This setting is fairly self-explanatory: if you don't want the option to reopen the previously open TagSpace to be enabled in the landing menu, disable this.  
**Enabled \(default\):** The option will be enabled \(given that there is a previously open TagSpace and it is valid\) and clicking it will reopen the previously open TagSpace.  
**Disabled:** The option will be disabled, though it will still be present.

### Automatically reopen the previously open TagSpace when TagViewer starts?

If you work mainly in one TagSpace or you appreciate a "session resume" feature, you may want to enable this setting.  
**Enabled:** Given that there is a previously open TagSpace and that it is valid \(not corrupt\), the previously open TagSpace will be automatically reopened on startup.  
**Disabled \(default\):** The previously open TagSpace will not be reopened on startup.

## Slideshow

### Duration to show each item \(in seconds\) \(Number\)

The default, one second, may be too fast \(or too slow\) for you. This setting is the number of seconds that each image will be shown for. It allows decimals up to a hundredth of a second \(0.01 for this setting\). 

{% hint style="info" %}
If there is a slideshow active when you change this setting, you will have to stop and restart the slideshow before each item's duration will change.
{% endhint %}

### End the slideshow when you exit fullscreen? \(Boolean\)

By default, any active slideshow will end when you exit fullscreen. To disable this behavior, this setting is offered.  
**Enabled \(default\):** Any active slideshow will end when you exit fullscreen.  
**Disabled:** The slideshow will not end when you exit fullscreen. You can still end the slideshow within fullscreen, or after you've exited fullscreen.

### End the slideshow when the last item is reached? \(Boolean\)

You may want the slideshow to end \(instead of restart at the beginning\) when you reach the last item in the TagSpace. Enable this setting to do that.  
**Enabled:** The slideshow will end automatically when the last item is reached.  
**Disabled \(default\):** The slideshow will wrap around and restart at the first item when the last item is reached, allowing it to continue indefinitely.

