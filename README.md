The Earthbound Battle Background live wallpaper is exactly what its name implies: a live wallpaper for Android 2.1 (or higher) that shows the battle backgrounds from the SNES RPG Earthbound.

Every battle background is composed of two layers, each with 326 possible styles (including "blank"). Thus, there are 326 * 326 = 106,276 possible different background combinations. Obviously, this many don't exist in the game--they only _potentially_ exist.

It's pretty damn hard to find out which battle backgrounds correspond to which enemies. You can review the list of enemies matched with known battle backgrounds to try and get your favorite on the *Suggested Layers* option. If you discover a new one, please, email me and I'll add it to the list, giving you full credit! You can find a COMPLETE list of potential battle backgrounds by going here: [http://eblw.galaxyclock.com](http://eblw.galaxyclock.com).

### How it Works

The data for each of the 326 styles are bundled within the app. Tiles are constructed from various memory addresses in Earthbound game data. To create the distortion effect, the following function is used:

    Offset (y, t) = A sin ( F*y + S*t )

where:

*  _y_ is the vertical coordinate being transformed
*  _t_ is time that's elapsed
*  _A_ is the amplitude
*  _F_ is the frequency
*  _S_ is the speed or frameskip of the transformation

Offest refers to the _y_ direction of the shift at a given time _t_.

There are also three types of distortions that use the result of the Offset function:

*  Horizontal translations, where each line is shifted left by the given number of pixels
*  Horizontal interlaced translations, where every other line is shifted right by the given number of pixels
*  Vertical compression translations, where each line is shifted up or down by the given number of pixels

Different backgrounds use different distortion effects.

### Building

First, make sure you call `ndk-build` in the root directory. Then, just run the Android application through Eclipse.

### License

This app is in no way endorsed or affiliated by Nintendo, Ape, HAL Laboratory, Shigesato Itoi, e.t.c. It's licensed under the GPL License, Version 3. You may obtain a copy of the License at [http://www.gnu.org/licenses](http://www.gnu.org/licenses).

### Donations

This app _is_ available on the Android Market: [https://market.android.com/details?id=com.miadzin.livewallpaper.earthbound&feature=search_result](https://market.android.com/details?id=com.miadzin.livewallpaper.earthbound&feature=search_result).

If this code inspires or helps you at all, please feel free to buy it from the market. Thank you!

### Credits

I am entirely indebted to Mr. Accident of forum.starmen.net for the original battle background generation code, which was a C# project that uses the battle backgrounds as Windows screensavers. He also provided me with help along the way, and as far as I'm aware, he discovered the math behind it all, including the entire Offset function calculation. *This port would be nothing without him.*

Additionally, everyone who worked on PK Hack or was even associated with the project. It's incredible to witness such a powerful community of fans who have turned a wonderful game inside-out over and over again.

And thank you to the people on StackOverflow and the NDK Group who answered my repetitive questions with patience and clarity.

### Discredits

Java, for _still_ not having the concept of unsigned types. You made my app difficult.