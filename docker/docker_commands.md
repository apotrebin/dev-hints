## Install Docker engine
...

## Use docker without sudo
- sudo groupadd docker
- sudo gpasswd -a $USER docker
- newgrp docker
- (sudo usermod -aG docker $USER)