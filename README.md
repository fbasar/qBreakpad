#qBreakpad

[![Build status](https://travis-ci.org/buzzySmile/qBreakpad.svg?branch=master)](https://travis-ci.org/buzzySmile/qBreakpad)




qBreakpad is Qt library to use google-breakpad crash reporting facilities (and using it conviniently).
Supports
* Windows (but crash dump decoding will not work with MinGW compiler)
* Linux
* MacOS X

How to use
----------------
* Clone repository recursively
```bash
$ git clone --recursive https://github.com/buzzySmile/qBreakpad.git
```
* Build qBreakpad static library (qBreakpad/handler/)
* Include "qBreakpad-handler.pri" to your target Qt project
```c++
include(libs/qBreakpad/qBreakpad-handler.pri)
```
* Setup linking with "qBreakpad-handler" library
```c++
QMAKE_LIBDIR += $$OUT_PWD/submodules/breakpad/handler
LIBS += -lqBreakpad-handler
```
* Use ```QBreakpadHandler``` singleton class to enable automatic crash dumps generation on any failure; example:
```c++
#include <QBreakpadHandler.h>

int main(int argc, char* argv[])
{
    ...
    QBreakpadInstance.setDumpPath(QLatin1String("crashes"));
    ...
}
```
* Read Google Breakpad documentation to know further workflow

Getting started with Google Breakpad
----------------
https://chromium.googlesource.com/breakpad/breakpad/+/master/docs/getting_started_with_breakpad.md

Detail description about integration `qBreakpad` into your system and platform you could find in **[Wiki](https://github.com/buzzySmile/qBreakpad/wiki)**.


----------------
Ekstra Yapılacaklar

breadpad projesini aşağıdaki linkten indirebilirsin

address : https://chromium.googlesource.com/breakpad/breakpad/

Linux syscall support projesini aşağıdaki linkten indirebilirsin

address : https://chromium.googlesource.com/linux-syscall-support

```bash
$ git clone https://chromium.googlesource.com/breakpad/breakpad
$ git clone https://chromium.googlesource.com/linux-syscall-support
```

Eğer -> qBreakpad\third_party\breakpad boş ise veya qBreakpad\third_party\lss boş ise yukarıdaki linklerden indirip yerli yerine koyabilirsin.
Ayriyeten extras içinede koyuldu oradan işlem yapılabilir.
