# cryosparc

In GCP
1. IAM & Admin --> Quotas --> Metrics, select None, then search GPU (all regions) --> Location, select None, then select Global
Compute Engine API GPUs (all region) 
submit request to increase 1 

2. https://cryosparc.com/docs/reference/install/
Follow the instructions

3. Check the OS from the terminal 

```
lsb_release -a

No LSB modules are available.
Distributor ID: Debian
Description:    Debian GNU/Linux 9.9 (stretch)
Release:        9.9
Codename:       stretch
```


3. Install Cuda

https://cloud.google.com/compute/docs/gpus/add-gpus
```
#!/bin/bash
 echo "Checking for CUDA and installing."
 # Check for CUDA and try to install.
 if ! dpkg-query -W cuda-10-0; then
   curl -O http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-repo-ubuntu1804_10.0.130-1_amd64.deb
   dpkg -i ./cuda-repo-ubuntu1804_10.0.130-1_amd64.deb
   apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
   apt-get update
   apt-get install cuda-10-0 -y
 fi
# Enable persistence mode
nvidia-smi -pm 1
```
I run this but throw an error "superuser". So install line by line. 
```
sudo apt-get install dirmngr
```

