UIDevice+GPF_UID
================

What is it?
-----------
An Objective-C category that acts as a drop-in replacement for
`[[UIDevice currentDevice] uniqueIdentifier]`.  It creates an "install"
identifier -- a unique identifier that will remain the same across installs of
the application and in iTunes backups.  The identifier could potentially be
the same for multiple devices.

How does it work?
-----------------
It makes use of `CFUUIDCreate()` and stores the value generated in
`NSUserDefaults`.  This will work on iOS >= 2.0.

How do I use it?
----------------
1. Copy UIDevice+GPF_UID.[hm] to your project
2. `#include "UIDevice+GPF_UID.h"`
3. `[[UIDevice currentDevice] installIdentifier]`
4. Consider replacing all calls to `uniqueIdentifier` with calls to
`installIdentifier`.

