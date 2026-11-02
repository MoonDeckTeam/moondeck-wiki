It is possible to run a script before MoonDeck Runner is started.

This can be done by specifying a custom "python execuable" in the MoonDeck settings where in reality it is just a hook-script which executes python in the end.

An example of such a hook-script can be seen below:
```
#!/bin/bash

# MoonDeck passes all the data to the "MoonDeck Runner" (python script) via ENV.
# They are all prefixed with a "MOONDECK_" keyword. What you do with this information
# is up to you...
# This is also a good place to execute some tasks before the script is executed,
# e.g. change SteamDeck settings and so on.

# Once you're done, continue with the python script execution.
exec /usr/bin/python "$@"
```

Once you have a script you want to use, simply make it executable via `chmod +x` and specify a path to it in the MoonDeck settings.
