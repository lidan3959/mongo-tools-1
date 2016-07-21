# mongo-tools
## Introduction
you can use this tool to sync db between mongodbs (compatible with mongo 3.0)
## How to build
compile with mongo(2.4)
  1. clone mongo and checkout r2.4.9 tag
  2. cp sync.h and sync.cpp to `src/mongo/tools/`
  3. modify the line 632 from 'normalTools = [ "dump", "restore", "export", "import", "stat", "top", "oplog" ]' to 'normalTools = [ "dump", "restore", "export", "import", "stat", "top", "oplog", "sync" ]'
  4. comment the `-Werror` flags in the `mongo/SConstruct` and `mongo/src/third_party/v8/SConscript`, as follows
    
    ```cpp
    mongo/SConstruct
    713 #        env.Append( CCFLAGS=["-Werror", "-pipe"] )
    
    mongo/src/third_party/v8/SConscript
    50  #                       '-Werror',
    ```
    
  5. scons tools
