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

8
```
root@a9144439c186:/workspace# CUDA_VISIBLE_DEVICES=2 torchpack dist-run -np 1 python tools/visualize.py  configs/nuscenes/seg/mytest-fusion-bev256d2-lss.yaml  --mode pred  --checkpoint /runs/run-2de6c3fa/latest.pth   --split val --out-dir results/mytest_habitat/viz  --map-score 0.5
2026-07-08 10:56:13,597 - mmdet - INFO - load checkpoint from local path: pretrained/swin_tiny_patch4_window7_224.pth
load checkpoint from local path: /runs/run-2de6c3fa/latest.pth
Traceback (most recent call last):
  File "tools/visualize.py", line 169, in <module>
    main()
  File "tools/visualize.py", line 76, in main
    load_checkpoint(model, args.checkpoint, map_location="cpu")
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/checkpoint.py", line 531, in load_checkpoint
    checkpoint = _load_checkpoint(filename, map_location, logger)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/checkpoint.py", line 470, in _load_checkpoint
    return CheckpointLoader.load_checkpoint(filename, map_location, logger)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/checkpoint.py", line 249, in load_checkpoint
    return checkpoint_loader(filename, map_location)
  File "/opt/conda/lib/python3.8/site-packages/mmcv/runner/checkpoint.py", line 265, in load_from_local
    raise IOError(f'{filename} is not a checkpoint file')
OSError: /runs/run-2de6c3fa/latest.pth is not a checkpoint file
--------------------------------------------------------------------------
Primary job  terminated normally, but 1 process returned
a non-zero exit code. Per user-direction, the job has been aborted.
--------------------------------------------------------------------------
--------------------------------------------------------------------------
mpirun detected that one or more processes exited with non-zero status, thus causing
the job to be terminated. The first process to do so was:

  Process name: [[21810,1],0]
  Exit code:    1
--------------------------------------------------------------------------
root@a9144439c186:/workspace# 

```
9
```
root@a9144439c186:/workspace# CUDA_VISIBLE_DEVICES=2 torchpack dist-run -np 1 python tools/visualize.py  
configs/nuscenes/seg/mytest-fusion-bev256d2-lss.yaml  --mode pred  --checkpoint runs/run-2de6c3fa/latest.
pth   --split val --out-dir results/mytest_habitat/viz  --map-score 0.5                                  
2026-07-08 10:58:52,951 - mmdet - INFO - load checkpoint from local path: pretrained/swin_tiny_patch4_win
dow7_224.pth
load checkpoint from local path: runs/run-2de6c3fa/latest.pth
The model and loaded state dict do not match exactly

size mismatch for encoders.camera.vtransform.depthnet.weight: copying a param with shape torch.Size([178,
 256, 1, 1]) from checkpoint, the shape in current model is torch.Size([230, 256, 1, 1]).
size mismatch for encoders.camera.vtransform.depthnet.bias: copying a param with shape torch.Size([178]) 
from checkpoint, the shape in current model is torch.Size([230]).
size mismatch for fuser.0.weight: copying a param with shape torch.Size([256, 208, 3, 3]) from checkpoint
, the shape in current model is torch.Size([256, 336, 3, 3]).
missing keys in source state_dict: encoders.camera.vtransform.dx, encoders.camera.vtransform.bx, encoders.camera.vtransform.nx, encoders.camera.vtransform.frustum

Traceback (most recent call last):
  File "tools/visualize.py", line 169, in <module>
    main()
  File "tools/visualize.py", line 79, in main
    model.cuda(),
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 680, in cuda
    return self._apply(lambda t: t.cuda(device))
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 570, in _apply
    module._apply(fn)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 570, in _apply
    module._apply(fn)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 570, in _apply
    module._apply(fn)
  [Previous line repeated 2 more times]
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 593, in _apply
    param_applied = fn(param)
  File "/opt/conda/lib/python3.8/site-packages/torch/nn/modules/module.py", line 680, in <lambda>
    return self._apply(lambda t: t.cuda(device))
RuntimeError: CUDA error: out of memory
CUDA kernel errors might be asynchronously reported at some other API call,so the stacktrace below might 
be incorrect.
For debugging consider passing CUDA_LAUNCH_BLOCKING=1.
--------------------------------------------------------------------------
Primary job  terminated normally, but 1 process returned
a non-zero exit code. Per user-direction, the job has been aborted.
--------------------------------------------------------------------------
--------------------------------------------------------------------------
mpirun detected that one or more processes exited with non-zero status, thus causing
the job to be terminated. The first process to do so was:

  Process name: [[23090,1],0]
  Exit code:    1
--------------------------------------------------------------------------
root@a9144439c186:/workspace# 

```






