FROM ubuntu:14.04

RUN apt-get -yqq update
RUN apt-get install -yqq python-setuptools python-dev python-pip
RUN apt-get install -yqq build-essential cmake pkg-config
RUN apt-get install -yqq libx11-dev libatlas-base-dev
RUN apt-get install -yqq libgtk-3-dev libboost-python-dev
RUN python -m pip install --upgrade pip
RUN pip install dlib
RUN pip install numpy
RUN pip install --ignore-installed six
RUN pip install scikit-image 
RUN pip install opencv-python

RUN mkdir /var/faceRec/ 
RUN mkdir /var/faceRec/dataset /var/faceRec/py /var/faceRec/test

WORKDIR /var/faceRec/

COPY ./py py

WORKDIR /var/faceRec/py

# sudo docker build -t facerec:v0.1 . 
# sudo docker run -it --name=test_facerec -v $PWD/dataset:/var/faceRec/dataset/ -v $PWD/test:/var/faceRec/test/ facerec:v0.1 /bin/bash
# python test.py shape_predictor_landmarks.dat face_rec_resnet_model.dat ../dataset/ ../test/test.jpg
