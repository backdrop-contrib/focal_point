##ABOUT

Focal Point allows you to specify the portion of an image that is most
important. This information can be used when the image is cropped or cropped and
scaled so that you don't, for example, end up with an image that cuts off the
subject's head.

This module borrows heavily from the ImageField Focus module but it works in a
fundamentally different way. In this module the focus is defined as a single
point on the image. Among other things this helps to solve the problem of
guaranteeing the size of a cropped image as described here:
https://drupal.org/node/1889542.

Additionally, Focal Point integrates both with standard image fields as well as
media fields provided by the media module.

There is an update path provided (during installation) that will migrate
existing imagefield_focus data to focal_points.

##DEPENDENCIES

- entity
- image

##USUAGE

### Setting up image fields

Install the module as usual. Once enabled you can specify which type of image
fields should
use focal point by visiting the configuration screen.

For media image fields, there is no setup involved. You cannot turn off focal
point on individual media fields.

### Setting the focal point for an image

To set the focal point on an image, go to the content edit form (ex. the node
edit form) and upload an image. You will notice a crosshair in the middle of the
newly uploaded image. Drag this crosshair to the most important part of your
image. Done.

As a bonus, you can double-click the crosshair to see the exact coordintes (in
percentages) of the focal point.

### Cropping your image
The focal point module comes with two image effects:

1. focal point crop
2. focal point crop and scale

Both effects will make sure that the define focal point is as close to the
center of your image as possible. It guarantees the focal point will be not be
cropped out of your image and that the image size will be the specified size.

##OTHER CONFIGURATIONS

The focal point module's configuration form has only two options. You can enable
focal point on standard image fields and/or media image fields. Additionally,
you can specify what image preset to use for the preview image if none is
already provided. Typically this is only used for Media fields.
