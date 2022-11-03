# Color Correction of Underwater Images

During this project, we studied various white balance algorithms as well as colour spaces in order to have colour-balanced underwater images. It is important to note that this project has been realised without any Artificial Intelligence notion.

![underwater](https://user-images.githubusercontent.com/72748466/199745048-0919838c-61ce-4ab6-86e8-7087bfb100c1.png)


## Gray World Hypothesis
‍
The first algorithm considers that the average illumination of the scene is gray. We thus modify each canal (R,G and B) separately to obtain a better white balance.

This program gives positive results on our non-underwater model picture. However, the resulting image is a bit too bright.

About our underwater images, the results may be considered a bit better but there still remains a general blue hue that is not wanted. This "simple" gray world hypothesis may not be always verified with underwater images.

‍![image](https://user-images.githubusercontent.com/72748466/199745458-1848b933-aebc-4827-a948-52f129c4ce56.png)


## White Patch Algorithm
‍
The second method will analyze each part of the image and will consider the brightest part as the white light source of the scene. It will then apply to the whole image the transformation necessary for it.

The non-watery result is very satisfactory, however, the underwater results have similar issues than before with a similar (brighter) blue hue.

This algorithm have one main issue which is that the picture needs to contain a light source or it will "create" a fake one.

‍![image](https://user-images.githubusercontent.com/72748466/199745624-117d7867-c769-4c88-adbd-c9b2273aff5d.png)


## Color Spaces

We've seen that applying the two methods on RGB underwater images might not be really efficient. Several research papers anounced better results with other color spaces, mainly the lab space (aka l alpha beta).

‍

Indeed, the next results are way better than what we had before. An important advantage of this method is that it seems to be efficient for every "kind" of underwater images whether they are mostly green or blue. However there are still some issues with these methods to obtain perfect images. The two main ones are the lack of contrast and the lack of saturation which make the picture quite bland.

‍

## The CLAHE Method
‍

One of the main issues the previous methods created on underwater images was the lack of contrast (the other being the lack of saturation, which we did not tackled). In order to solve the problem, we used the "Contrast Limited Adaptive Histogram Equalization" (CLAHE) algorithm, which consists of modifying the lightness of the image by computing histograms of moving windows in the image, clip them and redistribute the values based on these histograms. We can see here a result of the method applied to the L canal of a Lab image. While this gives really impressing images, the modification is too important and the underwater results were not really good. It was clearly more efficient to do a simple histogram modificiation (for instance an histogram equalization).

We thus considered this CLAHE method more like a bonus in our project, and we probably should have focused on the saturation issue, even though it might not have been easy to do without any AI.


![image](https://user-images.githubusercontent.com/72748466/199745798-abc06f12-6b02-4f38-a743-9d2c28e779d4.png)


Please check the notebook for more information and associated code.
