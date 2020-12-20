# Speed Bump Object Detection using SSD_MobileNet architecture in Windows

1. Create a virtual environment either using Anaconda prompt or simply in a directory
      > conda create -n tf pip python=3.5
      
2. Activate virtual environment
      > conda activate tf
      
3. Install tensorflow. I have used tensorflow==1.13.0
     - If you are using gpu install
          > pip install tensorflow-gpu
     - If it is CPU then
          > pip install tensorflow

4. Install necessary packages
     - conda install -c anaconda protobuf
     - pip install pillow
     - pip install lxml
     - pip install Cython
     - pip install contextlib2
     - pip install jupyter
     - pip install matplotlib
     - pip install pandas
     - pip install opencv-python
      
5. Create a folder tensorflow/models. Download this cloned repository and move/copy this cloned repository into tensorflow/models/ folder

6. Set python environment variable.
      > set PYTHONPATH=C:\tensorflow\models;C:\tensorflow\models\research;C:\tensorflow\models\research\slim

7. Goto C:/tensorflow/models/research folder and compile protocol buffer and run setup.py
      > protoc --python_out=. .\object_detection\protos\anchor_generator.proto .\object_detection\protos\argmax_matcher.proto .\object_detection\protos\bipartite_matcher.proto .\object_detection\protos\box_coder.proto .\object_detection\protos\box_predictor.proto .\object_detection\protos\eval.proto .\object_detection\protos\faster_rcnn.proto .\object_detection\protos\faster_rcnn_box_coder.proto .\object_detection\protos\grid_anchor_generator.proto .\object_detection\protos\hyperparams.proto .\object_detection\protos\image_resizer.proto .\object_detection\protos\input_reader.proto .\object_detection\protos\losses.proto .\object_detection\protos\matcher.proto .\object_detection\protos\mean_stddev_box_coder.proto .\object_detection\protos\model.proto .\object_detection\protos\optimizer.proto .\object_detection\protos\pipeline.proto .\object_detection\protos\post_processing.proto .\object_detection\protos\preprocessor.proto .\object_detection\protos\region_similarity_calculator.proto .\object_detection\protos\square_box_coder.proto .\object_detection\protos\ssd.proto .\object_detection\protos\ssd_anchor_generator.proto .\object_detection\protos\string_int_label_map.proto .\object_detection\protos\train.proto .\object_detection\protos\keypoint_box_coder.proto .\object_detection\protos\multiscale_anchor_generator.proto .\object_detection\protos\graph_rewriter.proto
      > python setup.py build
      > python setup.py install

8. Finally run training file. Goto C:/tensorflow/models/research/object_detection/
      > python train.py --logtostderr --train_dir=training/ --pipeline_config_path=training/ssd_mobilenet_v1_pets.config
      


## License

[Apache License 2.0](LICENSE)
