# 错误
```
2026-07-08 06:40:36,281 - mmdet3d - INFO - workflow: [('train', 1)], max: 20 epochs
2026-07-08 06:40:36,283 - mmdet3d - INFO - Checkpoints will be saved to /workspace/runs/run-14e682de by $
ardDiskBackend.
Traceback (most recent call last):
  File "tools/train.py", line 87, in <module>
    main()
  File "tools/train.py", line 76, in main
    train_model(
  File "/workspace/mmdet3d/apis/train.py", line 126, in train_model
    runner.run(data_loaders, [("train", 1)])
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 127, in run
    epoch_runner(data_loaders[i], **kwargs)
  File "/workspace/mmdet3d/runner/epoch_based_runner.py", line 14, in train
    super().train(data_loader, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 50, in train
    self.run_iter(data_batch, train_mode=True, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 29, in run_iter
    outputs = self.model.train_step(data_batch, self.optimizer,
  File "/opt/conda/lib/python3.8/site-packages/mmcv/parallel/distributed.py", line 52, in train_step
    output = self.module.train_step(*inputs[0], **kwargs[0])
  File "/workspace/mmdet3d/models/fusion_models/base.py", line 78, in train_step
    losses = self(**data)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 253, in forward
    outputs = self.forward_single(
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 301, in forward_single
    feature = self.extract_camera_features(
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 133, in extract_camera_features
    x = self.encoders["camera"]["vtransform"](
 File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/workspace/mmdet3d/models/vtransforms/lss.py", line 76, in forward
    x = super().forward(*args, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 214, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/vtransforms/base.py", line 234, in forward
    x = self.bev_pool(geom, x)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 214, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/vtransforms/base.py", line 176, in bev_pool
    x = bev_pool(x, geom_feats, B, self.nx[2], self.nx[0], self.nx[1])
  File "/workspace/mmdet3d/ops/bev_pool/bev_pool.py", line 95, in bev_pool
    x = QuickCumsumCuda.apply(feats, coords, ranks, B, D, H, W)
  File "/workspace/mmdet3d/ops/bev_pool/bev_pool.py", line 45, in forward
    interval_lengths[-1] = x.shape[0] - interval_starts[-1]
IndexError: index -1 is out of bounds for dimension 0 with size 0
--------------------------------------------------------------------------
Primary job  terminated normally, but 1 process returned
a non-zero exit code. Per user-direction, the job has been aborted.
--------------------------------------------------------------------------
--------------------------------------------------------------------------
mpirun detected that one or more processes exited with non-zero status, thus causing
the job to be terminated. The first process to do so was:

  Process name: [[2313,1],0]
  Exit code:    1
--------------------------------------------------------------------------
root@a9144439c186:/workspace# 

```

```
2026-07-08 06:48:44,010 - mmdet3d - INFO - workflow: [('train', 1)], max: 20 epochs             [25/1549]
2026-07-08 06:48:44,012 - mmdet3d - INFO - Checkpoints will be saved to /workspace/runs/run-14e682de by H
ardDiskBackend.
Traceback (most recent call last):
  File "tools/train.py", line 87, in <module>
    main()
  File "tools/train.py", line 76, in main
    train_model(
  File "/workspace/mmdet3d/apis/train.py", line 126, in train_model
    runner.run(data_loaders, [("train", 1)])
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 127, in run
    epoch_runner(data_loaders[i], **kwargs)
  File "/workspace/mmdet3d/runner/epoch_based_runner.py", line 14, in train
    super().train(data_loader, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 50, in train
    self.run_iter(data_batch, train_mode=True, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 29, in run_iter
    outputs = self.model.train_step(data_batch, self.optimizer,
  File "/opt/conda/lib/python3.8/site-packages/mmcv/parallel/distributed.py", line 52, in train_step
    output = self.module.train_step(*inputs[0], **kwargs[0])
  File "/workspace/mmdet3d/models/fusion_models/base.py", line 78, in train_step
    losses = self(**data)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 253, in forward
    outputs = self.forward_single(
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 301, in forward_single
    feature = self.extract_camera_features(
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 133, in extract_camera_features
    x = self.encoders["camera"]["vtransform"](
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/workspace/mmdet3d/models/vtransforms/lss.py", line 76, in forward
    x = super().forward(*args, **kwargs)
 File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 214, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/vtransforms/base.py", line 234, in forward
    x = self.bev_pool(geom, x)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 214, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/vtransforms/base.py", line 176, in bev_pool
    x = bev_pool(x, geom_feats, B, self.nx[2], self.nx[0], self.nx[1])
  File "/workspace/mmdet3d/ops/bev_pool/bev_pool.py", line 95, in bev_pool
    x = QuickCumsumCuda.apply(feats, coords, ranks, B, D, H, W)
  File "/workspace/mmdet3d/ops/bev_pool/bev_pool.py", line 45, in forward
    interval_lengths[-1] = x.shape[0] - interval_starts[-1]
IndexError: index -1 is out of bounds for dimension 0 with size 0
--------------------------------------------------------------------------
Primary job  terminated normally, but 1 process returned
a non-zero exit code. Per user-direction, the job has been aborted.
--------------------------------------------------------------------------
--------------------------------------------------------------------------
mpirun detected that one or more processes exited with non-zero status, thus causing
the job to be terminated. The first process to do so was:

  Process name: [[4069,1],0]
  Exit code:    1
--------------------------------------------------------------------------
root@a9144439c186:/workspace# 
```

