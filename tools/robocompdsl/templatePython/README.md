```
[[[cog

import sys
sys.path.append('/opt/robocomp/python')

import cog
def A():
	cog.out('<@@<')
def Z():
	cog.out('>@@>')
def TAB():
	cog.out('<TABHERE>')
def SPACE(i=0):
	s = ''
	if i>0:
		s = str(i)
	cog.out('<S'+s+'>')
includeDirectories = theIDSLPaths.split('#')
from parseCDSL import *
component = CDSLParsing.fromFile(theCDSL, includeDirectories=includeDirectories)

]]]
[[[end]]]
```
#
```
[[[cog
A()
cog.out(' ' + component['name'])
]]]
[[[end]]]
```
Intro to component here


## Configuration parameters
As any other component,
```
[[[cog
A()
cog.out(' *' + component['name'] + '* ')
Z()
]]]
[[[end]]]
```
needs a configuration file to start. In

    etc/config

you can find an example of a configuration file. We can find there the following lines:

    EXAMPLE HERE

    
## Starting the component
To avoid changing the *config* file in the repository, we can copy it to the component's home directory, so changes will remain untouched by future git pulls:

    cd

```
[[[cog
A()
cog.out(' <' + component['name'] + ' \'s path> ')
Z()
]]]
[[[end]]]
```

    cp etc/config config
    
After editing the new config file we can run the component:

    bin/

```
[[[cog
A()
cog.out(component['name'] + ' ')
Z()
]]]
[[[end]]]
```

    --Ice.Config=config
