# python-basic-setup

### To run program

In your terminal type `python bin/practice`

It will print to the screen `Hello World`

### How it links together

##### Bin
Our bin file is our executable. However in order for it to read as pythong we need to first set it's environment.

```#!usr/bin/env python```

Afterwards, we need to tell this file about our environment file. We need two things in order to do this.
```
import os
import sys
```

import `os` gives us functions to be able to get the current working directory, which gives us the root of our project.
```
cwd = os.getcwd()
```

We set this as a variable `cwd` so that we can then use it to get the directory for `config`
```
sys.path.append(cwd + "/config")
```

Now that this file knows aout that directory, we can then import all of the functions that the environment.rb knows about
```
from environment import *
```

This imports all of the functions and ready to be used within our bin directory.

##### Environment.py
We again need to import our os and sys so since our environment file is going to contain all of our lib file's functions
```
import os
import sys

# get current directory
cwd = os.getcwd()
# add the lib directory to the pathing for imports
sys.path.append(cwd + "/lib")
```

This allows us to have access to the lib directory.

Then any files that we want to have access to we can then import over all the functions in that file.
```
# imports all of the practice functions from the practice.py file
from practice import *
```

This gives us access in our bin file the function we wrote in our `practice.py` file.
```
def greeting():
  print "Hello World!"
```

We are now able to call it in our `bin/practice`.
```
greeting()
```
