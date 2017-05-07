Post-processing is for the moment not plugged in the current app and rely heavily on `BoofCV`. 

However, all the logic is already implemented. You'll find it as a tuto example in the [WaveletDenoise](https://github.com/echopen/PRJ-medtec_androidapp/blob/master/app/src/main/java/com/echopen/asso/echopen/filters/WaveletDenoise.java) class. Any other algorithm can be simply implemented with the same pattern as [WaveletDenoise](https://github.com/echopen/PRJ-medtec_androidapp/blob/master/app/src/main/java/com/echopen/asso/echopen/filters/WaveletDenoise.java), and the abstraction logic is given through `AbstractBaseImage, BaseProcess, BaseImage`. 

## BoofCV

All information about BoofCV tyoe format are available [here](http://boofcv.org/index.php?title=Tutorial_Images)

