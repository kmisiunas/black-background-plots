black-background-plots
======================

Transforms plots so they have black background. Useful for including plots into presentations

## Example

Initial Plot
![in](https://cloud.githubusercontent.com/assets/4820843/5201025/735f33b2-7564-11e4-96d2-be091f336164.png)

Output
![out](https://cloud.githubusercontent.com/assets/4820843/5201033/8b9004ac-7564-11e4-8983-f811ff2023b6.png)

## Idea

Invent the image (white -> black, etc) and then rotate color space by 180 degrees to get original colors.

## Using Photoshop 

 1. Import image
 2. Iamge -> Adjustments -> Invert
 3. Iamge -> Adjustments -> Hue/Saturation...
 4. Set Hue to +180 and click OK

All done

## Using Mathematica 

    ToBlackBackground[img_Image] :=  ImageApply[{Mod[#[[1]] + 0.5, 1], #[[2]], #[[3]]} &,  ColorConvert[ColorNegate@img, "HSB"]]
    
    ToBlackBackground[ Import["sample_image.png" ] ] 


