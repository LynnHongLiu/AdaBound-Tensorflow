# AdaBound-Tensorflow
Simple Tensorflow implementation of ["Adaptive Gradient Methods with Dynamic Bound of Learning Rate" (ICLR 2019)](https://openreview.net/forum?id=Bkg3g2R9FX)

## Hyperparameter
* `learning_rate` = 0.01
* `final_lr` = 0.1
* `beta1` = 0.9
* `beta2` = 0.999

## Usage
```python
  from AdaBound import AdaBoundOptimizer
  
  train_op = AdaBoundOptimizer(learning_rate=0.01, final_lr=0.1, beta1=0.9, beta2=0.999, amsgrad=False).minimize(loss)
```

## Network Architecture
```python
  x = fully_connected(inputs=images, units=100)
  x = relu(x)
  logits = fully_connected(inputs=x, units=10)
```

## Fashion-mnist Result

### lr=0.01, final_lr=0.1, beta1=0.9, beta2=0.99, batch_size=32

<div align="center">
   <img src="/assets/99_loss.png" width="420">
  <img src="/assets/99_acc.png"  width="420">
</div>

*Optimizer* | *Best Test Acc* | 
:---: | :---: | 
SGD | 86.45% |
Adam | 85.81% |
AMSGrad | 87.28% |
AdaBound | 87.68% |
AMSBound | **87.76%** |

### lr=0.01, final_lr=0.1, beta1=0.9, beta2=0.999, batch_size=32

<div align="center">
   <img src="/assets/999_loss.png" width="420">
  <img src="/assets/999_acc.png"  width="420">
</div>

*Optimizer* | *Best Test Acc* | 
:---: | :---: | 
SGD | 86.33% |
Adam | 86.14% |
AMSGrad | 86.63% |
AdaBound | 86.88% |
AMSBound | **87.25%** |

## Related works
* [AMSGrad-Tensorflow](https://github.com/taki0112/AMSGrad-Tensorflow)

## Author
Junho Kim
