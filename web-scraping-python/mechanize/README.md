

login ubnt

```python

import cookielib 
import urllib2 
import mechanize 
 
# Browser 
br = mechanize.Browser() 
 
# Enable cookie support for urllib2 
cookiejar = cookielib.LWPCookieJar() 
br.set_cookiejar( cookiejar ) 
 
# Broser options 
br.set_handle_equiv( True ) 
br.set_handle_gzip( True ) 
br.set_handle_redirect( True ) 
br.set_handle_referer( True ) 
br.set_handle_robots( False ) 
 
# ?? 
br.set_handle_refresh( mechanize._http.HTTPRefreshProcessor(), max_time = 1 ) 
 
br.addheaders = [ ( 'User-agent', 'Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.9.0.1) Gecko/2008071615 Fedora/3.0.1-1.fc9 Firefox/3.0.1' ) ] 
 
# authenticate 
br.open('http://10.0.0.1/login.cgi') 
br.select_form(nr=0)
br[ "username" ] = 'tronicanet'
br[ "password" ] = '33404159'
res = br.submit() 
 
print "Success!\n"

```
