# PyTorch-to-TensorflowLite-Conversion
## Procedure to convert the Pytorch file (.pt) to the TensorflowLite file (.tflite)

### 1) Install ONNX (Open Neural Network Exchange), its runtime, and onnxsim using the below commands.
   >*!pip --quiet install onnx onnxruntime onnxsim*\
   >*!pip install onnx-tf*
### 2) Clone the YOLOv7 model from the GitHub repo and download the yolov7.pt PyTorch file from the specified URL.
>*!git clone https://github.com/WongKinYiu/yolov7.git*
##
>*%cd yolov7*
##
>*!wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt*
### 3) Command line instruction to run the Python script file and The PyTorch file is converted into ONNX format.
>!python /content/yolov7/export.py --weights /content/yolov7-final.pt --grid --end2end --simplify \ \
>*--topk-all 100 --iou-thres 0.65 --conf-thres 0.35 --img-size 640 640 --max-wh 640*
### 4) Conversion of OONX format to TensorFlow format.
>*!onnx-tf convert -i /content/yolov7-final.onnx -o /content/yolov7-final.pb*
### 5) Convertion of Tensorflow format to TensorFlowlite format.

>import tensorflow as tf \
>converter = tf.lite.TFLiteConverter.from_saved_model('/content/yolov7-final.pb') \
>tflite_model = converter.convert() \
>with open('/content/yolov7_model.tflite', 'wb') as f: \
>> f.write(tflite_model)

## For further clarity please look into the .ipynb file.
