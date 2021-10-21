# Automatic_number_plate_detection

In this project we working on automatic licence plate with help of Tesseract - OCR.

* First we create on object detection using yolo v4 pretrained model for detecte a number plate of pretrained weight .

Here yolo v4 weights : https://drive.google.com/open?id=1cewMfusmPjYWbrnuJRuKhPMwRe_b9PaT.

* Then apply opencv for some preprocessing our detection parts.[Convert to gray scale, thresold an image with otu's method .

* After preprocessing pass into ocr extract an image one by one and append it.

# Steps:

1) First set an path

  *  Tensorflow CPU [Recommanded]

	* conda env create -f conda-cpu.yml

	* conda activate yolov4-cpu

	or 

 	* pip install -r requirements.txt

2) Custom yolov4 using TensorFlow

	* python save_model.py --weights ./data/custom.weights --output ./checkpoints/custom-416 --input_size 416 --model yolov4 

3) THen download a Tesseract api:

	* link : https://github.com/UB-Mannheim/tesseract/wiki

	* Then connect with my project in pycharm

	* Go to utilis.py to check it. [Whether my location of my downloaded path will be connected or not >> pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract']

4) Run a OCR model :

  	*  Run License Plate Recognition

	python detect.py --weights ./checkpoints/custom-416 --size 416 --model yolov4 --images ./data/images/car2.jpg --plate
  
  
  # Use case of this project
  
  * Identify who don't follow traffic rules.
  * Used in TollGate purpose.
  * Identify vehicle type.


