### Steps to reproduce
1. `git clone https://github.com/awshaichen/PyTorch-YOLOv3.git`
1. `( cd weights/ && bash download_weights.sh )` (run with parentheses; they are for downloading to the right folder without changing the current path)
1. `python detect_trace_noyl.py`

Should see the following ending log messages.
```
     tonga0:tpb0  truediv_67:0
     tonga0:tpb0  truediv_68:0
     tonga0:tpb0  truediv_69:0
     tonga0:tpb0  truediv_6:0
     tonga0:tpb0  truediv_70:0
     tonga0:tpb0  truediv_71:0
     tonga0:tpb0  truediv_7:0
     tonga0:tpb0  truediv_8:0
     tonga0:tpb0  truediv_9:0

           Color  Target
     tonga0:tpb0  tonga
     cpu1000:cpu  llvm
        cpu0:cpu  llvm -mcpu=skylake-avx512


............
Compiler status PASS
[W shared_memory.cpp:190] Warning: The current Neuron runtime configuration does not support shared memory data transfer. Please refer to https://github.com/aws/aws-neuron-sdk/blob/master/docs/neuron-runtime/nrt-theory-of-operation.md#shared-memory-for-inference-ifmaps-and-ofmaps if you encounter performance problem caused by high CPU usage on inf1 instances. (function allocate_shm)
INFO:Neuron:Number of arithmetic operators (post-compilation) before = 325, compiled = 325, percent compiled = 100.0%
INFO:Neuron:The neuron partitioner created 1 sub-graphs
INFO:Neuron:Neuron successfully compiled 1 sub-graphs, Total fused subgraphs = 1, Percent of model sub-graphs successfully compiled = 100.0%
INFO:Neuron:Compiled these operators (and operator counts) to Neuron:
INFO:Neuron: => aten::_convolution: 75
INFO:Neuron: => aten::add: 23
INFO:Neuron: => aten::batch_norm: 72
INFO:Neuron: => aten::cat: 4
INFO:Neuron: => aten::detach: 77
INFO:Neuron: => aten::leaky_relu: 72
INFO:Neuron: => aten::upsample_nearest2d: 2

Performing object detection:
        + Batch 0, Inference Time: 0:00:00.091311
        + Batch 1, Inference Time: 0:00:00.052116
        + Batch 2, Inference Time: 0:00:00.046366
        + Batch 3, Inference Time: 0:00:00.050018
        + Batch 4, Inference Time: 0:00:00.049543
        + Batch 5, Inference Time: 0:00:00.060043
        + Batch 6, Inference Time: 0:00:00.076080
        + Batch 7, Inference Time: 0:00:00.044322
        + Batch 8, Inference Time: 0:00:00.047359

Saving images:
(0) Image: 'data/samples/dog.jpg'
        + Label: dog, Conf: 0.99325
        + Label: bicycle, Conf: 0.99980
        + Label: truck, Conf: 0.94071
(1) Image: 'data/samples/eagle.jpg'
        + Label: bird, Conf: 0.99701
(2) Image: 'data/samples/field.jpg'
        + Label: person, Conf: 0.99996
        + Label: horse, Conf: 0.99976
        + Label: dog, Conf: 0.99395
(3) Image: 'data/samples/giraffe.jpg'
        + Label: giraffe, Conf: 0.99957
        + Label: zebra, Conf: 0.97948
(4) Image: 'data/samples/herd_of_horses.jpg'
        + Label: horse, Conf: 0.99479
        + Label: horse, Conf: 0.99369
        + Label: horse, Conf: 0.96902
        + Label: horse, Conf: 0.99491
(5) Image: 'data/samples/messi.jpg'
        + Label: person, Conf: 0.99994
        + Label: person, Conf: 0.99983
        + Label: person, Conf: 0.99978
(6) Image: 'data/samples/person.jpg'
        + Label: person, Conf: 0.99884
        + Label: dog, Conf: 0.99282
(7) Image: 'data/samples/room.jpg'
        + Label: chair, Conf: 0.99906
        + Label: chair, Conf: 0.96983
        + Label: clock, Conf: 0.99970
(8) Image: 'data/samples/street.jpg'
        + Label: car, Conf: 0.99976
        + Label: car, Conf: 0.99381
        + Label: car, Conf: 0.99837
        + Label: car, Conf: 0.99777
        + Label: car, Conf: 0.97863
        + Label: car, Conf: 0.95236
        + Label: traffic light, Conf: 0.99995
        + Label: car, Conf: 0.61807
```
