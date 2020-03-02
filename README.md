ansible-get-swift-objects
=========================

This role is used to get binaries, packages and containers from a `swift` 
service.

Requirements
------------

You must export some standard `openstack` variables needed by `swift` client.

Role Variables
--------------

* `swift_objects_package_state`: `present` or `latest`
* `cache_timeout`: APT cache value, used to decide if the cache must be updated

* `swift_objects_oci_repo_container`: `containers`, name of the container used 
to store the artifacts
* `swift_objects_packages_container`: `packages`, name of the container used to 
store the artifacts
* `swift_objects_binaries_container`: `binaries`, name of the container used to 
store the artifacts

* `swift_objects_oci_repo_transport`: `containers-storage`, transport method 
used by `skopeo`. By default the images are to be used by `podman`.

Dependencies
------------

N.A.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: ansible-get-swift-objects
      vars:
         packages_swift_container: packages
         binaries_swift_container: binaries
         oci_images_swift_container: containers

License
-------

GPL-3+

Author Information
------------------

Mathieu GRZYBEK
