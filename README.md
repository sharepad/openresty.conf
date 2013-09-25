openresty.conf
==============

Sample [openresty](http://openresty.org) configuration, inspired by the configuration used at [SharePad](http://sharepad.co).

## Features

- HTTP and HTTPS
- Performance improvements
- Mobile device detection
- Separate configuration for development and production

## Configuration files

The configuration is split between several files:

- `nginx.conf` is the main file
- `host.devel.conf` and `host.production.conf` are two versions of the host configuration. As the name suggests, one is used for development and the other for production
- `mobile.conf` is a mobile device detection based on the User-Agent
- `performance.conf` and `http_performance.conf` are performance optimization attempts. Your mileage may vary...

## How to use the configuration

1. Symlink `host.devel.conf` or `host.production.conf` to `host.conf`.
2. Create a Lua application containing at least two files: `init.lua` which contains code that is run once at server startup and one `index.lua` that contains at least a main controller named `main`.
3. Run with: `nginx -p PATH_TO_RUNTIME -c openresty.conf/nginx.conf`.
4. Add SSL keys in `openresty.conf`.

Most uppercase elements should be changed.

## Directory structure

- openresty.conf/ is where these configurations files are
- src/ contains the Lua code
- templates/ contains HTML templates, using for instance [slt2](https://github.com/henix/slt2).
