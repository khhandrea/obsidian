---
created-at: 2024-01-16T16:45
tags: 
description:
---
# Predictive navigation agent pseudo code

## Training
``` python
obs = env.reset()
intrinsic_reward = 0
extrinsic_reward = 0
pred_action = None
while not done:
	feature = inverse_net(obs, pred_action)
	z, intrinsic_reward = forward_net(pred_action, feature)
	reward = extrinsic_reward + intrinsic_reward
	action = controller_net(z, feature, extra, reward)
	obs, extrinsic_reward = env.step(action)
	
	pred_action = action
```

## InverseNetwork
``` python
def forward(obs, pred_action) -> feature:
	pass
```

## ForwardNetwork
``` python
def forwrad(pred_action, feature) -> z, reward:
	pass
```
## ControllerNetwork
``` python
def forward(z, feature, extra, reward) -> action:
	pass
```

