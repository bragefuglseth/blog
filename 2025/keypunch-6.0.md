# Keypunch 6.0

Spring is in the air, the snow is finally melting away here in the cold north, and [Keypunch](https://apps.gnome.org/Keypunch) is getting an update! Let's walk through all the new features and improvements together.

## Realistic Results

Up to now, Keypunch's measurements of typing performance have been rather primitive. For speed, it has just compared the total number of typed characters, both correct and incorrect, to the test duration. Likewise, the "correctness" rate is nothing more than the share of correct characters at the time of calculation. If you make a mistake and then correct it, it's not taken into account at all.

These calculations are easy to understand and interpret, but also omissive and potentially misleading. The one for speed in particular has caused some pretty [ridiculous result screens](https://github.com/bragefuglseth/keypunch/issues/85) because of its uncritical counting. Needless to say, this is not ideal.

I've gone a little back and forth with myself on how to move forward, and ended up overhauling both of the calculations: For speed, Keypunch now counts how many *correct* characters there are at the end of the test, while the correctness rate has been replaced with real accuracy, based on *all* operations that have changed the typed text rather than just the final result. The new calculations come with their own trade-offs, but in general I believe this is a change for the better.

## Frustration Relief

Learning to type is awfully hard. At least it was for me; sometimes it felt like I wasn't even in control of my own fingers. This made me furious, and my number-one coping mechanism was to go berserk with my keyboard and mash random keys in frustration. As one might guess, this did not help me progress, and I probably should just have gone for a walk or something instead.

To safeguard the poor souls who come after me, I'm introducing something I call *frustration relief*. The concept is simple: If Keypunch detects that you're randomly mashing your keyboard, it will cancel the test and provide a helpful piece of life advice. I can't understate how much I wish I had something like this a couple of years ago.

## Input Improvements

Being a text-centric app with multi-language support, Keypunch inevitably has to work with the many intricacies of digital text input. This includes the fact that the Unicode standard contains more than a dozen different space characters. For a while, Keypunch has supported entering regular spaces in the place of [non-breaking](https://en.wikipedia.org/wiki/Non-breaking_space) ones, and now the same is possible the other way around too. Notably, this is a significant improvement for users of the francophone [BÉPO](https://bepo.fr/) keyboard layout.

## Platform Improvements

This Keypunch release is based on the GNOME 48 runtime, which brings a bunch of external platform goodness to the app:

- The latest Adwaita styling
- Better adherence to system font settings
- Improved performance
- An "Other Apps" section in the about window

## Additional Artwork

## Circle

Keypunch is now part of [GNOME Circle](https://circle.gnome.org)! I'm happy and grateful to have another app of mine accepted into the program. For full transparency, I'm part of the Circle Committee myself, but Keypunch has been independently reviewed by two other committee members, namely [Tobias](https://tobiasbernard.com) and [Gregor](https://codeberg.org/gregorni). Thanks!

## Languages

Keypunch's international community has been hard at work lately, and I'm happy to report a solid upturn in language support.