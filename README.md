# Home Assistant TensorFlow Integration Setup

This repo is here to simplify setup of the TensorFlow integration for Home Assistant. To install the prerequisite dependancies, simply run the following command inside your `config` directory:

```bash
git clone https://github.com/hunterjm/hass-tensorflow.git tensorflow
```

Afterwards, check out the [TensorFlow 2 Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md) and download a detection model to use. After downloading, extract the model into the `models` directory. Your Home Assistant configuration should then look something like this:

```yaml
image_processing:
  - platform: tensorflow
    source:
      - entity_id: camera.local_file
    model:
      graph: /config/tensorflow/models/efficientdet_d0_coco17_tpu-32/
```
