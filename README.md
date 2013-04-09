Plex-GDM-IntentService
======================

A simple Android IntentService which searches for Plex Media Servers' on the local network using their custom "Good Day Mate" service.

You'll need the following permissions:

* android.permission.INTERNET
* android.permission.ACCESS_WIFI_STATE

The service itself broadcasts 2 local messages that you'll need to intercept in your app:

* GDMService.MSG_RECEIVED
This is broadcasted whenever a plex media server discovery packet is received.
The received packet is sent with the broadcast as an extra called "data".
The IP Address (of the PMS) that sent the packet is available as an extra called "ipaddress".

Both values are Strings. You'll have to parse them for the relevant information.

* GDMService.SOCKET_CLOSED
This is broadcasted after a timeout has been reached (2000ms) on the listening socket. Essentially no more servers have responded. Once you've received this you can rest assured all packets have been received.

More detailed information to follow.
