Role Name
=========

[Elasticsearch](http://www.elasticsearch.org), [Logstash](http://logstash.net), [Kibana](http://www.elasticsearch.org/overview/kibana/) role. Set up a logging server, basically.

There is a switch to swap out Logstash for [FluentD](http://www.fluentd.org) though. See Variables section below.


Requirements
------------

You need EPEL configured for supporting packages.
You also need a running httpd - there is a default docroot assumed, which you can override with the elk_docroot variable.


Role Variables
--------------

These are the defaults set. Do not change them in defaults/, but set in role call, -e, or inventory variables.

    elk_java: java-1.7.0-openjdk
    elk_es: https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.3.2.noarch.rpm
    elk_ls: https://download.elasticsearch.org/logstash/logstash/packages/centos/logstash-1.4.2-1_2c0f5a1.noarch.rpm
    elk_fluentd_pkgs: td-agent
    elk_kibana: https://download.elasticsearch.org/kibana/kibana/kibana-3.1.0.tar.gz
    elk_kbver: 3.1.0
    elk_docroot: /var/www/html
    elk_logger: logstash

elk_logger can either be 'logstash' or 'fluentd' - which means you can choose the log aggregator you require.

Dependencies
------------

* Running httpd - docroot defaults to /var/www/html. Override this with elk_docroot.
* EPEL yumrepo.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: elk, elk_logger: fluentd }

License
-------

BSD

Author Information
------------------

Mark Phillips <mark@devopsguys.com>

