Focal Point
===========

Focal Point allows you to specify the portion of an image that is most
important. This information can be used when the image is cropped or cropped and
scaled so that you don't, for example, end up with an image that cuts off the
subject's head.

In this module the focus is defined as a single point on the image. Among other
things this helps to solve the problem of guaranteeing the size of a cropped image
as described here: <https://drupal.org/node/1889542>.

There is an update path provided (during installation) that will migrate
existing imagefield_focus data to focal_points.

Dependencies
------------

* entity
* image

Installation
------------

Install this module using the official Backdrop CMS instructions at <https://backdropcms.org/guide/modules>.

Setting up image fields
-----------------------

You can specify which type of image fields should use focal point by visiting the configuration screen.

Setting the focal point for an image
------------------------------------

To set the focal point on an image, go to the content edit form (ex. the node
edit form) and upload an image. You will notice a crosshair in the middle of the
newly uploaded image. Drag this crosshair to the most important part of your
image. Done.

As a bonus, you can double-click the crosshair to see the exact coordinates (in
percentages) of the focal point.

Cropping your image
-------------------

The focal point module comes with two image effects:

1. focal point crop
2. focal point crop and scale

Both effects will make sure that the define focal point is as close to the
center of your image as possible. It guarantees the focal point will be not be
cropped out of your image and that the image size will be the specified size.

Other configurations
--------------------

The focal point module's configuration form has only three options. You can
enable focal point on standard image fields and/or media image fields.
Additionally, you can specify what image preset to use for the preview image if
none is already provided.

Additionally, you can select what method to use when calculating the initial
focal point value on image upload. Out of the box, the smart crop module (if
it's installed) can be selected or you can write your own. See
focal_point.api.php for an example of this. **Use this option with care
however since it can require a lot of memory and image processing.**

Updating from imagefield_focus to focal_point
---------------------------------------------

1. Make sure you are on Publisher 7.29.0 or greater
2. **DO NOT** disable imagefield_focus
3. Enable focal_point.
    * During the install process, this module will check every file entity that
    has "imagefield_focus" data and convert that data to "focal_points" by using
    the exact center of the focus rectangle as the focal point.
4. Convert your image styles. Any image style you are using that uses the *Focus
   Crop* or *Focus Scale & Crop* effects should be changed to use the focal
   point equivilents.
    * Don't forget to reexport your features if necessary.
    * **It is not recommended that you create new styles and delete the old ones
    as this can mess with (among other things) existing views and display suite
    settings.**
5. Once you have confirmed that your images are displaying as desired, it is
   safe to disable imagefield_focus.

Support
-------

Submit your issue at <https://github.com/backdrop-contrib/focal_point/issues>.

License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for complete text.

Maintainers
-----------

Seeking maintainers.

Ported to Backdrop by:

* herbdool <https://github.com/herbdool>

Credits
-------

This module is based on the Focal Point module for Drupal--starting at version 7.x-1.1--originally written and maintained by:

* bleen <https://www.drupal.org/u/bleen>