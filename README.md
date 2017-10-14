Azkaban 3 [![Build Status](http://img.shields.io/travis/azkaban/azkaban.svg?style=flat)](https://travis-ci.org/azkaban/azkaban)
========

## Building from Source
--------------------

To build Azkaban packages from source, run:

```
./gradlew distTar
```

The above command builds all Azkaban packages and packages them into GZipped Tar archives. To build Zip archives, run:

```
./gradlew distZip
```

If not building for the first time, it's good to clean first:

```
./gradlew clean
```

## Documentation
-------------
This project add some new useful features, see below. If you want other function document, please go to [Azkaban Project Site](http://azkaban.github.io/) 
### Flow priority
------------
If in one Azkaban project, there are many flows, sometimes you need to determine which flow should be run at the higher priority.
In our case, you just need several steps to enable this feature.
##### Add schedule properties:
```python
flowOverride[internal.flow.priority.enable] = 'true'
flowOverride[internal.flow.max.number] = '4' #'4' is an example, it is determined by the requirements and resources of the environment.
```
##### Add flow priority in job profile
internal.flow.priority = 10 # Bigger the number is, higher the priority is. 



