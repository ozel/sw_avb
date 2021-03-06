AVB Software Stack
..................

:Stable release:  Development

:Status:  Reference Software

:Maintainer:  davidn@xmos.com

:Description:  Audio over Ethernet Software (AVB)


Key Features
============

* 1722 Packet listener and talker
* 1722 MAAP multicast reservation protocol
* MRP,MMRP,MVRP,SRP 802.1 protocols
* PTP server and protocol
* Audio interface for I2S and TDM
* Clock recovery and interface to PLL clock source

To Do
=====

* Finish 1722.1 beta
* Empty talker audio fifo of packets when going from idle to active
* Firmware update over the wire

Firmware Overview
=================

This is an implementation of the AVB transport stream protocol carrying audio data. It includes a PTP time
server to provide a stable wallclock reference, clock recovery to synchronize listener audio to talker audio
codecs.  It includes implementations of the Stream Reservation Protocol for conveying AVB stream reservation
information through 802.1 network infrastructure.

Known Issues
============

* Multiple talkers and listeners on the same network can cause clock instability in eack other
* The listener does not respond to the withdrawal of a talker advertise message
* The talker may transmit some invalid timestamps 

Required Repositories
================

* sc_ethernet git\@github.com:xcore/sc_ethernet.git
* sc_xtcp git\@github.com:xcore/sc_xtcp.git
* sc_xlog git\@github.com:xcore/sc_xlog.git
* sc_i2c git\@github.com:xcore/sc_i2c.git
* xcommon git\@github.com:xcore/xcommon.git

Support
=======

Supported by XMOS Ltd.
