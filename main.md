# Android Development Guides

Here you will find little guides that will help you in your Android development journey :)

## Table of Contents
* [Hiding the System UI](#hiding-the-system-ui)

## Hiding the System UI

To remove navigation, status and title bars,
use [Immersive Fullscreen][immersive-fullscreen-link].

Use sticky mode if you want the UI to revert to being hidden
after the user makes it appears again.

You need to add calls to hide the system UI to the `onCreate()`
and `onWindowFocusChanged()` methods.

You should use the following method to hide the system UI:
```Java
private void hideSystemUI() {
    getWindow().getDecorView().setSystemUiVisibility(
            View.SYSTEM_UI_FLAG_LAYOUT_STABLE
                    | View.SYSTEM_UI_FLAG_LAYOUT_HIDE_NAVIGATION
                    | View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN
                    | View.SYSTEM_UI_FLAG_HIDE_NAVIGATION
                    | View.SYSTEM_UI_FLAG_FULLSCREEN
                    | View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY
    );
}
```
You should remove the `_STICKY` from the last flag if you do not want to use sticky mode.


[immersive-fullscreen-link]: https://developer.android.com/training/system-ui/immersive.html