# Shutdown while installing or updating package

While updating a package, my laptop unexpectedly ran out of battery. After reconnecting the charger and rebooting, I tried to continue the update, however, the process failed with an error, and the package could not be installed.

**What caused the error:** When my laptop lost power during the package update, the build process was interrupted. This likely left temporary build files, partial installations, or corrupt package states in the AUR helper’s cache (I was using *paru* at the time). So when I later retried the update, paru tried to reuse those broken or incomplete build artifacts — resulting in errors because the environment wasn't clean.

To resolve this, you can force a clean rebuild of the package:
```
paru -S --rebuild [package]
```

Here I used *paru*, but the same can be done if you use *yay*.

**How forcing a rebuild fixes it:** When you use `--rebuild`, you’re telling *paru* (or *yay*) to ignore any previously cached build data and rebuild the package from scratch. It fetches the latest version of the PKGBUILD, re-downloads sources if needed, and compiles everything fresh — avoiding whatever leftover mess caused the failure.
