A Simple Java client for REST
=============================

The Rest Client offers a simplified interface to an underlying implementation of an HTTP client, 
specifically geared to operate REST resources.

Maven dependency
----------------
	<dependency>
		<groupId>smartrics.restfixture</groupId>
		<artifactId>smartrics-RestClient</artifactId>
		<version>2.0</version>
	</dependency>

Links
-----

*Release*: https://oss.sonatype.org/content/repositories/releases/smartrics/restfixture/smartrics-RestClient/

*Continuous Integration*: http://jenkins.fazend.com:8080/job/RestClient

*Maven Site*: http://jenkins.fazend.com:8080/job/RestClient/site/index.html

Getting started
---------------

The current implementation of '''RestClient''' wraps Apache HttpClient 3.1.

	org.apache.commons.httpclient.HttpClient = new org.apache.commons.httpclient.HttpClient();
	RestClient client = new RestClientImpl(httpClient);
	client.setBaseUrl("http://mydomain.com:8080/orders");
	RestRequest request = new RestRequest().setMethod(RestRequest.Method.Get).setResource("/resource");
	RestResponse response = client.execute(request);
	String body = response.getBody();
	Header h = response.getHeader("Content-Type");
	// ...
	