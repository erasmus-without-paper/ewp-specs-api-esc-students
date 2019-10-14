European Student Card Students API
==================================

* [What is the status of this document?][statuses]
* [See the index of all other EWP Specifications][develhub]

Summary
-------

This document describes the **European Student Card Students API**.
It is assumed that this API is implemented by only one host managed by
the European Student Card team (ESC Router).
However, the specification itself does not limit the number of hosts.

It allows external clients to manage students data at the ESC Router
(add, check, update, delete).


Security
--------

This version of this API uses [standard EWP Authentication and Security, Version 2][sec-v2].
Server implementers choose which security methods they
support by declaring them in their Manifest API entry.

This API handles data which is considered private. Server implementers are
allowed to forbid less-secure methods of authentication and encryption for this
API (by dropping support for them). Currently, we leave it for the server
implementers to decide which methods are "secure enough". These recommendations
MAY change in the future.


Endpoints to be implemented
---------------------------

Server implementers MUST:

 * Implement the [`send` endpoint](endpoints/send.md).
 * *More endpoints to be added in the future*
 * Put the URLs of these endpoints in their [manifest file][discovery-api], as
   described in [manifest-entry.xsd](manifest-entry.xsd).

The details of each of these endpoints are described on separate pages of this
API specification (use the links above).


[develhub]: http://developers.erasmuswithoutpaper.eu/
[discovery-api]: https://github.com/erasmus-without-paper/ewp-specs-api-discovery
[sec-v2]: https://github.com/erasmus-without-paper/ewp-specs-sec-intro/tree/stable-v2
[statuses]: https://github.com/erasmus-without-paper/ewp-specs-management#statuses