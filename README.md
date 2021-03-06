#SpyDir
The purpose of the SpyDir tool is to extend the functionality of BurpSuite Proxy by automating Forced Browsing. The tool attempts to enumerate application endpoints via an input directory containing the application's source code. The tool provides an option to process files as endpoints, think: ASP, PHP, HTML, or parse files to attempt to enumerate endpoints via plugins, think: MVC. Users may opt to send the discovered endpoints directly to the Burp Spider.

##New Features
###Version 0.8.5
Implemented a mechanism to allow users to enable/disable plugins once they are loaded.

###Version 0.8.4
Added the ability to consume a single text file to parse previously processed/stored endpoints. This is mostly for folks that aren't comfortable with making Python plugins but still want to use the tool. 

Implemented the ability to persist the extension settings through open/close of Burp Suite.

##Plugins
Plugin requirements:

* Have a `get_name()` function that returns a string with the title of the plugin. 
* Have a `run()` function that accepts a list containing the lines of a source file. Return a `list`, `[]`, of endpoints.
* Have a `get_ext()` function that returns a string containing a comma delimited string of file extension type(s).

##Requirements
Jython2.7+ stand-alone jar file. Get it here: http://www.jython.org/downloads.html

##TODO
1. Modify the plugin return type to allow the specification of HTTP method passed to the spider. (This will require a custom HTTP request and handler)
2. Auto-resize window
3. Export data