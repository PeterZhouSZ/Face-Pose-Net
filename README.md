# Face-Pose-Net

This page contains DCNN model and python code to robustly estimate 6 degrees of freedom, 3D face pose from an unconstrained image, without the use of face landmark detectors. The method is described in the paper:

_F.-J. Chang, A. Tran, T. Hassner, I. Masi, R. Nevatia, G. Medioni, "FacePoseNet: Making a Case for Landmark-Free Face Alignment", in 7th IEEE International Workshop on Analysis and Modeling of Faces and Gestures, ICCV Workshops, 2017_ [1].

This release bundles up our **FacePoseNet** (FPN) with the **Face Renderer** from Masi _et al._ [2,5], which is available separately from [this project page](https://github.com/iacopomasi/face_specific_augm).

The result is an end-to-end pipeline that seamlessly estimates facial pose and produces multiple rendered views to be used for face alignment and data augmentation.

![Teaser](http://www-bcf.usc.edu/~iacopoma/img/FPN3.png)

## Features
* **6DoF 3D Head Pose estimation** + **3D rendered facial views**.
* Does not use **fragile** landmark detectors
* Robustness on images landmark detectors struggle with (low rez., occluded, etc.)
* Extremely fast pose estimation
* Both CPU and GPU supported
* Provides better face recognition through better face alignment than alignment using state of the art landmark detectors [1]

## Dependencies

* [TensorFlow](https://www.tensorflow.org/)
* [OpenCV Python Wrapper](http://opencv.org/)
* [Numpy](http://www.numpy.org/)
* [Python2.7](https://www.python.org/download/releases/2.7/)

The code has been tested on Linux only. On Linux you can rely on the default version of python, installing all the packages needed from the package manager or on Anaconda Python and install required packages through `conda`. 

**Note:** no landmarks are used in our method, although you can still project the landmarks on the input image using the estimated pose. See the paper for further details. 

## Usage

* **Important:** In order to download **both** FPN code and the renderer use `git clone --recursive`
* **Important:** Please download the learned models from https://www.dropbox.com/s/r38psbq55y2yj4f/fpn_new_model.tar.gz?dl=0   and make sure that the FPN models are stored in the folder `fpn_new_model`.

### Run it

The alignment and rendering can be used from the command line in the following, different ways.

To run it directly on a list of images (software will run FPN to estimate the pose and then render novel views based on the estimated pose):

```bash
$ python main_fpn.py <input-list-path>
```

We provide a sample input list available [here](input.csv).
```bash
<ID, FILE, FACE_X, FACE_y, FACE_WIDTH, FACE_HEIGHT>
```
where `<FACE_X, FACE_y, FACE_WIDTH, FACE_HEIGHT>` is the face bounding box information, either obtained manually or by the face detector. 

## Sample Results
Please see the input images [here](images) and rendered outputs [here](output_render).

The rendered images will be saved here!
## Subject 1 ##
### input: ### 
![sbj1](../images/input1.jpg)
### rendering: ### 
![sbj1](./subject1/subject1_a_rendered_aug_-00_00_10.jpg)
![sbj1](./subject1/subject1_a_rendered_aug_-22_00_10.jpg)
![sbj1](./subject1/subject1_a_rendered_aug_-40_00_10.jpg)
![sbj1](./subject1/subject1_a_rendered_aug_-55_00_10.jpg)
![sbj1](./subject1/subject1_a_rendered_aug_-75_00_10.jpg)





## Subject 2 ##

### input: ### 

![sbj2](../images/input2.jpg)

### rendering: ### 

![sbj2](./subject2/subject2_a_rendered_aug_-00_00_10.jpg)

![sbj2](./subject2/subject2_a_rendered_aug_-22_00_10.jpg)

![sbj2](./subject2/subject2_a_rendered_aug_-40_00_10.jpg)

![sbj2](./subject2/subject2_a_rendered_aug_-55_00_10.jpg)

![sbj2](./subject2/subject2_a_rendered_aug_-75_00_10.jpg)



## Subject 3 ##

### input: ### 

![sbj3](../images/input3.jpg)

### rendering: ### 

![sbj3](./subject3/subject3_a_rendered_aug_-40_00_10.jpg)

![sbj3](./subject3/subject3_a_rendered_aug_-55_00_10.jpg)

![sbj3](./subject3/subject3_a_rendered_aug_-75_00_10.jpg)



## Subject 4 ##

### input: ### 

![sbj4](../images/input4.jpg)

### rendering: ### 

![sbj4](./subject4/subject4_a_rendered_aug_-40_00_10.jpg)

![sbj4](./subject4/subject4_a_rendered_aug_-55_00_10.jpg)

![sbj4](./subject4/subject4_a_rendered_aug_-75_00_10.jpg)



## Subject 5 ##

## input: ##



### input: ### 

![sbj5](../images/input5.jpg)

### rendering: ### 

![sbj5](./subject5/subject5_a_rendered_aug_-40_00_10.jpg)

![sbj5](./subject5/subject5_a_rendered_aug_-55_00_10.jpg)

![sbj5](./subject5/subject5_a_rendered_aug_-75_00_10.jpg)



## Subject 6 ##

### input: ### 

![sbj6](../images/input6.jpg)

### rendering: ### 

![sbj6](./subject6/subject6_a_rendered_aug_-40_00_10.jpg)

![sbj6](./subject6/subject6_a_rendered_aug_-55_00_10.jpg)

![sbj6](./subject6/subject6_a_rendered_aug_-75_00_10.jpg)



## Subject 7 ##

### input: ### 

![sbj7](../images/input7.jpg)

### rendering: ### 

![sbj7](./subject7/subject7_a_rendered_aug_-00_00_10.jpg)

![sbj7](./subject7/subject7_a_rendered_aug_-22_00_10.jpg)

![sbj7](./subject7/subject7_a_rendered_aug_-40_00_10.jpg)

![sbj7](./subject7/subject7_a_rendered_aug_-55_00_10.jpg)

![sbj7](./subject7/subject7_a_rendered_aug_-75_00_10.jpg)



## Subject 8 ##

### input: ### 

![sbj8](../images/input8.jpg)

### rendering: ### 

![sbj8](./subject8/subject8_a_rendered_aug_-40_00_10.jpg)

![sbj8](./subject8/subject8_a_rendered_aug_-55_00_10.jpg)

![sbj8](./subject8/subject8_a_rendered_aug_-75_00_10.jpg)



## Subject 9 ##

### input: ### 

![sbj9](../images/input9.jpg)

### rendering: ### 

![sbj9](./subject9/subject9_a_rendered_aug_-40_00_10.jpg)

![sbj9](./subject9/subject9_a_rendered_aug_-55_00_10.jpg)

![sbj9](./subject9/subject9_a_rendered_aug_-75_00_10.jpg)



## Subject 10 ##

### input: ### 

![sbj10](../images/input10.jpg)

### rendering: ### 

![sbj10](./subject10/subject10_a_rendered_aug_-00_00_10.jpg)

![sbj10](./subject10/subject10_a_rendered_aug_-22_00_10.jpg)

![sbj10](./subject10/subject10_a_rendered_aug_-40_00_10.jpg)

![sbj10](./subject10/subject10_a_rendered_aug_-55_00_10.jpg)

![sbj10](./subject10/subject10_a_rendered_aug_-75_00_10.jpg)



## Current Limitations
FPN is currently trained with a single 3D generic shape, without accounting for facial expressions. Addressing these is planned as future work.

## Citation

Please cite our paper with the following bibtex if you use our face renderer:

``` latex
@inproceedings{masi16dowe,
      title={{F}ace{P}ose{N}et: Making a Case for Landmark-Free Face Alignment},
      booktitle = {7th IEEE International Workshop on Analysis and Modeling of Faces and Gestures, ICCV Workshops},
      author={
      Feng-ju Chang
      and Anh Tran 
      and Tal Hassner 
      and Iacopo Masi 
      and Ram Nevatia
      and G\'{e}rard Medioni},
      year={2017},
    }
```

## References
[1] F.-J. Chang, A. Tran, T. Hassner, I. Masi, R. Nevatia, G. Medioni, "FacePoseNet: Making a Case for Landmark-Free Face Alignment", in 7th IEEE International Workshop on Analysis and Modeling of Faces and Gestures, ICCV Workshops, 2017

[2] I. Masi\*, A. Tran\*, T. Hassner\*, J. Leksut, G. Medioni, "Do We Really Need to Collect Million of Faces for Effective Face Recognition? ", ECCV 2016, 
    \* denotes equal authorship

[3] I. Masi, S. Rawls, G. Medioni, P. Natarajan "Pose-Aware Face Recognition in the Wild", CVPR 2016

[4] T. Hassner, S. Harel, E. Paz and R. Enbar "Effective Face Frontalization in Unconstrained Images", CVPR 2015

[5] I. Masi, T. Hassner, A. Tran, and G. Medioni, "Rapid Synthesis of Massive Face Sets for Improved Face Recognition", FG 2017

## Changelog
- August 2017, First Release 

## Disclaimer

_The SOFTWARE PACKAGE provided in this page is provided "as is", without any guarantee made as to its suitability or fitness for any particular use. It may contain bugs, so use of this tool is at your own risk. We take no responsibility for any damage of any sort that may unintentionally be caused through its use._

## Contacts

If you have any questions, drop an email to _fengjuch@usc.edu_, _anhttran@usc.edu_, _iacopo.masi@usc.edu_ or _hassner@isi.edu_ or leave a message below with GitHub (log-in is needed).
