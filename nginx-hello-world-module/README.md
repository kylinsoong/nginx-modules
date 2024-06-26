# Hello World Module for Nginx

## This example come from https://github.com/perusio/nginx-hello-world-module.

## Introduction

This module serves as a learning exercise for me, and hopefully for
others too, when doing [Nginx](http://nginx.org) module development. 

I [stole](http://dominicfallows.com/2011/02/20/hello-world-nginx-module-3/)
the code and added some notes using mostly Evan Miller's
[Nginx Module Development Guide](http://www.evanmiller.org/nginx-modules-guide.html). Also
helpful is the
[translation](http://antoine.bonavita.free.fr/nginx_mod_dev_en.html)
of Vhalery Kholodov's
[Nginx Module Guide](http://www.grid.net.ru/nginx/nginx-modules.html)
done by [Antoine Bonavita](http://antoine.bonavita.free.fr/) that also
mantains a [Nginx Discovery](http://www.nginx-discovery.com/) blog to
document his journey on Nginx module development.

## Installation

   1. Configure Nginx adding this module with:
          
          Static Module : ./configure (...) --add-module=/path/to/nginx-hello-world-module
          Dynamic Module: ./configure (...) --add-dynamic-module=/path/to/nginx-hello-world-module
       
   2. Build Nginx as usual with `make`.
   
   3. Configure the module. There's only one directive `hello_world`
      that is supported in the **location** context only.
      
      Example:
          
          location = /test {
             
             hello_world;
          
          }

      Now doing something like:
          
          curl -i http://example.com/test
          
      should return the **hello world** string as the response body.

