# Local drive object detection and model

The model is based off a YOLO, more specifically YOLOv5 from:
- https://github.com/fcakyon/yolov5-pip

A yolo based model was selected for the speed and what appeared to me (at the time) to be a well documented description of what the multiple layers and architecture. The yolov5 package offered very quick turn around time for training, verification, and eventually video testing. 

# Verification Testing

The first static image of traffic lights was trained on 15 images, tested on 18, and tested on 1048 images of traffic lights. I initially tried to determine 6 different images in addition to the items which the models install with. 

The 6 items were: 

| 	|Class           | 	      Images |   	Labels| 	P  | 	R      | 	mAP@.5| 	mAP@.5:.95|
| - | ---            | ------------- | -------- | --   | -       | ------ | ----------- |
|0  |  all           | 	  18         | 	66      | 0.218|  	0.344| 	 0.323|        0.117|
|1  |	 walking_light | 	  18         | 	3       | 0.000| 	  0.000| 	 0.043| 	     0.010|
|2  |  green_light   | 	  18         | 	15      | 0.320|  	0.800| 	 0.719| 	     0.278|
|3  |  traffic_light | 	  18         | 	15      | 0.459| 	  0.667| 	 0.477| 	     0.215|
|4  |  red_light     | 	  18         | 	15      | 0.334| 	  0.467| 	 0.385|   	   0.117|
|5  |  yellow_light  | 	  18         | 	15      | 0.196| 	  0.133| 	 0.148|   	   0.043|
|6  |  timer_light   |    18         | 	3       | 0.000| 	  0.000| 	 0.167|  	     0.037|

The standard classes defined before the addition of the above are/were:

```yaml
nc: 80  # number of classes
names: ['person', 'bicycle', 'car', 'motorcycle', 'airplane', 'bus', 'train', 'truck', 'boat', 'traffic light',
        'fire hydrant', 'stop sign', 'parking meter', 'bench', 'bird', 'cat', 'dog', 'horse', 'sheep', 'cow',
        'elephant', 'bear', 'zebra', 'giraffe', 'backpack', 'umbrella', 'handbag', 'tie', 'suitcase', 'frisbee',
        'skis', 'snowboard', 'sports ball', 'kite', 'baseball bat', 'baseball glove', 'skateboard', 'surfboard',
        'tennis racket', 'bottle', 'wine glass', 'cup', 'fork', 'knife', 'spoon', 'bowl', 'banana', 'apple',
        'sandwich', 'orange', 'broccoli', 'carrot', 'hot dog', 'pizza', 'donut', 'cake', 'chair', 'couch',
        'potted plant', 'bed', 'dining table', 'toilet', 'tv', 'laptop', 'mouse', 'remote', 'keyboard', 'cell phone',
        'microwave', 'oven', 'toaster', 'sink', 'refrigerator', 'book', 'clock', 'vase', 'scissors', 'teddy bear',
        'hair drier', 'toothbrush']  # class names
```

The classes added look like:

```yaml 
# number of classes
nc: 6

# class names 0           1              2                3            4               5
names: ["walking light",
        "green light",
        "traffic light",
        "red light",
        "yellow light",
        "timer light"]
```

It was an unfortunate miss of the "traffic light" class in the original yolo model. Given there was not a large training and validation image set used, the confidence/output from the training I performed at [image test results](./test_results_imgs/) and [video results](./test_results_video/). The traffic light confidence and weighting that the yolov5 provided is significantly more defined than the model I provided. Given enough time, I could categorize, define, and train on a larger dataset, but it does not provide signficant benefit given the current models (more than adequate) capability. For the purpose of a proof of concept traffic light recognition system is therefore completed.
