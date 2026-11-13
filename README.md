<h2>TensorFlow-FlexUNet-Image-Segmentation-Kidney-Stone-CT-Coronal (2026/11/13)</h2>
Sarah T. Arai<br>
Software Laboratory antillia.com<br><br>
This is the first experiment of Image Segmentation for <b>Kidney-Stone-CT-Coronal </b>
 based on
our <a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">TensorFlowFlexUNet Model</a>
 (<b>TensorFlow Flexible UNet Image Segmentation Model for Multiclass</b>) and a 512x512-pixel PNG 
<a href="https://drive.google.com/file/d/1B6IKfHphXcUi2KsaCE7KzRLFN82rhj5l/view?usp=sharing">
Augmented-Kidney-Stone-CT-Coronal-ImageMask-Dataset.zip</a> 
(<a href="https://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a>) which was derived by us from the Kaggle
<br><br>
<a href="https://www.kaggle.com/datasets/bemorekgg/kidney-stone-segmentation-dataset/data">
<b>Kidney Stone Segmentation Dataset</b>
</a> <br>
by kildongGo.
<br><br>
<hr>
<b>Actual Image Segmentation for Kidney-Stone-CT-Coronal Images of 512x512 pixels</b><br>
As shown below, the inferred masks resemble the ground-truth masks. <br>
<br>
<table>
<tr>
<th width="320" height="auto">Input: image</th>
<th width="320" height="auto">Mask (ground_truth)</th>
<th width="320" height="auto">Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/10080.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/10080.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/10080.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/10280.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/10280.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/10280.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/hflipped_10540.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/hflipped_10540.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/hflipped_10540.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>1. Dataset Citation</h3>
The dataset used here was taken from the following Kaggle:<br><br>
<a href="https://www.kaggle.com/datasets/bemorekgg/kidney-stone-segmentation-dataset/data">
<b>Kidney Stone Segmentation Dataset</b>
</a> <br>
by kildongGo.
<br><br>
The following explanation was taken the website above.
<br><br>
<b>About Dataset</b><br>
<b>Overview</b><br>
This dataset contains images of kidney stones with corresponding segmentation masks generated 
using the Segment Anything Model (SAM). It is designed for medical image segmentation tasks focusing on kidney stone detection and delineation.
<br><br>
<b>Dataset Contents</b><br>
Images: CT scan images of kidney stones in JPG format<br>
Segmentation Masks: Binary masks in PNG format generated from YOLO bounding box annotations using SAM<br>
Text Files: Original YOLO format annotations used to guide the segmentation process<br><br>
<b>License</b><br>
<a href="https://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a>
<br>
<br>
<h3>
2. Kidney-Stone-CT-Coronal ImageMask Dataset
</h3>
<h3>2.1 Download ImageMask Dataset</h3>
 If you would like to train this Kidney-Stone-CT-Coronal Segmentation model,
 please download the dataset from
<a href="https://drive.google.com/file/d/1B6IKfHphXcUi2KsaCE7KzRLFN82rhj5l/view?usp=sharing">
<b>Augmented-Kidney-Stone-CT-Coronal-ImageMask-Dataset.zip</b>
</a>.
Expand the downloaded and put it under the <b>./dataset</b> folder.
<br>
<pre>
./dataset
└─Kidney-Stone-CT-Coronal
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
         ├─images
         └─masks
</pre>
<br>
<b>Kidney-Stone-CT-Coronal Statistics</b><br>
<img src ="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/Kidney-Stone-CT-Coronal_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images in the training and valid datasets is not so large to use for the
 training set of our segmentation model.
<br><br>
<h3>2.2 Train Sample Images and Masks</h3>
<b>Train_sample_images</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_sample_masks</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/train_masks_sample.png" width="1024" height="auto">
<br>
<h3>
3. Train TensorFlowFlexUNet Model
</h3>
 We trained the Kidney-Stone-CT-Coronal TensorFlowFlexUNet model using the following
<a href="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
This runs the following command.<br>
<pre>
>python ../../../src/TensorFlowFlexUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>
<b>Model parameters</b><br>
Defined a small <b>base_filters=16 </b> and large <b>base_kernels=(11,11)</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet.py</a> 
and a large <b>num_layers=8</b> (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
; You may specify your own UNet class derived from our TensorFlowFlexModel
model         = "TensorFlowFlexUNet"
generator     =  False
image_width    = 512
image_height   = 512
image_channels = 3
num_classes    = 2
base_filters   = 16
base_kernels   = (11,11)
num_layers     = 8
dropout_rate   = 0.03
dilation       = (1,1)
</pre>
<b>Learning rate</b><br>
Defined a small learning rate.  
<pre>
[model]
learning_rate  = 0.00007
</pre>
<b>Loss and metrics functions</b><br>
Specified "categorical_focal_dice_loss" and <a href="./src/dice_coef_multiclass.py">"dice_coef_hybrid"</a>.<br>
<pre>
[model]
loss           = "categorical_focal_dice_loss"
metrics        = ["dice_coef_hybrid"]
hybrid_alpha   = 1.6
hybrid_beta    = 0.4
</pre>
<b>Dataset class</b><br>
Specifed <a href="./src/ImageCategorizedMaskDataset.py">ImageCategorizedMaskDataset</a> class.<br>
<pre>
[dataset]
class_name    = "ImageCategorizedMaskDataset"
</pre>
<br>
<b>Learning rate reducer callback</b><br>
Enabled the learning_rate_reducer callback and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.4
reducer_patience   = 4
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with the patience parameter.
<pre>
[train]
patience      = 10
</pre>
<b>RGB Color map</b><br>
Specified RGB color map dict for Kidney-Stone-CT-Coronal 2 classes.<br>
<pre>
[mask]
mask_datatype= "categorized"
mask_file_format = ".png"
; Kidney-Stone-CT-Coronal RGB color map dict for 1+1 classes.
;      Background: black,  Nodule:white
rgb_map = {(0,0,0):0,(255,255,255):1,}
</pre>

<b>Epoch change inference callback</b><br>
Enabled <a href="./src/EpochChangeInferencer.py">epoch_change_infer callback</a></b>.<br>
<pre>
[train]
epoch_change_infer       = True
epoch_change_infer_dir   =  "./epoch_change_infer"
num_infer_images         = 6
</pre>

By using this callback, on every epoch change, the inference procedure can be called
 for 6 images in the <b>mini_test</b> folder. This will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> 
<br> 
<!--
As shown below, early in the model training, the predicted masks from our FlexUNet segmentation model showed 
discouraging results.
 However, as training progressed through the epochs, the predictions gradually improved. 
 <br> 
<br>
-->
<b>Epoch_change_inference output at starting (epoch 1,2,3)</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/epoch_change_infer_at_start.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at middlepoint (epoch 24,25,26)</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/epoch_change_infer_at_middle.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at ending (epoch 49,50,51)</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/epoch_change_infer_at_end.png" width="1024" height="auto"><br>
<br>
In this experiment, the training process was stopped at epoch 51 by EarlyStoppingCallback.<br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/train_console_output_at_epoch51.png" width="1024" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/eval/train_metrics.png" width="520" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/eval/train_losses.png" width="520" height="auto"><br>
<br>
<h3>
4. Evaluation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal</b> folder,
and run the following bat file to evaluate the TensorFlowUNet model for Kidney-Stone-CT-Coronal.<br>
<pre>
>./2.evaluate.bat
</pre>
This runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetEvaluator.py ./train_eval_infer.config
</pre>

Evaluation console output:<br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/evaluate_console_output_at_epoch51.png" width="1024" height="auto">
<br><br>Image-Segmentation-Kidney-Stone-CT-Coronal

<a href="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/evaluation.csv">evaluation.csv</a><br>
The loss (categorical_focal_dice_loss) on this Kidney-Stone-CT-Coronal/test was very low, and dice_coef_hybrid was high, as shown below.
<br>
<pre>
categorical_focal_dice_loss,0.002
dice_coef_hybrid,0.939
</pre>
<br>
<h3>
5. Inference
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal</b> folder
and run the following bat file to infer segmentation regions for images using the trained TensorFlowUNet model for Kidney-Stone-CT-Coronal.<br>
<pre>
>./3.infer.bat
</pre>
This runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetInferencer.py ./train_eval_infer.config
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/mini_test_masks.png" width="1024" height="auto"><br>

<hr>
<b>Inferred test masks</b><br>
<img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks for Kidney-Stone-CT-Coronal Images of 512x512 pixels</b><br>
As shown below, the inferred masks look similar to the ground truth masks except for the third and sixth cases.<br>
<br>
<table>
<tr>
<th width="320" height="auto">Image</th>
<th width="320" height="auto">Mask (ground_truth)</th>
<th width="320" height="auto">Inferred-mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/10280.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/10280.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/10280.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/10374.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/10374.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/10374.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/10682.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/10682.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/10682.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/10808.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/10808.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/10808.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/hflipped_10171.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/hflipped_10171.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/hflipped_10171.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/images/10732.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test/masks/10732.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Kidney-Stone-CT-Coronal/mini_test_output/10732.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>
References
</h3>
<b>1.  TensorFlow-FlexUNet-Image-Segmentation-KSSD2025-Kidney-Stone-CT</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-KSSD2025-Kidney-Stone-CT">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-KSSD2025-Kidney-Stone-CT
</a>
<br><br>
<b>2. TensorFlow-FlexUNet-Image-Segmentation-Kidney-Stone-CT-Axial</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Kidney-Stone-CT-Axial">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Kidney-Stone-CT-Axial
</a>
<br><br>
<b>3. TensorFlow-FlexUNet-Image-Segmentation-Model</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model
</a>
<br><br>
