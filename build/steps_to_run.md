# Initial Setup
## Carla

### AWS
- https://carla.readthedocs.io/en/latest/tuto_G_rllib_integration/
- - https://carla.readthedocs.io/en/latest/
- https://github.com/jbnunn/CARLADesktop

### Google Colab
- https://github.com/MichaelBosello/carla-colab

## Yolov5
- https://pypi.org/project/yolov5/ 
- https://github.com/ultralytics/yolov5

## Ubuntu 20.04.4 LTS
- https://ubuntu.com/download/desktop

# Simple steps
1. Setup Yolov5, and (if desired) design new model and complete training/testing of model. Once the local model is working, I will transfer the model and the required data files to the AWS instance which will run the model over either another AWS Carla Ubuntu instance or the Google Colab notebook. The advantage of using the AWS instance is that Colab (for non-pro users) will need to be "active" on the notebook page to keep it from being shutdown.
2. Setup Carla on local/remote computer.
3. Complete AWS testing on free tier instances prior to starting an instance with more capability. 
4. Design Carla driving simulations.
5. Run the yolo model with the Carla instance/Google Colab notebook. 