nvidia-smi --query-compute-apps=gpu_uuid,pid,process_name,used_gpu_memory --format=csv
nvidia-smi
pgrep -af 'nvidia-cuda-mps|tools/train.py|torchpack|mpirun'
nvidia-smi -q -d COMPUTE


(base) [lixiaoxiao19@localhost original_bs2_ep30]$ nvidia-smi --query-compute-apps=gpu_uuid,pid,process_name,used_gpu_memory --format=csv
gpu_uuid, pid, process_name, used_gpu_memory [MiB]
GPU-230e70f3-fcca-c799-d8c2-bb5185aee96c, 72210, /root/miniconda3/envs/openstereo/bin/python, 41502 MiB
GPU-d49b39db-9a12-3085-d584-4a3f323241a5, 72211, /root/miniconda3/envs/openstereo/bin/python, 41510 MiB
GPU-6241bc2f-4169-5fd4-d518-f0a05796c981, 72212, /root/miniconda3/envs/openstereo/bin/python, 41510 MiB
GPU-b4d3afca-94cc-a3d4-2263-a89126463ab2, 72213, /root/miniconda3/envs/openstereo/bin/python, 41470 MiB
GPU-900866b0-28a5-b692-08a3-fa5554befd5e, 76956, python, 18902 MiB
GPU-717b4115-dc61-6cfb-fe77-0a25f4988f29, 82706, /root/miniconda3/envs/openstereo/bin/python, 2140 MiB
GPU-ecca4f34-d4ac-7e00-5b68-246d89bc352b, 88098, ./build/bin/llama-server, 26076 MiB
(base) [lixiaoxiao19@localhost original_bs2_ep30]$ nvidia-smi
Wed Jul 29 15:44:41 2026       
+---------------------------------------------------------------------------------------+
| NVIDIA-SMI 545.23.08              Driver Version: 545.23.08    CUDA Version: 12.3     |
|-----------------------------------------+----------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |         Memory-Usage | GPU-Util  Compute M. |
|                                         |                      |               MIG M. |
|=========================================+======================+======================|
|   0  NVIDIA L40                     On  | 00000000:34:00.0 Off |                    0 |
| N/A   63C    P0             244W / 300W |  41532MiB / 46068MiB |     99%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   1  NVIDIA L40                     On  | 00000000:35:00.0 Off |                    0 |
| N/A   68C    P0             253W / 300W |  41540MiB / 46068MiB |     99%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   2  NVIDIA L40                     On  | 00000000:36:00.0 Off |                    0 |
| N/A   69C    P0             253W / 300W |  41540MiB / 46068MiB |     79%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   3  NVIDIA L40                     On  | 00000000:37:00.0 Off |                    0 |
| N/A   70C    P0             263W / 300W |  41500MiB / 46068MiB |     81%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   4  NVIDIA L40                     On  | 00000000:9B:00.0 Off |                    0 |
| N/A   47C    P0             130W / 300W |  18914MiB / 46068MiB |     46%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   5  NVIDIA L40                     On  | 00000000:9C:00.0 Off |                    0 |
| N/A   43C    P0              89W / 300W |   2160MiB / 46068MiB |    100%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   6  NVIDIA L40                     On  | 00000000:9D:00.0 Off |                    0 |
| N/A   35C    P8              34W / 300W |     55MiB / 46068MiB |      0%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   7  NVIDIA L40                     On  | 00000000:9E:00.0 Off |                    0 |
| N/A   35C    P0              75W / 300W |  26088MiB / 46068MiB |      0%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
                                                                                         
