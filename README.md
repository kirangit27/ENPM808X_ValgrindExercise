# ENPM808X_ValgrindExercise

```
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scratch
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  valgrind ./build/app/shell-app
```

## Extra Credit:
What happens when the executable is linked statically?  
When an executable is linked statically, it means that all of the necessary libraries (dependencies) are included within the executable itself. This means that the program doesn't rely on external shared libraries during runtime.

Does Valgrind still detect those same bugs?
Though valgrind throws a ton of errors, when an executable is linked statically, it's not able to detect those same bugs. this can be observed from the HEAP SUMMARY output.

Why or why not?
Library-related Issues: Valgrind can't check for problems in libraries if they are statically linked, because it doesn't track library code that's not part of your executable.



