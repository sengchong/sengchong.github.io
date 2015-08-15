---
layout: post
title: Graphics Pipeline
---
![Graphics pipleline]({{site.url}}/images/GraphicsPipeline.png)

The graphics pipeline starts off from the model world. A model can be in 3D or 2D. 
Every model will have its own local coordinate system. Where you can scale, rotate without affect other model. 
Once you are happy with the scale and the rotation of a model, the next thing that you need to do is to put it together with other models. 

The place where every model is being assemble in a bigger world is labelled as the world space. You will do a transform in the world base on where you want each individual model to be. 

Once that is done, we will define the camera. The camera is showing a part of a bigger world. Just think in terms of a real camera. 
A world is made up of billions of objects but at any time, the camera can only capture a small part of it. By defining the camera, we are limiting what should be rendered. 

Once the camera is defined, we will apply the projection matrix. Remember whatever that is to be render is actually 2D images, in pixel on the screen. However our world could be in a 3D world. So we have to squash these 3D models into a 2D image. If you look carefully in a painting, the model that is future is usually smaller. Similarly to achieve the same effect of having a perspective of depth, we need to resize an image base on the distant it is at from the camera. This process is called projection. Projection is usually in two forms, perceptive and orthogonal.
Perspective is basically what I described just now. Giving a sense of depth for objects that are further away. Where as for orthographic, there is no need to scale a model base on it's depth. Everything will be scale symmetrically. 

After applying the projection martix, we need to subtracted the W value. We call this the projection division. More will be explain on why is there a need to do that.

As the image can be possibility render to different type of screens, we do a normalization so as to make life easier when we apply the view port matrix. 

Finally, after normalising, we apply the view port matrix, we is depending on your viewport settings. 