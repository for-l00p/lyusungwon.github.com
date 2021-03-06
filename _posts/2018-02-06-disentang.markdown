---
layout: post
title:  "Early Visual Concept Learning with Unsupervised Deep Learning"
date:   2018-02-06 12:21:59
author: Sungwon Lyu
categories: studies
tags: deep-learning generative-models
---
## WHY? 
이미지의 피쳐를 추출할 때, 한 피쳐 값이 이미지에 대하여 우리가 인지할 수 있는 특성을 나타낸다면 이 값을 조정하여 이미지를 의도적으로 생성할 수 있을 것이다. 이렇게 이미지의 feature를 우리가 의도한 방식으로 추출하는 것을 disentangling이라고 한다. 이러한 disentangled factors는 이미지의 특성 및 추상화된 개념을 나타내게 된다. 

## WHAT?
아기가 처음 처하는 상황과 마찬가지로 상황을 제한하여 unsupervised하게 disentangling하는 방법을 제시한다. VAE 프레임 웍을 통하여 잠재적인 z를 추출하는데 다음식을 최대화한다: \\
$$L(\theta, \phi ; x) = E_{q_{\phi}}(log p_{\theta}(x \mid z)) - \beta D_{KL}(q_{\phi}(z\mid x)\parallel p(x))$$\\
Latent variable $$p(z)$$의 분포와 $$q(z|x)$$의 분포간의 KL Divergence를 라그랑지안 제한으로 두어 $$p(x|z)$$를 최대화 하는데 이 제약의 가중치를 $$\beta$$로 준다. 

## So
연속성이 있는 그림 집합으로 부터 x위치, y위치, 크기, 회전과 같은 disentangled factor를 추출하는데 어느정도 성과가 있었다. 