3
```
2026-07-08 06:54:27,545 - mmdet3d - INFO - workflow: [('train', 1)], max: 20 epochs
2026-07-08 06:54:27,549 - mmdet3d - INFO - Checkpoints will be saved to /workspace/runs/run-14e682de by $
ardDiskBackend.
Traceback (most recent call last):
  File "tools/train.py", line 87, in <module>
    main()
  File "tools/train.py", line 76, in main
    train_model(
  File "/workspace/mmdet3d/apis/train.py", line 126, in train_model
    runner.run(data_loaders, [("train", 1)])
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 127, in run
    epoch_runner(data_loaders[i], **kwargs)
  File "/workspace/mmdet3d/runner/epoch_based_runner.py", line 14, in train
    super().train(data_loader, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 50, in train
    self.run_iter(data_batch, train_mode=True, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 29, in run_iter
    outputs = self.model.train_step(data_batch, self.optimizer,
  File "/opt/conda/lib/python3.8/site-packages/mmcv/parallel/distributed.py", line 52, in train_step
    output = self.module.train_step(*inputs[0], **kwargs[0])
  File "/workspace/mmdet3d/models/fusion_models/base.py", line 78, in train_step
    losses = self(**data)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 253, in forward
    outputs = self.forward_single(
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 332, in forward_single
    x = self.fuser(features)
File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/workspace/mmdet3d/models/fusers/conv.py", line 23, in forward
    return super().forward(torch.cat(inputs, dim=1))
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/container.py", line 141, in forward
    input = module(input)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/conv.py", line 446, in forward
    return self._conv_forward(input, self.weight, self.bias)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/conv.py", line 442, in _conv_forward
    return F.conv2d(input, weight, bias, self.stride,
RuntimeError: Given groups=1, weight of size [256, 336, 3, 3], expected input[1, 208, 75, 75] to have 336
 channels, but got 208 channels instead
--------------------------------------------------------------------------
Primary job  terminated normally, but 1 process returned
a non-zero exit code. Per user-direction, the job has been aborted.
--------------------------------------------------------------------------
--------------------------------------------------------------------------
mpirun detected that one or more processes exited with non-zero status, thus causing
the job to be terminated. The first process to do so was:

  Process name: [[4849,1],0]
  Exit code:    1
--------------------------------------------------------------------------
root@a9144439c186:/workspace# 

```

4
```
2026-07-08 06:58:30,740 - mmdet3d - INFO - workflow: [('train', 1)], max: 20 epochs
2026-07-08 06:58:30,742 - mmdet3d - INFO - Checkpoints will be saved to /workspace/runs/run-ef6361d7 by H
ardDiskBackend.
Traceback (most recent call last):
  File "tools/train.py", line 87, in <module>
    main()
  File "tools/train.py", line 76, in main
    train_model(
  File "/workspace/mmdet3d/apis/train.py", line 126, in train_model
    runner.run(data_loaders, [("train", 1)])
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 127, in run
    epoch_runner(data_loaders[i], **kwargs)
  File "/workspace/mmdet3d/runner/epoch_based_runner.py", line 14, in train
    super().train(data_loader, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 50, in train
    self.run_iter(data_batch, train_mode=True, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/epoch_based_runner.py", line 29, in run_iter
    outputs = self.model.train_step(data_batch, self.optimizer,
  File "/opt/conda/lib/python3.8/site-packages/mmcv/parallel/distributed.py", line 52, in train_step
    output = self.module.train_step(*inputs[0], **kwargs[0])
  File "/workspace/mmdet3d/models/fusion_models/base.py", line 78, in train_step
    losses = self(**data)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 253, in forward
    outputs = self.forward_single(
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 340, in forward_single
    x = self.decoder["neck"](x)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 253, in forward
    outputs = self.forward_single(
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/fusion_models/bevfusion.py", line 340, in forward_single
    x = self.decoder["neck"](x)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 1102, in _call_impl
    return forward_call(*input, **kwargs)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/fp16_utils.py", line 128, in new_func
    output = old_func(*new_args, **new_kwargs)
  File "/workspace/mmdet3d/models/necks/second.py", line 96, in forward
    out = torch.cat(ups, dim=1)
RuntimeError: Sizes of tensors must match except in dimension 1. Expected size 75 but got size 76 for ten
sor number 1 in the list.
--------------------------------------------------------------------------
Primary job  terminated normally, but 1 process returned
a non-zero exit code. Per user-direction, the job has been aborted.
--------------------------------------------------------------------------
--------------------------------------------------------------------------
mpirun detected that one or more processes exited with non-zero status, thus causing
the job to be terminated. The first process to do so was:

  Process name: [[4429,1],0]
  Exit code:    1
--------------------------------------------------------------------------
root@a9144439c186:/workspace# 

```

