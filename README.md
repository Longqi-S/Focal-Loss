# Implementation of Focal-Loss
The implementation of Focal-Loss Using Caffe;
### Citation
The paper is available at https://arxiv.org/abs/1708.02002.
### Usage
```
// Focal Loss layer
optional SoftmaxFocalLossParameter softmax_focal_loss_param = XXX; (XXX is determined by your own caffe)

message SoftmaxFocalLossParameter{
  optional float alpha = 1 [default = 0.25];
  optional float gamma = 2 [default = 2];
}

layer {
  name: "focal_loss"
  type: "SoftmaxWithFocalLoss"
  bottom: "ip2"
  bottom: "label"
  top: "focal_loss"
  softmax_focal_loss_param {
    alpha: 1 
    gamma: 1
  }
}
```
### Notes
Loss = -1/M * sum_t alpha * (1 - p_t) ^ gamma * log(p_t)
### Sigmoid Form
Here use `softmax` instead of `sigmoid` function.  
If you want see how to use `sigmoid` to implement `Focal Loss`, please see https://github.com/sciencefans/Focal-Loss to get more information.  
### Other Implemtation
Caffe: https://github.com/zimenglan-sysu-512/Focal-Loss;

