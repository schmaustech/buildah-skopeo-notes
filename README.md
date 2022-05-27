# buildah-skopeo-notes

~~~bash
$ podman login registry.access.redhat.com
Username: bschmaus
Password: 
Login Succeeded!

$ podman login poc-registry-quay-quay-poc.apps.kni20.schmaustech.com --tls-verify=false
Username: openshift
Password: 
Login Succeeded!
$ skopeo inspect docker://registry.access.redhat.com/ubi8/ubi
{
    "Name": "registry.access.redhat.com/ubi8/ubi",
    "Digest": "sha256:f85554c06bf8f4d712a25d4c0373491f7c7437c578a434c8111c6dfce738559a",
    "RepoTags": [
        "8.5-239.1651231664",
        "8.4-213",
        "8.4-211",
        "8.5-236.1647448331-source",
        "8.4-206.1626828523-source",
        "8.6-754",
        "8.4-199",
        "8.4-211-source",
        "8.5-200-source",
        "8.4-203.1622660121-source",
        "8.1-328",
        "8.5-214",
        "8.2-265-source",
        "8.5-239.1651231664-source",
        "8.2-347-source",
        "8.2-299.1592810498",
        "8.5-226-source",
        "8.0-154",
        "8.0",
        "8.3",
        "8.2",
        "8.0-208",
        "8.4",
        "8.3-297.1618432833-source",
        "8.6",
        "8.2-347",
        "8.2-265",
        "8.3-227-source",
        "8.5-200",
        "8.4-206-source",
        "8.0-122",
        "8.3-297.1618432833",
        "8.4-209-source",
        "8.0-126",
        "8.0-129",
        "8.2-299.1594117625",
        "8.3-297-source",
        "8.2-299.1594117625-source",
        "8.1",
        "8.4-203",
        "8.2-299-source",
        "8.3-199",
        "8.4-209",
        "8.5-236.1648460182-source",
        "8.3-297",
        "8.4-203.1622660121",
        "8.1-406-source",
        "8.3-199-source",
        "8.1-397-source",
        "8.5-239-source",
        "8.6-754-source",
        "8.1-408-source",
        "8.5",
        "8.1-277",
        "8.5-236.1648460182",
        "8.4-203-source",
        "8.3-227",
        "8.5-226",
        "8.2-299.1592810498-source",
        "8.5-214-source",
        "8.5-236.1647448331",
        "8.0-199",
        "8.5-236",
        "8.4-213-source",
        "8.4-206.1626828523",
        "8.5-239",
        "8.4-199-source",
        "8.5-226.1645809065-source",
        "8.2-299",
        "8.3-289",
        "8.4-206",
        "8.5-236-source",
        "8.5-226.1645809065",
        "8.1-408",
        "8.1-406",
        "8.3-289-source",
        "8.1-397",
        "latest"
    ],
    "Created": "2022-05-03T08:39:27.737951Z",
    "DockerVersion": "1.13.1",
    "Labels": {
        "architecture": "x86_64",
        "build-date": "2022-05-03T08:36:31.336870",
        "com.redhat.build-host": "cpt-1002.osbs.prod.upshift.rdu2.redhat.com",
        "com.redhat.component": "ubi8-container",
        "com.redhat.license_terms": "https://www.redhat.com/en/about/red-hat-end-user-license-agreements#UBI",
        "description": "The Universal Base Image is designed and engineered to be the base layer for all of your containerized applications, middleware and utilities. This base image is freely redistributable, but Red Hat only supports Red Hat technologies through subscriptions for Red Hat products. This image is maintained by Red Hat and updated regularly.",
        "distribution-scope": "public",
        "io.k8s.description": "The Universal Base Image is designed and engineered to be the base layer for all of your containerized applications, middleware and utilities. This base image is freely redistributable, but Red Hat only supports Red Hat technologies through subscriptions for Red Hat products. This image is maintained by Red Hat and updated regularly.",
        "io.k8s.display-name": "Red Hat Universal Base Image 8",
        "io.openshift.expose-services": "",
        "io.openshift.tags": "base rhel8",
        "maintainer": "Red Hat, Inc.",
        "name": "ubi8",
        "release": "754",
        "summary": "Provides the latest release of Red Hat Universal Base Image 8.",
        "url": "https://access.redhat.com/containers/#/registry.access.redhat.com/ubi8/images/8.6-754",
        "vcs-ref": "f1ee6e37554363ec55e0035aba1a693d3627fdeb",
        "vcs-type": "git",
        "vendor": "Red Hat, Inc.",
        "version": "8.6"
    },
    "Architecture": "amd64",
    "Os": "linux",
    "Layers": [
        "sha256:f70d60810c69edad990aaf0977a87c6d2bcc9cd52904fa6825f08507a9b6e7bc",
        "sha256:545277d800059b32cf03377a9301094e9ac8aa4bb42d809766d7355ca9aa8652"
    ],
    "Env": [
        "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
        "container=oci"
    ]
}

