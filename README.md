# Unsupervised-Adaptation-for-Deep-Stereo
Official Code for "Unsupervised Adaptation for Deep Stereo" - ICCV17 (http://openaccess.thecvf.com/content_ICCV_2017/papers/Tonioni_Unsupervised_Adaptation_for_ICCV_2017_paper.pdf)

This is the original caffe implementation used for the ICCV17 paper, since then we have also developed an easier to handle tensorflow implementation available here: https://github.com/AlessioTonioni/dispflownet-tf.
(**DISCLAIMER**: the performance of the Dispnet trained on tensorlfow are slightly worse than those of the original one, act accordingly)

This code is intended to be plugged into DispNet by Mayer et al., available at https://lmb.informatik.uni-freiburg.de/resources/binaries/dispflownet/dispflownet-release-1.2.tar.gz 
If you use this code, please cite our paper: 


	@InProceedings{Tonioni_2017_ICCV,
	  author = {Tonioni, Alessio and Poggi, Matteo and Mattoccia, Stefano and Di Stefano, Luigi},
	  title = {Unsupervised Adaptation for Deep Stereo},
	  booktitle = {The IEEE International Conference on Computer Vision (ICCV)},
	  month = {Oct},
	  year = {2017}
	}

## List of source files:

+ **/dispflownet-adaptation-release/src/caffe/layers/custom_data_layer**:
Allows to read confidence in addition to stereo pairs and disaprity ground-truth.

+ **/dispflownet-adaptation-release/src/caffe/layers/l1loss_layer**:
Includes the confidence weighted L1 loss used for unsupervised adaptation.

+ **/dispflownet-adaptation-release/src/caffe/proto/caffe.proto**:
Definition of the confidence data type CONF

+ **/dispflownet-adaptation-release/tools/convert_imageset_disparity_confidence.cpp** and **convert_imageset_disparity_confidence_from_png.cpp**:
Tool to create dataset with stereo pairs, ground-truth disparity and confidence

+ **/dispflownet-adaptation-release/models/DispNet_Adaptation_kitti_train/**:
Contains solver and training procedure used to adapt DispNetCorrD1 on KITTI dataset + get_weights.sh to download a caffemodel weights file for DispNetCorr1D adpated on Kitti2012 using Census and CCNN for 120000 step

+ **/dispflownet-adaptation-release/models/DispNet_Adaptation_ShadowOnTruck/**:
Contains get_weights.sh to download a caffemodel weights file for DispNetCorr1D adapted on the challenging sequence "ShadowOnTruck"
