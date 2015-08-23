# PS4 SDK
An open source PlayStation 4 SDK.

## Design
At the moment, it is primarily focused on the kernel. For example, [all semaphore system calls have been implemented](https://github.com/CTurt/PS4-SDK/blob/master/source/semaphore.c), from 549 to 556.

However, using function pointers and the `RESOLVE` macro, we can call functions from other modules. For example, [the socket functions](https://github.com/CTurt/PS4-SDK/blob/master/source/network.c) from `libSceNet.sprx`.

The [hello](https://github.com/CTurt/PS4-SDK/blob/master/examples/hello/source/main.c) example shows how to initialise libc, and perform system calls.

## Support
Whilst the SDK isn't capable of most basic functionality yet, such as displaying graphics, or receiving controller input, it is a solid foundation which will be improved upon over time.

## Building and installing
Just run `make` on the `PS4-SDK` directory to build the library.

Then create an environment variable called, `PS4SDK` which points to the base directory of the repository, using the Unix path style; for example:

    /C/Users/Chris/Documents/GitHub/PS4-SDK

You must make sure that your compiler supports the System V AMD64 ABI calling convention. PS4-SDK relies on this for compatibility with Sony's functions and system calls.