$ skopeo copy --authfile=/home/bschmaus/quay-merged-pull-secret.json --all docker://registry.access.redhat.com/ubi8/ubi docker://poc-registry-quay-quay-poc.apps.kni20.schmaustech.com/openshift/ubi --dest-tls-verify=false --remove-signatures --dest-username=openshift --dest-password=PMDYUD2ITCYNUEN6M9DVCSR50BOXEF69
Copying 4 of 4 images in list
Copying image sha256:88b67c5c3d7bc900e0dc77c058601c618758e3c79d468ebfe446e91c45657b46 (1/4)
Copying blob f70d60810c69 skipped: already exists  
Copying blob 545277d80005 skipped: already exists  
Copying config 1264065f6a done  
Writing manifest to image destination
Storing signatures
Copying image sha256:d76aca6a7d77690e4c05a6129de6fe1e788f5c59950eaffdbb86108adaaae95b (2/4)
Copying blob 0f6e46285dbe skipped: already exists  
Copying blob b88304ccd20b skipped: already exists  
Copying config 33e584026d done  
Writing manifest to image destination
Storing signatures
Copying image sha256:683cace406dbb9b311152a838406170b1f089e7bd64c973afafc1e6f273926d8 (3/4)
Copying blob 0a1c03975291 skipped: already exists  
Copying blob 3535894aee57 skipped: already exists  
Copying config 321596c103 done  
Writing manifest to image destination
Storing signatures
Copying image sha256:81461825a6cd8d7833c39e509d051927b2eef1ce98817c2cee045306398bf319 (4/4)
Copying blob fa7d3d3fed5d skipped: already exists  
Copying blob e8d8cab5ec85 skipped: already exists  
Copying config d2d494a576 done  
Writing manifest to image destination
Storing signatures
Writing manifest list to image destination
Storing list signatures


$ skopeo copy --authfile=/home/bschmaus/quay-merged-pull-secret --all docker://registry.access.redhat.com/ubi8/ubi dir:./ubi
Getting image list signatures
Copying 4 of 4 images in list
Copying image sha256:88b67c5c3d7bc900e0dc77c058601c618758e3c79d468ebfe446e91c45657b46 (1/4)
Getting image source signatures
Checking if image destination supports signatures
Copying blob f70d60810c69 done  
Copying blob 545277d80005 done  
Copying config 1264065f6a done  
Writing manifest to image destination
Storing signatures
Copying image sha256:d76aca6a7d77690e4c05a6129de6fe1e788f5c59950eaffdbb86108adaaae95b (2/4)
Getting image source signatures
Checking if image destination supports signatures
Copying blob 0f6e46285dbe done  
Copying blob b88304ccd20b done  
Copying config 33e584026d done  
Writing manifest to image destination
Storing signatures
Copying image sha256:683cace406dbb9b311152a838406170b1f089e7bd64c973afafc1e6f273926d8 (3/4)
Getting image source signatures
Checking if image destination supports signatures
Copying blob 3535894aee57 done  
Copying blob 0a1c03975291 done  
Copying config 321596c103 done  
Writing manifest to image destination
Storing signatures
Copying image sha256:81461825a6cd8d7833c39e509d051927b2eef1ce98817c2cee045306398bf319 (4/4)
Getting image source signatures
Checking if image destination supports signatures
Copying blob e8d8cab5ec85 done  
Copying blob fa7d3d3fed5d done  
Copying config d2d494a576 done  
Writing manifest to image destination
Storing signatures
Writing manifest list to image destination
Storing list signatures

~~~

~~~bash
$ buildah from registry.access.redhat.com/ubi8/ubi-init
ubi-init-working-container

$ buildah run ubi-init-working-container -- yum -y install httpd
Updating Subscription Management repositories.
Unable to read consumer identity
Subscription Manager is operating in container mode.
Red Hat Enterprise Linux 8 for x86_64 - AppStream (RPMs)                                                                                                                           9.4 MB/s |  44 MB     00:04    
Red Hat Enterprise Linux 8 for x86_64 - BaseOS (RPMs)                                                                                                                              9.5 MB/s |  47 MB     00:05    
Red Hat Universal Base Image 8 (RPMs) - BaseOS                                                                                                                                     711 kB/s | 781 kB     00:01    
Red Hat Universal Base Image 8 (RPMs) - AppStream                                                                                                                                  2.9 MB/s | 2.9 MB     00:00    
Red Hat Universal Base Image 8 (RPMs) - CodeReady Builder                                                                                                                           26 kB/s |  17 kB     00:00    
Dependencies resolved.
===================================================================================================================================================================================================================
 Package                                     Architecture                    Version                                                               Repository                                                 Size
