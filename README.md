# testcontainers-python-and-conu

## Blogpost I follow during this video
The original blogpost with the steps to setup Python testcontainers with ConU on Fedora.
https://fedoramagazine.org/test-containers-python-conu/

Was posted on Fedora Magazine https://fedoramagazine.org/

## Python
- Python was version 3.9 initially. I used the alternatives to configure another version of Python on my system. Information on Alternatives https://linuxconfig.org/how-to-switch-between-python-versions-on-fedora-linux
- Installing python 3.7 ```sudo dnf install -y python3.7```
  - After that I called the following command
  ```
  sudo alternatives --install /usr/bin/python python /usr/bin/python3.7 1
  sudo alternatives --install /usr/bin/python python /usr/bin/python3.9 2
  ```
  - and then to choose the default one.
  ```
  sudo alternatives --config python 
  ```
  - Later discovered that the symlink of /usr/bin/python3 was still pointing to python3.9, removed the link and created the link to just python so that the alternatives has effect. 
  ```
  cd /usr/bin
  sudo rm /usr/bin/python3
  (y)
  sudo ln -s python3 python
  ```
  
## Docker
- To add $user to the docker group so you can run docker commands as a regular user.
```
sudo groupadd docker
sudo usermod -aG docker $USER
```
- Logout
- I restarted the docker service just in case. ```sudo service docker restart```
- See: https://docs.docker.com/engine/install/linux-postinstall/

# References
- Testcontainers.org: https://www.testcontainers.org/
- Container Utilities: https://github.com/user-cont/conu
- Error docker (cgroups: cannot found cgroup mount destination: unknown): https://github.com/docker/for-linux/issues/219#issuecomment-375160449
- (Not in the video but found it valueble to share) https://conu.readthedocs.io/en/latest/reference/fixtures_index.html
