# Why?

I needed a plain VM based on a given stemcell so I could tinker around and develop a release from the ground up in an iterative way. Unfortunately I found no easy way to set up such a plain VM. However, while searching the web I read about phantom jobs, got the idea and built a release for a phantom job.

# How?

Clone this repo. Target director. Upload desired stemcell to your BOSH director. Adjust deployment manifest accordingly.
Note: if your creating the release for the first time, it will ask you for a name. Just call it phantom.
```
$ bosh create release --force --with-tarball
$ bosh upload release --rebase
$ bosh deployment examples/phantom.yml
$ bosh deploy
$ bosh ssh phantom
```

# Notes

The example deployment manifest works for BOSH Lite. You may want to adjust the manifest for use on a real BOSH.
