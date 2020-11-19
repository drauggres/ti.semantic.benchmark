# Results

## Load Time

* `parse`:
  * Read `semantics.colors.json`
  * parse it
  * fetch each color with `Ti.UI.fetchSemanticColor`
* `create`: `Ti.UI.create*`
* `layout`: first `postlayout` event on the window

![android](results/time/android.png)

![ios](results/time/ios.png)


## Memory

### Java heapdump size.

Collected with command:
* `adb shell 'am dumpheap PID /data/local/tmp/dump.hprof'`

Note: in SDK 8.2.1 for Android `Ti.UI.fetchSemanticColor` returns `string` value; in 9.2.2 - ColorProxy (?)

![android](results/memory_java/android.png)

### JavaScript heap snapshot size.

Value reported in `Statistics` as **`Total`** for a heap snapshot. 
![android](results/memory_js/android.png)

Size of an exported heap snapshot (not the actual heap size!).
![ios](results/memory_js/ios.png)
