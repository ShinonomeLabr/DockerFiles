# DockerFiles

## sample_nginx 

```
sudo docker run -d -p 80:80 --name website -v $PWD/website:/var/www/html/website jamtur01/nginx nginx
```

## smaple_facerec

```
sudo docker run -it --name=test_facerec -v $PWD/dataset:/var/faceRec/dataset/ -v $PWD/test:/var/faceRec/test/ facerec:v0.1 /bin/bash
python test.py shape_predictor_landmarks.dat face_rec_resnet_model.dat ../dataset/ ../test/test.jpg
```

## Installations

### Ubuntu:14.04
#### docker-ce

```
$ sudo apt-get update
$ sudo apt-get install \
	apt-transport-https \
	ca-certificates \
	curl \
	software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository \
	"deb [arch=amd64] https://download.docker.com/linux/ubuntu \
	$(lsb_release -cs) \
	stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce
```

#### docker-compose

```
$ sudo apt-get install python-pip
$ sudo pip install docker-compose
```

遇到错误 "ERROR: Cannot uninstall 'chardet'.", 尝试
```
$ pip install --upgrade --force-reinstall pip==9.0.3
$ pip install docker-compose --disable-pip-version-check
$ pip install --upgrade pip
```

#### Upgrade

```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository \
  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) \
  stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce
```

### RHEL or CentOS
#### docker-ce

```
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum makecache fast

sudo yum -y install docker-ce
// or 
sudo yum -y install docker-ce-<version>-<release>

sudo systemctl start docker
sudo docker run hello-world
```

