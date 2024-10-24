# Sublinks Docker

This repo will hold docker-compose.yml files to run Sublinks for demo/live
as well as local dev purposes

***CURRENT STATUS: Please note, this repo currently holds configuration files
intended for development purposes only. As we get closer to our initial MVP
release we will provide sample files for use in a live site.***

## Preface

[] surrounding a paramter indicates the parameter is optional. The brackets
themselves should not be included. Eg:

```bash
docker-compose -f docker-compose.<area>.yml up [-d]
```

In the above command, you can run it either as:

```bash
docker-compose -f docker-compose.<area>.yml up
```

or

```bash
docker-compose -f docker-compose.<area>.yml up -d
```

The `-d` is optional. It means "detach" and will cause the command prompt to
return almost immediately but the docker images will continue running in the
background.  If you use this method, you must run
`docker-compose -f docker-compose.<area>.yml down` in order to teardown the
environment (NOTE: You can also use `stop` instead of `down` if you only want
to stop the containers but not actually tear them down. This is useful if you
plan to bring the containers back up and want their current state to be
remembered. Otherwise, `down` will ensure the next time you launch the
containers they are brought up in a "clean" state)

## Demo Site

NOTE: Demo site has been removed for now. We will add it back in once we have
a more stable version of the site to show off.

## Frontend Dev

Run `docker-compose -f docker-compose.frontend.yml up [-d]`

## Backend Dev

Run `API_HOST=host.docker.internal docker-compose -f docker-compose.backend.yml up [-d]`
OR to run the Sublinks UI (currently experimental), run:
`UI=sublinks API_HOST=host.docker.internal docker-compose -f docker-compose.backend.yml up [-d]`

## Federation Dev

Run `docker-compose -f docker-compose.federation.yml up [-d]`