+---------------------------------------------------------------------------------------+
| Processes:                                                                            |
|  GPU   GI   CI        PID   Type   Process name                            GPU Memory |
|        ID   ID                                                             Usage      |
|=======================================================================================|
|    0   N/A  N/A     72210      C   ...niconda3/envs/openstereo/bin/python    41502MiB |
|    1   N/A  N/A     72211      C   ...niconda3/envs/openstereo/bin/python    41510MiB |
|    2   N/A  N/A     72212      C   ...niconda3/envs/openstereo/bin/python    41510MiB |
|    3   N/A  N/A     72213      C   ...niconda3/envs/openstereo/bin/python    41470MiB |
|    4   N/A  N/A     76956      C   python                                    18902MiB |
|    5   N/A  N/A     82706      C   ...niconda3/envs/openstereo/bin/python     2140MiB |
|    7   N/A  N/A     88098      C   ./build/bin/llama-server                  26076MiB |
+---------------------------------------------------------------------------------------+
(base) [lixiaoxiao19@localhost original_bs2_ep30]$ pgrep -af 'nvidia-cuda-mps|tools/train.py|torchpack|mpirun'
72205 /root/miniconda3/envs/openstereo/bin/python /root/miniconda3/envs/openstereo/bin/torchrun --nnodes=1 --nproc_per_node=4 --rdzv_backend=c10d --rdzv_endpoint=localhost:23456 tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
72210 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
72211 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
72212 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
72213 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
76950 /bin/sh -c mpirun --allow-run-as-root -np 1 -H localhost:1 -bind-to none -map-by slot -x CONDA_DIR -x CUDA_VERSION -x CUDA_VISIBLE_DEVICES -x DEBIAN_FRONTEND -x HOME -x HOSTNAME -x LC_CTYPE -x LD_LIBRARY_PATH -x LIBRARY_PATH -x MASTER_HOST -x NCCL_VERSION -x NVARCH -x NVIDIA_DRIVER_CAPABILITIES -x NVIDIA_PRODUCT_NAME -x NVIDIA_REQUIRE_CUDA -x NVIDIA_VISIBLE_DEVICES -x NV_CUDA_COMPAT_PACKAGE -x NV_CUDA_CUDART_DEV_VERSION -x NV_CUDA_CUDART_VERSION -x NV_CUDA_LIB_VERSION -x NV_CUDA_NSIGHT_COMPUTE_DEV_PACKAGE -x NV_CUDA_NSIGHT_COMPUTE_VERSION -x NV_LIBCUBLAS_DEV_PACKAGE -x NV_LIBCUBLAS_DEV_PACKAGE_NAME -x NV_LIBCUBLAS_DEV_VERSION -x NV_LIBCUBLAS_PACKAGE -x NV_LIBCUBLAS_PACKAGE_NAME -x NV_LIBCUBLAS_VERSION -x NV_LIBCUSPARSE_DEV_VERSION -x NV_LIBCUSPARSE_VERSION -x NV_LIBNCCL_DEV_PACKAGE -x NV_LIBNCCL_DEV_PACKAGE_NAME -x NV_LIBNCCL_DEV_PACKAGE_VERSION -x NV_LIBNCCL_PACKAGE -x NV_LIBNCCL_PACKAGE_NAME -x NV_LIBNCCL_PACKAGE_VERSION -x NV_LIBNPP_DEV_PACKAGE -x NV_LIBNPP_DEV_VERSION -x NV_LIBNPP_PACKAGE -x NV_LIBNPP_VERSION -x NV_NVML_DEV_VERSION -x NV_NVPROF_DEV_PACKAGE -x NV_NVPROF_VERSION -x NV_NVTX_VERSION -x PATH -x PIP_DEFAULT_TIMEOUT -x PIP_INDEX_URL -x PIP_RETRIES -x PWD -x SHLVL -x TERM -x _ -mca pml ob1 -mca btl ^openib -mca btl_tcp_if_exclude docker0,lo /opt/conda/bin/python -m torchpack.launch.assets.silentrun python tools/train.py configs/robot_bev/seg/robotbev_camera_lidar_lss.yaml --run-dir /output/base/original_parameters_bs2_ep30 dataset_root=/data/ data.samples_per_gpu=2 data.workers_per_gpu=2 optimizer.lr=5e-5 max_epochs=30
76951 mpirun --allow-run-as-root -np 1 -H localhost:1 -bind-to none -map-by slot -x CONDA_DIR -x CUDA_VERSION -x CUDA_VISIBLE_DEVICES -x DEBIAN_FRONTEND -x HOME -x HOSTNAME -x LC_CTYPE -x LD_LIBRARY_PATH -x LIBRARY_PATH -x MASTER_HOST -x NCCL_VERSION -x NVARCH -x NVIDIA_DRIVER_CAPABILITIES -x NVIDIA_PRODUCT_NAME -x NVIDIA_REQUIRE_CUDA -x NVIDIA_VISIBLE_DEVICES -x NV_CUDA_COMPAT_PACKAGE -x NV_CUDA_CUDART_DEV_VERSION -x NV_CUDA_CUDART_VERSION -x NV_CUDA_LIB_VERSION -x NV_CUDA_NSIGHT_COMPUTE_DEV_PACKAGE -x NV_CUDA_NSIGHT_COMPUTE_VERSION -x NV_LIBCUBLAS_DEV_PACKAGE -x NV_LIBCUBLAS_DEV_PACKAGE_NAME -x NV_LIBCUBLAS_DEV_VERSION -x NV_LIBCUBLAS_PACKAGE -x NV_LIBCUBLAS_PACKAGE_NAME -x NV_LIBCUBLAS_VERSION -x NV_LIBCUSPARSE_DEV_VERSION -x NV_LIBCUSPARSE_VERSION -x NV_LIBNCCL_DEV_PACKAGE -x NV_LIBNCCL_DEV_PACKAGE_NAME -x NV_LIBNCCL_DEV_PACKAGE_VERSION -x NV_LIBNCCL_PACKAGE -x NV_LIBNCCL_PACKAGE_NAME -x NV_LIBNCCL_PACKAGE_VERSION -x NV_LIBNPP_DEV_PACKAGE -x NV_LIBNPP_DEV_VERSION -x NV_LIBNPP_PACKAGE -x NV_LIBNPP_VERSION -x NV_NVML_DEV_VERSION -x NV_NVPROF_DEV_PACKAGE -x NV_NVPROF_VERSION -x NV_NVTX_VERSION -x PATH -x PIP_DEFAULT_TIMEOUT -x PIP_INDEX_URL -x PIP_RETRIES -x PWD -x SHLVL -x TERM -x _ -mca pml ob1 -mca btl ^openib -mca btl_tcp_if_exclude docker0,lo /opt/conda/bin/python -m torchpack.launch.assets.silentrun python tools/train.py configs/robot_bev/seg/robotbev_camera_lidar_lss.yaml --run-dir /output/base/original_parameters_bs2_ep30 dataset_root=/data/ data.samples_per_gpu=2 data.workers_per_gpu=2 optimizer.lr=5e-5 max_epochs=30
76955 /bin/sh -c python tools/train.py configs/robot_bev/seg/robotbev_camera_lidar_lss.yaml --run-dir /output/base/original_parameters_bs2_ep30 dataset_root=/data/ data.samples_per_gpu=2 data.workers_per_gpu=2 optimizer.lr=5e-5 max_epochs=30 2>&1
76956 python tools/train.py configs/robot_bev/seg/robotbev_camera_lidar_lss.yaml --run-dir /output/base/original_parameters_bs2_ep30 dataset_root=/data/ data.samples_per_gpu=2 data.workers_per_gpu=2 optimizer.lr=5e-5 max_epochs=30
82662 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82663 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82664 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82665 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82666 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82667 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82668 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82669 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82670 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82671 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82672 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82673 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82674 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82675 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82676 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82677 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82678 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82679 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82680 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82681 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82682 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82683 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82684 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82685 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82686 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82687 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82688 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82689 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82690 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82691 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82692 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82693 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82694 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82695 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82696 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82697 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82698 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82699 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82700 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82702 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82703 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82704 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82705 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82706 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82707 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82708 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82709 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82710 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82711 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82712 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82713 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82714 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82715 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82722 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82723 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82724 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82725 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82726 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82727 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82729 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82731 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82732 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82742 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
82748 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82784 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_multi.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_multipre_dispall_ep20
82806 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
82870 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
82934 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83000 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83064 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83192 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83320 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83449 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83577 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83834 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
83964 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
84029 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
84157 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
84283 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
84413 /root/miniconda3/envs/openstereo/bin/python -u tools/train.py --dist_mode --cfg_file cfgs/aimon/1688/aimon_outground.yaml --extra_tag debug --pin_memory --save_root_dir ./output/v1_outground_mulbxbs
96187 python tools/train.py configs/robot_bev/seg/robotbev_camera_lidar_lss.yaml --run-dir /output/base/original_parameters_bs2_ep30 dataset_root=/data/ data.samples_per_gpu=2 data.workers_per_gpu=2 optimizer.lr=5e-5 max_epochs=30
96251 python tools/train.py configs/robot_bev/seg/robotbev_camera_lidar_lss.yaml --run-dir /output/base/original_parameters_bs2_ep30 dataset_root=/data/ data.samples_per_gpu=2 data.workers_per_gpu=2 optimizer.lr=5e-5 max_epochs=30
(base) [lixiaoxiao19@localhost original_bs2_ep30]$ nvidia-smi -q -d COMPUTE

==============NVSMI LOG==============

Timestamp                                 : Wed Jul 29 15:45:35 2026
Driver Version                            : 545.23.08
CUDA Version                              : 12.3

Attached GPUs                             : 8
GPU 00000000:34:00.0
    Compute Mode                          : Default

GPU 00000000:35:00.0
    Compute Mode                          : Default

GPU 00000000:36:00.0
    Compute Mode                          : Default

GPU 00000000:37:00.0
    Compute Mode                          : Default

GPU 00000000:9B:00.0
    Compute Mode                          : Default

GPU 00000000:9C:00.0
    Compute Mode                          : Default

GPU 00000000:9D:00.0
    Compute Mode                          : Default

GPU 00000000:9E:00.0
    Compute Mode                          : Default

(base) [lixiaoxiao19@localhost original_bs2_ep30]$ 