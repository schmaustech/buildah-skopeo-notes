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






~~~
