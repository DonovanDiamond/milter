# Fork

This library is a fork of phalaaxx/milter, which is a fork of andybalholm/milter.

This fork makes the following changes to the original library:

- When the milter sends a reject, it will not close the session. This was done
because postfix still keeps the SMTP session open after a reject, which means
more commands may be issued to postfix which the milter will miss.

- Added the Abort method to the Milter interface and ensured it is called by
the session handler when the MTA sends an abort command.

Below is the original README.md from the phalaaxx/milter library:

[![GoDoc](https://godoc.org/github.com/phalaaxx/milter?status.svg)](https://godoc.org/github.com/phalaaxx/milter)

# milter
A Go library for milter support heavily inspired from https://github.com/andybalholm/milter
For example how to use the library see https://github.com/phalaaxx/pf-milters - postfix milter for email classification with bogofilter and blacklisting messages which contain files with executable extensions.
