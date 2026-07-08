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