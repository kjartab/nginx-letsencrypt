Nginx Letsencrypt
=========

Installs letsencrypt and sets up default configuration so that it is compatible with letsencrypt for setting up TLS certificates

Requirements
------------

In order for this to work you have to have a domain which is pointing to your server's IP address. The TLS certificates will work, but you won't be able to verify as the traffic won't be routed to your server.


Role Variables
--------------

This role includes a basic default configuration (default in NGINX installation) which will be copied over the existing one. It is preferrable to remove the default one and use your own setup. If you decide to do so, simply put a template, e.g. "server.j2" in your playbook's templates folder. The domain_name will be used for all relative paths, and you have to supply a configuration for your domain's NGINX site in a templates folder in your ansible folder.

- nginx_config_name: default
- nginx_web_root: /var/www/html
- domain_name: (e.g. example.com) - NO DEFAULT
- letsencrypt_email: (e.g. joe@gmail.com) - NO DEFAULT



Dependencies
------------

- kjartab.nginx

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars: 
        letsencrypt_email: joe@gmail.com
        domain_name: example.com
      roles:
        - role: kjartab.nginx
        - role: kjartab.nginx-letsencrypt

Directory structure:

provision/playbook.yaml
provision/templates/example.com.j2



License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
