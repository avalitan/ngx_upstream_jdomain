ngx_upstream_jdomain
====================

An asynchronous domain name resolve module for nginx upstream

Installation(Static):

	./configure --add-module=/path/to/this/directory
	make
	make install

Installation(Dynamic):

	./configure --add-dynamic-module=/path/to/this/directory
	make modules
	cp objs/ngx_http_upstream_jdomain_module.so /path/to/nginx/modules
	
Remember to add the module to your modules config:

	load_module modules/ngx_my_module.so;

Usage:

	upstream backend {                                                                              
		jdomain www.baidu.com; #port=80                                                             
		#jdomain www.baidu.com port=8080; #port=8080
	}                                                                                               
                                                                                                    
Jdomain: 

	* Syntax: jdomain <domain-name> [port=80] [max_ips=20] [retry_off]                              
	* Context:    upstream                                                                          
	* port:       Backend's listening port.                                                         
	* max_ips:    IP buffer size.                                                                   
	* retry_off:  Do not retry if one IP fails. 

See http://wiki.nginx.org/HttpUpstreamJdomainModule for details.

Author
======

wdaike <wdaike@163.com>, Baidu Inc.

Copyright & License
===================

This module is licenced under the BSD License.
Copyright (C) 2014-2014, by wdaike <wdaike@163.com>, Baidu Inc.

All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

