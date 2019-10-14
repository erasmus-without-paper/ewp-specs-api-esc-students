European Student Card Students Send endpoint
============================================

* [What is the status of this document?][statuses]
* [See the index of all other EWP Specifications][develhub]


Summary
-------

This endpoint allows the HEI to add or update student data.


Request method and parameters
-----------------------------

 * Requests MUST be made with HTTP POST method. Servers SHOULD reject all other
   request methods.
   
 * The body of the request MUST contain a raw XML element described in the
   [send-request.xsd](send-request.xsd) schema. The request SHOULD also
   contain a matching `Content-Type` header (such as `text/xml`).

   (This endpoint is **NOT** using the regular `application/x-www-form-urlencoded`
   request format which most of other EWP endpoints do.)


Handling of invalid parameters
------------------------------

 * General [error handling rules][error-handling] apply.

 * If some of the required parameters (the ones with `minOccurs="1"`) are
   missing, or are passed in an invalid format, then the server MUST respond
   with HTTP 400 error response.

 * If the request contains unknown parameters (extra elements not allowed in
   the schema), then the server MUST ignore such parameters, and continue with
   processing the request.

 * If the requester does not cover the student HEI, then server MUST respond
   with HTTP 401 error response.
   
 * If the student with given identifier has anonymized his account, then the server
   MUST respond with HTTP 410 error response.

 * More requirements are described in the [send-request.xsd](send-request.xsd) file.


Response
--------

Servers MUST respond with a valid XML document described by the
[send-response.xsd](send-response.xsd) schema. See the schema annotations
for further information.


[develhub]: http://developers.erasmuswithoutpaper.eu/
[statuses]: https://github.com/erasmus-without-paper/ewp-specs-management#statuses
[error-handling]: https://github.com/erasmus-without-paper/ewp-specs-architecture#error-handling
