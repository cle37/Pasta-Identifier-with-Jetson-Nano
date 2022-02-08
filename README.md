# Pasta Identifier with Jetson Nano
## _Don't know the shape of that pasta? Pasta Identifier is here to help!_

Pasta Identifier is an image classification project made for the Jetson AI Specialist Certification Project.

## Description

Ever wondered the name of the pasta shape you have in your pantry? The Pasta Identifier is here to identify your pasta! Currently, the Pasta Identifier supports the identification of penne and spaghetti!

Pasta Identifier was made through transfer learning with the training of a custom dataset of pasta shapes. This program works with the Image Classification part of the Hello AI World Tutorial here: https://github.com/dusty-nv/jetson-inference

## Files for This Project

The files listed below are all of the files necessary to run this program as well as the raw dataset so you can train more pasta shapes! The files were too large to be uploaded here, so download links are provided below in Instructions.
- pastaidentifierdata: the images used to train pasta shapes
- pastaidentifiermodels: the model of the Pasta Identifier

## Instructions

Setup
- Set up your Jetson Nano with Jetpack and Jetson-Inference: https://github.com/dusty-nv/jetson-inference/blob/master/docs/jetpack-setup-2.md
  - Plug in a compatible camera into the Jetson Nano
- Run the Jetson-Inference docker container: https://github.com/dusty-nv/jetson-inference/blob/master/docs/aux-docker.md
```sh
cd jetson-inference/
docker/run.sh
```
- Move to the Classification Folder
```sh
cd python/training/classification/
```
- Download pastaidentifiermodel here: https://drive.google.com/drive/folders/1kFCeqmBy3vUzQYYeG3SWWh9y4jo8Mr4Y?usp=sharing
- Download pastaidentifierdata here: https://drive.google.com/drive/folders/1tNhA5pvDsDlhR_K9RdP91C0T1lnqXizO?usp=sharing
- Move pastaidentifiermodel into the folder jetson-inference/python/training/classification/models
- Move pastaidentifierdata into the folder jetson-inference/python/training/classification/data

Run the Image Classification Program

- Run imagenet with the pastaidentifiermodel
```sh
imagenet --model=models/pastaidentifiermodel/resnet18.onnx --labels=data/pastaidentifierdata/labels.txt --input_blob=input_0 --output_blob=output_0 /dev/video0
```
