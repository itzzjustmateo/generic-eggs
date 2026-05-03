# CMake Language (C / C++ / C#)

This egg is designed to build and run generic CMake-based projects supporting **C, C++ and C#**. Users can pull their own source code from a GitHub repository or upload their own files directly.

It compiles the project using CMake and then runs the resulting binary defined by the configuration.

---

## Configuration

The server will remain in a `starting` state until the startup detection pattern matches output from the application. You must update the detection text so that Pterodactyl can correctly detect when the application is running.

This is important because different projects may output different startup messages.

---

## Startup Detection

You can define multiple values to mark the server as running. This is useful when working with different projects or build outputs.

Example:

```json
{
  "done": [
    "Build finished",
    "Application started",
    "Server running"
  ]
}
```

---

## Notes

* Requires a valid `CMakeLists.txt` in the project root.
* The build process uses a `build/` directory inside the container.
* The executable name must match the `EXECUTABLE_NAME` variable.
* Supports C, C++ and C# depending on installed toolchain and CMake configuration.
* Make sure all required dependencies are handled by your project or installation script.

---

## Important

If your application does not start correctly:

* Check your CMake configuration
* Verify the executable target name
* Ensure all dependencies are installed during build
* Confirm the startup detection text matches your pr
