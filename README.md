# awesome-qt6

migrating apps from qt5 to qt6 is non-trivial due to changed api, so only few apps use qt6 for now

## C++

C++ apps using qt6. also qt is written in C++

* [qt6 repos on github](https://github.com/search?q=qt6&type=Repositories)
* [qt6 topic on github](https://github.com/topics/qt6)

### projects using QMake build system

qmake is deprecated in favor of cmake, but still supported in qt6

we can convert qmake projects to cmake projects with [pro2cmake.py](https://code.qt.io/cgit/qt/qtbase.git/tree/util/cmake/pro2cmake.py) from qtbase.
this only works for simple qmake projects, more complex qmake projects must be converted by hand

* [pyqt6](https://www.riverbankcomputing.com/software/pyqt)
  * implemented in C++ and QML
  * download from pypi: https://pypi.org/project/PyQt6/
  * pyqt is built with [pyqt-builder](https://www.riverbankcomputing.com/software/pyqt-builder/), which uses qmake
    * [self.qmake = self._find_exe('qmake')](https://www.riverbankcomputing.com/hg/PyQt-builder/file/tip/pyqtbuild/builder.py#l65)
  * [Pyqtdeploy plan for the end of qmake?](https://www.riverbankcomputing.com/pipermail/pyqt/2020-April/042834.html)
    * "PyQt6 will require SIP v6 which will include a cmake builder (to replace 
      the qmake builder in PyQt-builder)."
  * [Bug#964127: plplot: Please switch from sip4 to sip5](https://www.mail-archive.com/search?l=debian-bugs-dist@lists.debian.org&q=subject:%22Bug%23964127%5C%3A+plplot%5C%3A+Please+switch+from+sip4+to+sip5%22&o=newest&f=1)
    * "My approach abuses the SIP's build system. sip-build generates a .pro file
      for qmake and tries to run qmake by default. I decided that it's better to
      rely on CMake to do the actual compilation (e.g. so that all compiler flags
      are honored), so I pass --no-build to sip-build and then copy the .cpp and
      .h files it generated to CMake's build directory, then let CMake build them."
* https://github.com/luebking/qarma cli tool to show simple gui dialogs (clone of vanity for gtk)
  * qt5compat dependency
* https://github.com/dail8859/NotepadNext
* https://github.com/KinectToVR/k2vr-application
* https://github.com/trialuser02/qt6gtk2

### projects using CMake build system

* https://github.com/telegramdesktop/tdesktop Telegram Desktop messaging app
  * using cmake_helpers https://github.com/desktop-app/cmake_helpers/blob/master/external/qt/qt6/CMakeLists.txt
* https://github.com/easymodo/qimgv image viewer
* https://github.com/strawberrymusicplayer/strawberry music player, based on amarok and clementine, similar to foobar2000
* http://qmmp.ylsoftware.com/ music player, similar to winamp or xmms
* https://github.com/trialuser02/qt6ct Qt6 Configuration Tool
* https://github.com/QtExcel/QXlsx spreadsheet editor
* https://github.com/euler0/mini-cmake-qt cmake project template, requires QML
* https://github.com/stiglers-eponym/BeamerPresenter pdf viewer
* https://github.com/Bollos00/LibreMines minesweeper game
* https://github.com/Constantor/fractals3d fractals viewer
* https://github.com/matijakevic/mcircuit digital logic circuit simulator
* https://github.com/zaghaghi/pixel-model-maker pixel art editor
* https://github.com/juzzlin/Heimer mindmaps, diagrams, notes
* https://github.com/qbittorrent/qBittorrent torrent client
* https://github.com/tsujan/Kvantum qt theme engine, based on SVG graphics
* https://github.com/rncbc/drumkv1 drumkit sampler
  * https://github.com/rncbc/padthv1 synthesizer
* https://github.com/fcitx/fcitx-qt5 input method framework
* https://git.jami.net/savoirfairelinux/jami-libclient p2p messaging
* https://github.com/desktop-app/libdbusmenu-qt Qt implementation of the DBusMenu protocol. The DBusMenu protocol makes it possible for applications to export and import their menus over DBus.
* https://poppler.freedesktop.org/ PDF rendering library

## python

pyside6 = qt6 bindings for python

* https://download.qt.io/official_releases/QtForPython/pyside6/ source code

apps using qt6 via [pyside6](https://github.com/topics/pyside6) in python:

* [pyside6 repos on github](https://github.com/search?p=3&q=pyside6&type=Repositories)
* [pyside6 topic on github](https://github.com/topics/pyside6)
* https://github.com/UGLYclown999/Apollo music player
* https://github.com/persepolisdm/persepolis download manager (frontend to aria2)
* https://github.com/mherrmann/fbs Create Python GUIs with Qt in minutes
* https://github.com/runesc/PPG Python Package Generator: python project generator?
* https://github.com/AnTAVR/Python3_Qt6_template python project template

## related

* https://download.qt.io/official_releases/qt/ source code for qt, qmake, qml (qtdeclarative), pyside, shiboken
* https://www.qt.io/blog/qt-roadmap-for-2021
* https://github.com/gentoo/qt/pull/224 qt6 in gentoo linux
* https://archlinux.org/packages/extra/x86_64/qt6-base/ qt6 in arch linux. see qt6 apps in `Required By`
  * ~~drumkv1~~
  * ~~fcitx-qt6~~
  * ~~jami-libclient~~
  * ~~kvantum~~
  * ~~libdbusmenu-qt6~~
  * ~~padthv1~~
  * poppler-qt6
  * ~~python-pyqt6~~
  * ~~qbittorrent~~
  * ~~qbittorrent-nox~~ (headless qbittorrent)
  * qcoro-qt6
  * qjackctl
  * qmidictl
  * qmidinet
  * ~~qmmp~~
  * qpwgraph
  * qsampler
  * qscintilla-qt6
  * qsynth
  * qtkeychain-qt6
  * qtractor
  * qtspell
  * qxgedit
  * samplv1
  * ~~shiboken6~~ (pyside6)
  * ~~strawberry~~
  * synthv1
  * fcitx5-qt
  * fcitx-qt5
  * libdbusmenu-qt
  * poppler
  * qcoro

## qt5 and older

* https://github.com/JesseTG/awesome-qt
* https://github.com/mikalv/awesome-qt-qml
* https://github.com/fffaraz/awesome-qt
* https://github.com/JulienGrv/awesome-python-qt
* https://github.com/insideqt/awesome-qt
