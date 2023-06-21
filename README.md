# PyTorch-to-TensorflowLite-Conversion
## Procedure to convert the Pytorch file (.pt) to the TensorflowLite file (.tflite)

### 1) Install ONNX (Open Neural Network Exchange), its runtime, and onnxsim using the below commands.
   >*!pip --quiet install onnx onnxruntime onnxsim*\
   >*!pip install onnx-tf*
### 2) Clone the YOLOv7 model from the GitHub repo and download the yolov7.pt PyTorch file from the specified URL.\
>*!git clone https://github.com/WongKinYiu/yolov7.git*
##
>*%cd yolov7*
##
>*!wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt*

