bird
=========

Installs and configures [BIRD](https://bird.network.cz).

Requirements
------------

None.

Role Variables
--------------

I have chosen _not_ to make this config modular since that would require too
much effort - almost every configuration would need its own filters etc.
anyway.

| Variable Name | Default Value | Description |
--------------- |---------------|--------------
`bird_config` | `""` | required, configuration for bird

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: bird
           bird_config: |
             router id 10.0.0.1;

             protocol kernel {
                 scan time 60;
                 import none;
                 export none;
             }

             protocol bgp {
                 import none;
                 export none;

                 local as 23456;
                 neighbor 10.0.0.2 as 23456;
             }

License
-------

BSD

Author Information
------------------

Find me on [GitHub](https://github.com/ThreeFx).
