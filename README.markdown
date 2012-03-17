# nginsane #
*en jin sane*



## Overview ##

This is an experimental project that aims to lower the barrier to entry 
for developers interested in using the nginx Web server. It tries to 
accomplish this by distilling and organizing information about nginx's 
core and module configuration settings. The information is conveniently 
formatted as a collection of configuration files, thus allowing 
developers to import this project's files directly into their nginx 
configuration directory. 



## Project Goals and Design Principles ##

### Inline Documentation ###

After the initial installation of nginx, the first task a developer 
faces is configuring nginx by editing the nginx.conf file, usually 
located at /etc/nginx/nginx.conf. Currently, the content of the 
nginx.conf file that ships with the software is not immediately useful, 
as it requires the developer to look up the various directives in 
nginx's online documentation.

Nginsane will attempt to address this issue by bringing the documentation 
into the configuration file itself. Nginsane precedes each nginx 
directive with a comment block that provides relevant information about 
the directive, for example:

- syntax
- context
- default values
- accepted values
- required arguments
- optional arguments
- brief description
- (compatability)*
- (module)**
- (status)***

\* Could be eliminated if nginsane became part of the nginx build, 
because presumably nginsane would only document directives that are 
compatible (and non-deprecated) for its corresponding nginx build/release. 

\** Could be eliminated if nginsane files convey this information 
through file names and directory structure. 

\*** I grabbed this info type from [Apache's 
docs](http://httpd.apache.org/docs/current/mod/directive-dict.html#Statu 
s), but it may not be necessary or useful to have in a config file. 
Frankly, I haven't worked with nginx enough to know at this point. 



### Sane Defaults ###

To the extent possible, nginsane will provide safe defaults and make 
it reasonably difficult for inexperienced developers to shoot themselves 
in the foot. 



### Built-in Best Practices ###

To the extent possible, nginsane will provide information and working 
examples that follow current best practices and adhere to established 
conventions. 



### WWAD - What Would Apache Do? ###

Nginsane acknowledges, appreciates, and respects the incredible amount 
of work that has gone into the [Apache HTTP 
Server](http://httpd.apache.org/) project and the [Apache HTTP Server 
Documentation](http://httpd.apache.org/docs-project/) sub-project. 
Nginsane also acknowledges that many (most?) new nginx users already 
have some level of experience or familiarity with the Apache webserver. 
Therefore, nginsane will implement its own features with a deliberate 
awareness of how Apache achieves similar functionality. New practices 
and conventions will not be established arbitrarily if Apache has 
already established a usable system. 



## Links ##

- [Nginx documentation](http://nginx.org/en/docs/) - the official source of information used to build nginsane.

- [PHP function definition syntax](http://www.php.net/manual/en/about.prototypes.php) - inspiration for defining nginsane's syntax.

- [Apache Terms Used to Describe Directives](http://httpd.apache.org/docs/current/mod/directive-dict.html) - WWAD?

- [Nginx default configuration files](http://trac.nginx.org/nginx/browser/nginx/trunk/conf)

- [Apache default configuration files](https://svn.apache.org/repos/asf/httpd/httpd/trunk/docs/conf/)

- [Apache default installation directory structure](https://svn.apache.org/repos/asf/httpd/httpd/trunk/config.layout) - does nginx have something comparable to this? Couldn't find anything. It would certainly help automate a lot of this configuration file mumbo jumbo.

- [Nginx configuration file parser source](http://trac.nginx.org/nginx/browser/nginx/trunk/src/core/ngx_conf_file.c)

- [Nginx GNUmakefile](http://trac.nginx.org/nginx/browser/nginx/trunk/misc/GNUmakefile) - ideally, nginsane could become part of the nginx build process.

- [GNU Make makefile convensions](http://www.gnu.org/prep/standards/html_node/Makefile-Conventions.html#Makefile-Conventions) - if I'm to make an attempt to incorporate nginsane into the nginx build process, I'll probably need to learn GNU Make at some point.


