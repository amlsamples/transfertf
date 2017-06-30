# Transfer Learning with TensorFlow

This sample shows how to use the Inception V3 model from TensorFlow as featurtizers to perform transfer learing on any classes of images you want.

Please visit this tutorial for detailed instruction. 
https://github.com/Azure/ViennaDocs/blob/master/Documentation/TransferLearning.md

Note you need to populate the images folder with at least 2 sub folders of images before you can run the training job.

Quick shortcuts:

```
# Train the model
$ az ml execute start -c docker retrain.py --bottleneck_dir=bottlenecks --model_dir=inception --summaries_dir=outputs/training_summaries/long --output_graph=outputs/retrained_graph.pb --output_labels=outputs/retrained_labels.txt --image_dir=images

# Score the model
az ml execute start -c myvm ./label_image.py --graph retrained_graph.pb --labels retrained_labels.txt --image new_test.jpg
```
