# Browser Security Handbook

- Written and maintained by [http://lcamtuf.coredump.cx/ Michal Zalewski](mailto:lcamtuf@google.com lcamtuf@google.com).
- Copyright 2008, 2009 Google Inc, rights reserved.
- Released under terms and conditions of the [http://creativecommons.org/licenses/by/3.0 CC-3.0-BY] license.

## Table of Contents

- [Part 1: Basic concepts behind web browsers](Part1.md)
- [Part 2: Standard browser security features](Part2.md)
- [Part 3: Experimental and legacy security mechanisms](Part3.md)

## Introduction

Hello, and welcome to the _Browser Security Handbook_!

This document is meant to provide web application developers, browser engineers, and information security researchers with a one-stop reference to key security properties of contemporary web browsers. Insufficient understanding of these often poorly-documented characteristics is a major contributing factor to the prevalence of several classes of security vulnerabilities.

Although all browsers implement roughly the same set of baseline features, there is relatively little standardization - or conformance to standards - when it comes to many of the less apparent implementation details. Furthermore, vendors routinely introduce proprietary tweaks or improvements that may interfere with existing features in non-obvious ways, and seldom provide a detailed discussion of potential problems.

The current version of this document is based on the following versions of web browsers:


| *Browser*                     | *Version*      | *Test date*  | *Usage*^*^ | *Notes* |
| ----------------------------- | -------------- | ------------ | ---------- | ------- |
| Microsoft Internet Explorer 6 | 6.0.2900.5512  | Feb 2, 2009  | 16%        |         |
| Microsoft Internet Explorer 7 | 7.0.5730.11    | Dec 11, 2008 | 11%        |         |
| Microsoft Internet Explorer 8 | 8.0.6001.18702 | Sep 7, 2010  | 28%        |         |
| Mozilla Firefox 2             | 2.0.0.18       | Nov 28, 2008 | 1%         |         |
| Mozilla Firefox 3             | 3.6.8          | Sep 7, 2010  | 22%        |         |
| Apple Safari                  | 4.0            | Jun 10, 2009 | 5%         |         |
| Opera                         | 9.62           | Nov 18, 2008 | 2%         |         |
| Google Chrome                 | 7.0.503.0      | Sep 7, 2010  | 8%         |         |
| Android  embedded browser     | SDK 1.5 R3     | Oct 3, 2009  | n/a        |         |

^*^ Approximate browser usage data based on public [http://marketshare.hitslink.com/browser-market-share.aspx?qprid=0 Net Applications] estimates for August 2010.

=Disclaimers and typographical conventions=

*Please note that although we tried to make this document as accurate as possible, some errors might have slipped through. Use this document only as an initial reference, and independently verify any characteristics you wish to depend upon. Test cases for properties featured in this document are [http://browsersec.googlecode.com/files/browser_tests-1.03.tar.gz freely available for download].*

The document attempts to capture the risks and security considerations present for general populace of users accessing the web with default browser settings in place. Although occasionally noted, the degree of flexibility offered through non-standard settings is by itself not a subject of this comparative study.

Through the document, red color is used to bring attention to browser properties that seem particularly tricky or unexpected, and need to be carefully accounted for in server-side implementations. Whenever status quo appears to bear no significant security consequences and is well-understood, but a particular browser implementation takes additional steps to protect application developers, we use green color to denote this, likewise. Rest assured, neither of these color codes implies that a particular browser is less or more secure than its counterparts.

=Acknowledgments=

_Browser Security Handbook_ would not be possible without the ideas and assistance from the following contributors:

- Filipe Almeida
- Brian Eaton
- Chris Evans
- Drew Hintz
- Nick Kralevich
- Marko Martin
- Tavis Ormandy
- Wladimir Palant
- David Ross
- Marius Schilder
- Parisa Tabriz
- Julien Tinnes
- Berend-Jan Wever
- Mike Wiacek

The document builds on top of previous security research by Adam Barth, Collin Jackson, Amit Klein, Jesse Ruderman, and many other security experts who painstakingly dissected browser internals for the past few years.
