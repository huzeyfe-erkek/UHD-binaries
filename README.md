# UHD binaries for testing purposes

Debug version of UHD binaries must be used to debug USRP code, otherwise it will [crash](https://stackoverflow.com/questions/71692143/uhd-usrp-crash-in-debug-mode). Official Ettus releases doesn't contain debug builds and [compiling](https://files.ettus.com/manual/page_build_guide.html) it takes time. I am sharing UHD [v4.1.0.5](https://github.com/EttusResearch/uhd/tree/v4.1.0.5) builds for testing purposes. No source code has been changed except a one little tiny [error](https://github.com/EttusResearch/uhd/commit/61337817eb9c617db37fdbb16fb5f598e15a29a7) related to a test executable. 

REMINDER: Do NOT use these binaries for deployment. They come with ABSOLUTELY NO WARRANTY.

## Custom Parameters used in compiling
* Boost 1.79 is linked statically
* Libusb 1.0.26 is linked statically
* MSVC2019 and MSVC2017 is used
### Release mode
* UHD_LOG_CONSOLE_LEVEL, warning
* UHD_LOG_FASTPATH_DISABLE, false
* UHD_LOG_FILE, uhd.log
* UHD_LOG_FILE_LEVEL, warning
* UHD_LOG_MIN_LEVEL, warning
### Debug mode
* 3 different debug binaries exist
* Followings are common:
    * UHD_LOG_FASTPATH_DISABLE, false
    * UHD_LOG_FILE, uhdd.log
* Followings depend on the binary:
    * UHD_LOG_CONSOLE_LEVEL, {trace, debug, info}
    * UHD_LOG_FILE_LEVEL, {trace, debug, info}
    * UHD_LOG_MIN_LEVEL, {trace, debug, info}