===================================================================================================================================================================================================================
Installing:
 httpd                                       x86_64                          2.4.37-47.module+el8.6.0+14529+083145da.1                             rhel-8-for-x86_64-appstream-rpms                          1.4 M
Installing dependencies:
 apr                                         x86_64                          1.6.3-12.el8                                                          rhel-8-for-x86_64-appstream-rpms                          130 k
 apr-util                                    x86_64                          1.6.1-6.el8                                                           rhel-8-for-x86_64-appstream-rpms                          105 k
 httpd-filesystem                            noarch                          2.4.37-47.module+el8.6.0+14529+083145da.1                             rhel-8-for-x86_64-appstream-rpms                           41 k
 httpd-tools                                 x86_64                          2.4.37-47.module+el8.6.0+14529+083145da.1                             rhel-8-for-x86_64-appstream-rpms                          108 k
 mailcap                                     noarch                          2.1.48-3.el8                                                          rhel-8-for-x86_64-baseos-rpms                              39 k
 mod_http2                                   x86_64                          1.15.7-5.module+el8.6.0+13996+01710940                                rhel-8-for-x86_64-appstream-rpms                          155 k
 redhat-logos-httpd                          noarch                          84.5-1.el8                                                            rhel-8-for-x86_64-baseos-rpms                              29 k
Installing weak dependencies:
 apr-util-bdb                                x86_64                          1.6.1-6.el8                                                           rhel-8-for-x86_64-appstream-rpms                           25 k
 apr-util-openssl                            x86_64                          1.6.1-6.el8                                                           rhel-8-for-x86_64-appstream-rpms                           27 k
Enabling module streams:
 httpd                                                                       2.4                                                                                                                                  

Transaction Summary
===================================================================================================================================================================================================================
Install  10 Packages

Total download size: 2.0 M
Installed size: 5.5 M
Downloading Packages:
(1/10): apr-util-openssl-1.6.1-6.el8.x86_64.rpm                                                                                                                                     90 kB/s |  27 kB     00:00    
(2/10): apr-util-bdb-1.6.1-6.el8.x86_64.rpm                                                                                                                                         80 kB/s |  25 kB     00:00    
(3/10): apr-util-1.6.1-6.el8.x86_64.rpm                                                                                                                                            298 kB/s | 105 kB     00:00    
(4/10): httpd-filesystem-2.4.37-47.module+el8.6.0+14529+083145da.1.noarch.rpm                                                                                                      402 kB/s |  41 kB     00:00    
(5/10): apr-1.6.3-12.el8.x86_64.rpm                                                                                                                                                935 kB/s | 130 kB     00:00    
(6/10): httpd-tools-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64.rpm                                                                                                           1.0 MB/s | 108 kB     00:00    
(7/10): mailcap-2.1.48-3.el8.noarch.rpm                                                                                                                                            409 kB/s |  39 kB     00:00    
(8/10): mod_http2-1.15.7-5.module+el8.6.0+13996+01710940.x86_64.rpm                                                                                                                1.3 MB/s | 155 kB     00:00    
(9/10): redhat-logos-httpd-84.5-1.el8.noarch.rpm                                                                                                                                   264 kB/s |  29 kB     00:00    
(10/10): httpd-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64.rpm                                                                                                                5.2 MB/s | 1.4 MB     00:00    
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                              3.0 MB/s | 2.0 MB     00:00     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                           1/1 
  Installing       : apr-1.6.3-12.el8.x86_64                                                                                                                                                                  1/10 
  Running scriptlet: apr-1.6.3-12.el8.x86_64                                                                                                                                                                  1/10 
  Installing       : apr-util-bdb-1.6.1-6.el8.x86_64                                                                                                                                                          2/10 
  Installing       : apr-util-1.6.1-6.el8.x86_64                                                                                                                                                              3/10 
  Running scriptlet: apr-util-1.6.1-6.el8.x86_64                                                                                                                                                              3/10 
  Installing       : apr-util-openssl-1.6.1-6.el8.x86_64                                                                                                                                                      4/10 
  Installing       : httpd-tools-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64                                                                                                                             5/10 
  Installing       : redhat-logos-httpd-84.5-1.el8.noarch                                                                                                                                                     6/10 
  Installing       : mailcap-2.1.48-3.el8.noarch                                                                                                                                                              7/10 
  Running scriptlet: httpd-filesystem-2.4.37-47.module+el8.6.0+14529+083145da.1.noarch                                                                                                                        8/10 
  Installing       : httpd-filesystem-2.4.37-47.module+el8.6.0+14529+083145da.1.noarch                                                                                                                        8/10 
  Installing       : mod_http2-1.15.7-5.module+el8.6.0+13996+01710940.x86_64                                                                                                                                  9/10 
  Installing       : httpd-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64                                                                                                                                  10/10 
  Running scriptlet: httpd-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64                                                                                                                                  10/10 
  Verifying        : apr-util-openssl-1.6.1-6.el8.x86_64                                                                                                                                                      1/10 
  Verifying        : apr-util-bdb-1.6.1-6.el8.x86_64                                                                                                                                                          2/10 
  Verifying        : apr-util-1.6.1-6.el8.x86_64                                                                                                                                                              3/10 
  Verifying        : apr-1.6.3-12.el8.x86_64                                                                                                                                                                  4/10 
  Verifying        : httpd-filesystem-2.4.37-47.module+el8.6.0+14529+083145da.1.noarch                                                                                                                        5/10 
  Verifying        : httpd-tools-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64                                                                                                                             6/10 
  Verifying        : httpd-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64                                                                                                                                   7/10 
  Verifying        : mod_http2-1.15.7-5.module+el8.6.0+13996+01710940.x86_64                                                                                                                                  8/10 
  Verifying        : mailcap-2.1.48-3.el8.noarch                                                                                                                                                              9/10 
  Verifying        : redhat-logos-httpd-84.5-1.el8.noarch                                                                                                                                                    10/10 
