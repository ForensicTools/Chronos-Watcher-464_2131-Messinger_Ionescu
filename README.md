Chronos Watcher
===============

Efficient, real time monitoring of file system activity, accomplished by intercepting syscalls responsible for opening and editing files.

This tool has potential for forensic and anti-forensic applications: bring your own hat. :)

Compatibility at this time (Nov 2013) will be guaranteed for Mac OS X 10.8.5, further testing will occur in the future and the OS Compatibility list will be ammended.

This tool is developed for Mac OS X, but it should be possible to port to Linux.

OS Compatibility
----------------

1. OS X 10.5.8

Functionality
-------------

This tool must be run as root.

This tool will begin monitoring the file system for changes at runtime. It does not scan the file system, or do anything inefficient of that sort.

File access and modify times will be saved prior to any changes being committed to the file's metadata. Events affecting MAC times will be recorded to a log file, times.log. You can keep a shell open with `tail -f times.log` to get a realtime view of all touched files while Chronos Watcher runs.

The log file (times.log) will provide a timeline of all modified files during that Chronos Watcher session. This is the forensic application.

When you are done monitoring with Chronos Watcher, you will have the option to revert the MAC times of all the touched files. This is the anti-forensic application.

Future Functionality
--------------------

This application has a lot of potential for expansion, some of the proposed features are

1. Selectively choose which files' MAC times to revert
2. Revert MAC times based on input from Chronos Watcher log file, independent of current Chronos Watcher session
3. Revert MAC times based on body file (generated by tools like fls, ils, and mac-robber)
4. A GUI might be nice

Usage
-----

TODO

Invoke Chronos Watcher with `chronos`, make sure you have root priviledges when you do this.

See the included manpage for more information.

Documentation
-------------

This software includes a manpage, chronos.8. It should be installed in the manpage directory for ease of use.

Run the following command as root
```bash
install -g 0 -o 0 -m 0644 chronos.8 /usr/share/man/man8
```

You should now be able to access it by doing
```bash
man chronos
```

Alternatively, if you don't wish to go through the trouble of installing it, you can still view it by giving `man` the path to the manpage file.
```bash
man ./chronos.8
```

License
-------

This program and all source code is released under GPLv2. Please see LICENSE included with this distribution for more information.

Authors
-------

Developed by two RIT students, Fall 2013.

* [Vlad Ionescu](https://github.com/vladionescu)
* [Joe Messinger](https://github.com/joem3921)
