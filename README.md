# Disclaimer - Work in progress

The repository you are looking into is work in progress.

It contains proof of concept and preview builds in development created in context of the [openDesk](https://gitlab.opencode.de/bmi/souveraener_arbeitsplatz/info) project.

The repository's content provides you with first insights into the containerized cloud IAM from Univention, derived from the UCS appliance.

This repository in particular is not intended as a stand-alone service, instead it serves as a base image layer for other services.

# container-nginx

This repository provides an nginx base container.

It bases on [ucs-base](https://gitlab.opencode.de/bmi/opendesk/component-code/crossfunctional/univention/ucs-base-image/) image.

Derived containers are:
- [univention-portal frontend](https://gitlab.opencode.de/bmi/opendesk/component-code/crossfunctional/univention/ums-univention-portal/-/blob/develop/frontend/Dockerfile?ref_type=heads)
- [container-store-dav](https://gitlab.opencode.de/bmi/opendesk/component-code/crossfunctional/univention/ums-container-store-dav)
- [Guardian management UI](https://gitlab.opencode.de/bmi/opendesk/component-code/crossfunctional/univention/ums-guardian/-/blob/main/management-ui/docker/Dockerfile?ref_type=heads)