Installed products updated.

Installed:
  apr-1.6.3-12.el8.x86_64                                               apr-util-1.6.1-6.el8.x86_64                                     apr-util-bdb-1.6.1-6.el8.x86_64                                           
  apr-util-openssl-1.6.1-6.el8.x86_64                                   httpd-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64          httpd-filesystem-2.4.37-47.module+el8.6.0+14529+083145da.1.noarch         
  httpd-tools-2.4.37-47.module+el8.6.0+14529+083145da.1.x86_64          mailcap-2.1.48-3.el8.noarch                                     mod_http2-1.15.7-5.module+el8.6.0+13996+01710940.x86_64                   
  redhat-logos-httpd-84.5-1.el8.noarch                                 

Complete!

$ buildah run ubi-init-working-container -- systemctl enable httpd
Created symlink /etc/systemd/system/multi-user.target.wants/httpd.service → /usr/lib/systemd/system/httpd.service.

$ buildah copy ubi-init-working-container index1.html /var/www/html/index.html
3a79f01b50068a5f403c0338e494cd20e5c293d883d25cafa62313e83d3ae865

$ buildah config --port 80 --cmd "/usr/sbin/init" ubi-init-working-container

$ buildah commit ubi-init-working-container el-httpd1
Getting image source signatures
Copying blob 5bf135c4a0de skipped: already exists  
Copying blob 773711fd02f0 skipped: already exists  
Copying blob 135fb4ad5daa skipped: already exists  
Copying blob 49e369a8dc39 done  
Copying config deb602c894 done  
Writing manifest to image destination
Storing signatures
deb602c8948097a1a8c6e789beba2775ca58ac4d85de4c25c5794e067eaba8dc

$ podman images
REPOSITORY                                                           TAG         IMAGE ID      CREATED        SIZE
localhost/el-httpd1                                                  latest      deb602c89480  5 seconds ago  452 MB
registry.access.redhat.com/ubi8/ubi-init                             latest      0d9e0c1523d9  3 weeks ago    240 MB
registry.access.redhat.com/ubi8/ubi                                  latest      1264065f6ae8  3 weeks ago    225 MB
poc-registry-quay-quay-poc.apps.kni20.schmaustech.com/ubi8/ubi       latest      1264065f6ae8  3 weeks ago    225 MB
poc-registry-quay-quay-poc.apps.kni20.schmaustech.com/openshift/ubi  latest      1264065f6ae8  3 weeks ago    225 MB

$ podman tag localhost/el-httpd1 poc-registry-quay-quay-poc.apps.kni20.schmaustech.com/openshift/el-httpd1

$ podman push poc-registry-quay-quay-poc.apps.kni20.schmaustech.com/openshift/el-httpd1 --tls-verify=false --authfile=/home/bschmaus/quay-merged-pull-secret.json 
Getting image source signatures
Copying blob 135fb4ad5daa done  
Copying blob 49e369a8dc39 done  
Copying blob 5bf135c4a0de skipped: already exists  
Copying blob 773711fd02f0 skipped: already exists  
Copying config deb602c894 done  
Writing manifest to image destination
Storing signatures
~~~

~~~bash

~~~
