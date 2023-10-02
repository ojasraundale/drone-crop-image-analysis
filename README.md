# Crop Image analysis using Multispectral Drone Images

This repo contains the project report and final presentation of my B.Tech Project at IIT Dharwad in the Fall Semester of 2020. The project was done under the guidance of Prof. Gayathri Ananthnarayan. It was a group project and my other teammate being Ameya Vadnere. 

Although I do not have the permission to upload the code used for this project, I do inface can showcase our reports. 
The BTP ppt can be found here : [PPT](/Drone%20Crop%20Image%20Analysis%20BTP%20.pdf )

And the report can be found here: [Report](/Crop%20Image%20Analysis%20Project.pdf) 

## Data
data was collected over several ﬂight missions of a rotary-wing UAV drone over an [agricultural region](https://www.google.com/maps/place/15%C2%B030'01.3%22N+74%C2%B059'16.4%22E/@15.5002972,74.9867712,386m/data=!3m1!1e3!4m5!3m4!1s0x0:0x0!8m2!3d15.500367!4d74.9878817) near Dharwad in October 2019. The drone was mounted with a Micasense™ Altum Multispectral Camera. The drone ﬂew at an altitude of about 40m and over the ﬂight, the camera captured high resolution (1544 x 2064) images across ﬁve bands: Red, Green, Blue, Near-InfraRed (NIR), Rededge (RE).

Image of the Drone: 
![image](https://github.com/ojasraundale/drone-crop-image-analysis/assets/44360914/4612cdba-15da-4667-9b22-0d16be0c9ce1)

Image of the Camera:
![image](https://github.com/ojasraundale/drone-crop-image-analysis/assets/44360914/816f5c3d-6b6b-434f-a2ff-b8d5f6788b7c)

A single image was captured using 5 bands, so for a single image we had 5 different underlying band images: For eg a typical shot looked like the following:
![image](https://github.com/ojasraundale/drone-crop-image-analysis/assets/44360914/1ebc4b61-7a70-443d-9c11-6b5259ceb870)

It wasn't possible to stack the images one on another as the 5 different cameras had different offsets. This caused images to be turned out blurry:
![image](https://github.com/ojasraundale/drone-crop-image-analysis/assets/44360914/5569ca9c-d336-4864-850f-34108c380549)

Also, the drone captured multiple images from various orientations. We had the drone's exact location and gyroscopic coordinates. For eg. 4 images from a single shot looked like the following: 
![image](https://github.com/ojasraundale/drone-crop-image-analysis/assets/44360914/50ea0cc8-4054-4fd5-850b-8cd43c92bf9e)

Due to these 2 types of errors, we couldn't simply just stack the images one on the other. This is where we started using Agisoft Metashape:


## Agisoft Metashape and Micasense
In this project we extensively used Agisoft Metashape and Micasense to stitch up the drone's images to create _Orthomosaics - a geometrically correct aerialimage that is composed of many individual still images that are stitchedtogether._ . This software helped us stitch the images properly. For eg in the below image we can see what happens if we stitch them together: 
![image](https://github.com/ojasraundale/drone-crop-image-analysis/assets/44360914/92de75a1-6a79-49e5-b110-662004484428)

Notice that we can even see the points on which the drone image was captured. 

![image](https://github.com/ojasraundale/drone-crop-image-analysis/assets/44360914/25a731e0-228a-415e-9eda-979d5447c97a)


Using  these software we were able to stitch up the images and apply image recognition and classification techniques to analyze the crop health and class. Further details can be found in the [Report](/Crop%20Image%20Analysis%20Project.pdf) 
