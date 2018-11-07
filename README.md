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
