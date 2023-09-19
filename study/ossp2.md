---
tags:
  - study
---

# OSSP2 주차 과제
<center>202111278 컴퓨터공학부 김환희</center>

## Gym Car Racing 정리
### References
- Chris Campbell. (2014). Box2D C++ tutorials - Top-down car physics
  http://www.iforce2d.net/b2dtut/top-down-car
- Gym documentation - Car Racing
  https://www.gymlibrary.dev/environments/box2d/car_racing/
### Action
Continuous와 discrete가 존재한다.
#### Continuous
3 actions
- Steering (-1 ~ +1)
- Gas
- Breaking
#### Discrete
5 actions
- Do nothing
- Steer left
- Steer right
- Gas
- Brake

### Observation
3채널의 96x96픽셀
- shape: (96, 96, 3)
- 픽셀 당 범위: \[0, 255\]
### Reward
$$-0.1t + \frac{1000}{N}$$
- t: frame
- N: total number of tile visited
### Starting state
도로 중심에서 시작
### Episode termination
- All of the tiles are visited
- Go outside of the playfield
### Import 방법
```python
gym.make("CarRacing-v2") 
``` 
### Version history
| Version | Description      |
| ------- | ---------------- |
| v0      | Original version |
| v1      | - Change track completion logic, domain randomization                 |