5
```
2026-07-08 07:16:37,266 - mmdet3d - INFO - Epoch(val) [19][40]  map/floor/iou@max: 0.9720, map/floor/iou$
0.35: 0.9717, map/floor/iou@0.40: 0.9719, map/floor/iou@0.45: 0.9720, map/floor/iou@0.50: 0.9719, map/fl$
or/iou@0.55: 0.9717, map/floor/iou@0.60: 0.9712, map/floor/iou@0.65: 0.9704, map/carpet/iou@max: 0.0000, 
map/carpet/iou@0.35: 0.0000, map/carpet/iou@0.40: 0.0000, map/carpet/iou@0.45: 0.0000, map/carpet/iou@0.5
0: 0.0000, map/carpet/iou@0.55: 0.0000, map/carpet/iou@0.60: 0.0000, map/carpet/iou@0.65: 0.0000, map/obs
tacle/iou@max: 0.4335, map/obstacle/iou@0.35: 0.4304, map/obstacle/iou@0.40: 0.4335, map/obstacle/iou@0.4
5: 0.4196, map/obstacle/iou@0.50: 0.3761, map/obstacle/iou@0.55: 0.3151, map/obstacle/iou@0.60: 0.2404, m
ap/obstacle/iou@0.65: 0.1731, map/wall/iou@max: 0.0000, map/wall/iou@0.35: 0.0000, map/wall/iou@0.40: 0.0
000, map/wall/iou@0.45: 0.0000, map/wall/iou@0.50: 0.0000, map/wall/iou@0.55: 0.0000, map/wall/iou@0.60: 
0.0000, map/wall/iou@0.65: 0.0000, map/threshold/iou@max: 0.0000, map/threshold/iou@0.35: 0.0000, map/thr
eshold/iou@0.40: 0.0000, map/threshold/iou@0.45: 0.0000, map/threshold/iou@0.50: 0.0000, map/threshold/io
u@0.55: 0.0000, map/threshold/iou@0.60: 0.0000, map/threshold/iou@0.65: 0.0000, map/unknown/iou@max: 0.86
39, map/unknown/iou@0.35: 0.8625, map/unknown/iou@0.40: 0.8634, map/unknown/iou@0.45: 0.8639, map/unknown
/iou@0.50: 0.8626, map/unknown/iou@0.55: 0.8595, map/unknown/iou@0.60: 0.8541, map/unknown/iou@0.65: 0.8463, map/mean/iou@max: 0.37822026-07-08 07:16:48,570 - mmdet3d - INFO - Epoch [20][50/160]   lr: 8.234e-06, eta: 0:00:20, time: 0.226, data_time: 0.053, memory: 1959, loss/map/floor/focal: 0.0013, loss/map/carpet/focal: 0.0000, loss/map/o$stacle/focal: 0.0039, loss/map/wall/focal: 0.0000, loss/map/threshold/focal: 0.0000, loss/map/unknown/fo$al: 0.0052, loss: 0.0104, grad_norm: 0.02022026-07-08 07:16:57,360 - mmdet3d - INFO - Epoch [20][100/160]  lr: 2.498e-06, eta: 0:00:11, time: 0.176$ data_time: 0.006, memory: 1959, loss/map/floor/focal: 0.0015, loss/map/carpet/focal: 0.0000, loss/map/o$stacle/focal: 0.0033, loss/map/wall/focal: 0.0000, loss/map/threshold/focal: 0.0000, loss/map/unknown/fo$al: 0.0046, loss: 0.0094, grad_norm: 0.01992026-07-08 07:17:06,215 - mmdet3d - INFO - Epoch [20][150/160]  lr: 9.099e-08, eta: 0:00:01, time: 0.177$ data_time: 0.006, memory: 1959, loss/map/floor/focal: 0.0012, loss/map/carpet/focal: 0.0000, loss/map/o$stacle/focal: 0.0043, loss/map/wall/focal: 0.0000, loss/map/threshold/focal: 0.0000, loss/map/unknown/fo$al: 0.0054, loss: 0.0109, grad_norm: 0.0200
2026-07-08 07:17:08,165 - mmdet3d - INFO - Saving checkpoint at 20 epochs
[>>] 40/40, 8.0 task/s, elapsed: 5s, ETA:     0s   ] 0/40, elapsed: 0s, ETA:

2026-07-08 07:17:15,156 - mmdet3d - INFO - Epoch(val) [20][40]  map/floor/iou@max: 0.9718, map/floor/iou$0.35: 0.9717, map/floor/iou@0.40: 0.9718, map/floor/iou@0.45: 0.9717, map/floor/iou@0.50: 0.9716, map/fl$or/iou@0.55: 0.9712, map/floor/iou@0.60: 0.9707, map/floor/iou@0.65: 0.9697, map/carpet/iou@max: 0.0000, map/carpet/iou@0.35: 0.0000, map/carpet/iou@0.40: 0.0000, map/carpet/iou@0.45: 0.0000, map/carpet/iou@0.$0: 0.0000, map/carpet/iou@0.55: 0.0000, map/carpet/iou@0.60: 0.0000, map/carpet/iou@0.65: 0.0000, map/obs
tacle/iou@max: 0.4351, map/obstacle/iou@0.35: 0.4341, map/obstacle/iou@0.40: 0.4351, map/obstacle/iou@0.4
5: 0.4186, map/obstacle/iou@0.50: 0.3753, map/obstacle/iou@0.55: 0.3132, map/obstacle/iou@0.60: 0.2408, m
ap/obstacle/iou@0.65: 0.1747, map/wall/iou@max: 0.0000, map/wall/iou@0.35: 0.0000, map/wall/iou@0.40: 0.0
000, map/wall/iou@0.45: 0.0000, map/wall/iou@0.50: 0.0000, map/wall/iou@0.55: 0.0000, map/wall/iou@0.60: 
0.0000, map/wall/iou@0.65: 0.0000, map/threshold/iou@max: 0.0000, map/threshold/iou@0.35: 0.0000, map/thr
eshold/iou@0.40: 0.0000, map/threshold/iou@0.45: 0.0000, map/threshold/iou@0.50: 0.0000, map/threshold/io
u@0.55: 0.0000, map/threshold/iou@0.60: 0.0000, map/threshold/iou@0.65: 0.0000, map/unknown/iou@max: 0.86
35, map/unknown/iou@0.35: 0.8611, map/unknown/iou@0.40: 0.8625, map/unknown/iou@0.45: 0.8632, map/unknown
/iou@0.50: 0.8635, map/unknown/iou@0.55: 0.8614, map/unknown/iou@0.60: 0.8572, map/unknown/iou@0.65: 0.85
12, map/mean/iou@max: 0.3784
root@a9144439c186:/workspace# 

```

6
```
torchpack dist-run -np 1 python tools/visualize.py \
  configs/nuscenes/seg/robot-fusion-bev150-lss.yaml \
  --mode pred \
  --checkpoint ./runs/run-ef6361d7/latest.pth \
  --split val \
  --out-dir results/robot-fusion-bev150-lss/viz \
  --map-score 0.5
```

7
```
root@a9144439c186:/workspace# torchpack dist-run -np 1 python tools/visualize.py   configs/nuscenes/seg/robot-fusion-bev150-lss.yaml   --mode pred   --checkpoint ./runs/run-2de6c3fa/latest.pth   --split val   -
-out-dir results/robot-fusion-bev150-lss/viz   --map-score 0.5                                           
2026-07-08 07:46:14,810 - mmdet - INFO - load checkpoint from local path: pretrained/swin_tiny_patch4_window7_224.pth
load checkpoint from local path: ./runs/run-2de6c3fa/latest.pth
The model and loaded state dict do not match exactly

missing keys in source state_dict: encoders.camera.vtransform.dx, encoders.camera.vtransform.bx, encoders.camera.vtransform.nx, encoders.camera.vtransform.frustum

100% 40/40 [00:05<00:00,  6.84it/s]
root@a9144439c186:/workspace# 
```