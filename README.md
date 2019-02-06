# RAW cars dataset

This repository contains 225 RAW images of scenes containing cars.

A description of the repo directories follows:

## RAW_converted
The original RAW images have been scaled to [0, 255] from their original scale of [0, 1023] and converted to the lossless PNG image format. This reduces their size and make circulation feasible. 

The edge pixels have been deleted, for they are removed by the ISP in the processed images. The ISP does so because these pixels do not receive enough illumination.

## ISP_processed
The image signal processed images can be found in ISP_processed directory. These images are in JPG format.

## Annotations
The annotations for the images can be found in annotations.xls

The image number is given in the imageFilename column and the coordinates for bounding boxes are given in coords_i columns.
A consecutive quadruple of coords columns forms a single bounding box, and has the following format:
box = [top_left_x, top_left_y, box_height, box_width]

# Original RAW images
For experimentation purposes, the original RAW images have been uploaded in a google drive and are available at the following link: https://goo.gl/vqSvdE

# Results
Using an off-the-shelf faster-RCNN network, we are able to achieve the following accuracies:

| Image Format | Accuracy |
| --- | --- |
| Original RAW images in the converted format | 16.67% |
| RAW images with gamma compression and pixel binning | 76% |
| JPG images | 76.67% |
| --- | --- |
