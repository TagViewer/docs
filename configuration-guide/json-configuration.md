# JSON Configuration

While the configuration can be edited with the UI, some users may find it easier or simpler to edit the JSON directly. The file is named `config.json` and is wherever the configuration is on your OS:

| **Windows** | **Mac** | **Linux** |
| :--- | :--- | :--- |
| `C:\Users\<you>\AppData\Roaming\TagViewer` | `~/Library/Application Support/TagViewer` | `$XDG_CONFIG_HOME/TagViewer or ~/.config/TagViewer` |

{% hint style="warning" %}
If you don't understand the JSON language, don't edit this file. Introducing syntax errors can cause unexpected behavior. If TagViewer is able to detect the error \(typically if there is a gross syntax error, as opposed to the wrong data type; don't rely on it\), you will be notified and the file will not be written to until the error is rectified or the file is deleted.
{% endhint %}

## Interface Configuration

### `navWidth` and `filtersWidth`

The width of the Files sidebar as well as the Properties/Filters sidebar can be controlled within the UI by dragging the sidebars's inner edge, and is stored in these keys. This property is stored as a number in pixels, and has no default \(it will be unset in the CSS, and the renderer will set their widths as appropriate\).

{% code title="config.json" %}
```javascript
"navWidth": 350 // the width of the Files sidebar will be 350 pixels.
"filtersWidth": 400 // the width of the Properties/Filters sidebar will be 400px.
```
{% endcode %}

### `noSaveWidths`

In addition, you can choose to not save this data to the configuration. If set to true, the saved widths will _not_ be deleted from the configuration and instead will be used as "defaults" on each restart, enabling you to set the widths however you like but have them revert to a normal value you've set upon restarting. If you'd like to completely revert this setting to default, you can remove the `navWidth` and `filterWidth` keys. This property's default is `false` \(save the widths\).

{% code title="config.json" %}
```javascript
"noSaveWidths": true // don't save the widths.
```
{% endcode %}

### `theme`

This key is the theme of the interface. Currently only two options \(`default-light` and `default-dark`\) are supported, but in the future support may be added for plugins which could offer custom themes and to set the theme to a custom theme, this key will be used. Thus, the default themes are prefixed as such. The default value for this property is `"default-light"`.

{% code title="config.json" %}
```javascript
"theme": "default-dark" // use the dark theme.
"theme": "my-custom-theme" // enable a custom theme (when support is added).
```
{% endcode %}

### `themeOverrides` and `themeInjections`

Especially while support for custom themes hasn't been implemented, but also when it has, you may want to override some aspects of a theme. That is the purpose of these keys. In `themeOverrides`, you can set the CSS variables \(more information on the names and values in the Developer Guide under Theming\), while in `themeInjections`, you directly write CSS rules to inject into the page. \(The rules are injected at the end of the body, so they override any existing rules in the default stylesheet.\) The default value for `themeOverrides` is `{}` \(no overrides\), while for `themeInjections` it's `""` \(no injections\).

{% code title="config.json" %}
```javascript
"themeOverrides": {
  "--main-background-color": "#123456" // override the main background color
},
"themeInjections": "input { color: green; }" // make the inputs have green text
```
{% endcode %}

## General Configuration

### `offerPrevLocation`

Whether to offer the most recently opened TagSpace for reopening in the central menu before a TagSpace is opened. Default is `true` \(offer it if it's available\).

{% code title="config.json" %}
```javascript
"offerPrevLocation": false // do not offer it even if one is saved
```
{% endcode %}

### `resumeSessionOnRestart`

Whether TagViewer should automatically reopen the previously open TagSpace after TagViewer is restarted. Default is `false` \(do not resume the session\). Note that this is independent of `offerPrevLocation`; that is, even if `offerPrevLocation` is set to `false`, the session will still be resumed automatically.

{% code title="config.json" %}
```javascript
"resumeSessionOnRestart": true // resume session on restart if one is saved
```
{% endcode %}

### `defaultTags`

The default tags shown when you're creating a new TagSpace. The defaults are "Favorite", "Low-Quality", and "Important". For no defaults, give an empty array \(`[]`\).

{% code title="config.json" %}
```javascript
"defaultTags": [["Foo", "#aabbcc"], ["Bar", "#ddeeff"]]
// defaults are "Foo" (color #aabbcc) and "Bar" (color #ddeeff)
// format: [[name, color (6 digit hex)]...]
```
{% endcode %}

### `defaultProps`

The default properties shown when you're creating a new TagSpace. The default is "Description" of type "String" \(though Title, Size, and Resolution are also included, they are immutable and required so they are not included in the value for this property\). For no defaults, give an empty array \(`[]`\).

```javascript
"defaultProps": [["Favorite?", "Boolean"], ["Location", "String"]]
// defaults are "Favorite?" of type "Boolean" and "Location" of type "String"
// format: [[name, type (String, Number, or Boolean)]...]
```

## Slideshow Configuration

### `slideshowInterval`

The time to show each item in the slideshow, in milliseconds. Default is `1000` \(one second\).

{% code title="config.json" %}
```javascript
"slideshowInterval": 2000 // two seconds
```
{% endcode %}

### `endSlideshowOnFSExit`

Whether to end the slideshow after exiting fullscreen mode. Default is `true` \(end the slideshow\).

{% code title="config.json" %}
```javascript
"endSlideshowOnFSExit": false // don't end the slideshow
```
{% endcode %}

### `stopSlideshowAtEnd`

Whether to stop the slideshow when the last item in the TagSpace is reached. Default is `false` \(wrap around back to the first item\).

{% code title="config.json" %}
```javascript
"stopSlideshowAtEnd": true // end slideshow at last item
```
{% endcode %}



