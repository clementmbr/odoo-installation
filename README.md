# Intro

Step by step tutorial to install Odoo on a server with :

* docker
* docky
* ak
* pipx
* nginx

## Justification

### [docker](https://docs.docker.com/get-started/)&[docky](https://github.com/akretion/docky)

Because we don't want any differences between our development and production environments. [Docky](https://github.com/akretion/docky) is a custom python app for launching Odoo environments anywhere with no headache, using [docker-compose](https://docs.docker.com/compose/).

### [ak](https://github.com/akretion/ak)

Another custom python app based on Acsone's [git-aggregator](https://github.com/acsone/git-aggregator). Used to update all your Odoo non-native modules  from their respectives repositories, branch or PR in github.

### [pipx](https://pypi.org/project/pipx/)

Because ak and docky could have different python requirements and should be used together. Avoid headaches and install them with [pipx](https://pypi.org/project/pipx/) instead of pip. Each app installed with pipx will run with its own environment.

### [nginx](https://www.nginx.com/)

A classical reverse proxy to serve your Odoo project through your own domain.





