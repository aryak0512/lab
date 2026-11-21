(base) aryak@Aryaks-MacBook-Pro lab % ./gradlew app:build app:taskTree
Calculating task graph as no cached configuration is available for tasks: app:build app:taskTree
```adlanguage
> Task :app:processResources SKIPPED
> Task :app:processTestResources SKIPPED
> Task :app:compileJava SKIPPED
> Task :app:classes SKIPPED
> Task :app:jar SKIPPED
> Task :app:startScripts SKIPPED
> Task :app:compileTestJava SKIPPED
> Task :app:distTar SKIPPED
> Task :app:distZip SKIPPED
> Task :app:testClasses SKIPPED
> Task :app:assemble SKIPPED
> Task :app:test SKIPPED
> Task :app:check SKIPPED
> Task :app:build SKIPPED
> Task :app:taskTree
```
------------------------------------------------------------
Project ':app'
------------------------------------------------------------
```adlanguage
:app:build
+--- :app:assemble
|    +--- :app:distTar
|    |    +--- :app:jar
|    |    |    +--- :app:classes
|    |    |    |    +--- :app:compileJava
|    |    |    |    \--- :app:processResources
|    |    |    \--- :app:compileJava *
|    |    \--- :app:startScripts
|    |         \--- :app:jar *
|    +--- :app:distZip
|    |    +--- :app:jar *
|    |    \--- :app:startScripts *
|    \--- :app:jar *
\--- :app:check
\--- :app:test
+--- :app:classes *
+--- :app:compileJava *
+--- :app:compileTestJava
|    +--- :app:classes *
|    \--- :app:compileJava *
\--- :app:testClasses
+--- :app:compileTestJava *
\--- :app:processTestResources
```

(*) - subtree omitted (printed previously)
Add --repeat to allow printing a subtree of the same task more than once.

To see task dependency tree for a specific task, run gradlew <project-path>:<task> <project-path>:taskTree [--depth <depth>] [--with-inputs] [--with-outputs] [--with-description] [--repeat]
Executions of all tasks except for taskTree are skipped. They are used for building the task graph only.

BUILD SUCCESSFUL in 570ms
1 actionable task: 1 executed
Configuration cache entry stored.