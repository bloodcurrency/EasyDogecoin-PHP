EasyDogecoin-PHP
===============

A simple class for making calls to Dogecoin's API using PHP.

Getting Started
---------------
1. Include easydogecoin.php into your PHP script:

	`require_once('easydogecoin.php');`
2. Initialize Dogecoin connection/object:

	`$dogecoin = new Dogecoin('username','password');`

	Optionally, you can specify a host, port and protocol (HTTP and HTTPS). Default is HTTP on localhost port 22555.

	`$dogecoin = new Dogecoin('username','password','localhost','22555','http');`
3. Make calls to dogecoind as methods for your object. Examples:

	`$dogecoin->getinfo();`
	`$dogecoin->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);`
	`$dogecoin->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');`

Additional Info
---------------
* When a call fails for any reason, it will return false and put the error message in $dogecoin->error

* The HTTP status code can be found in $dogecoin->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $dogecoin->response while the raw JSON is stored in $dogecoin->raw_response
