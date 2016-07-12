# mongo-tools
## Introduction
you can use this tool to sync db between mongodbs (compatible with mongo 3.0)
## How to build
compile with mongo(2.4)
  1. clone mongo and checkout r2.4.0 tag
  2. cp sync.h and sync.cpp to `src/mongo/tools/`
  3. cp SConstruct to `src/mongo/` (make our file could be compile)
  4. scons tools

## Other Tips
mongo(2.4) can not be compiled successful in my env, just change the `mongo/SConstruct` and `mongo/src/third_party/v8/SConscript`, delete the `-Werror` flags, then it does work
