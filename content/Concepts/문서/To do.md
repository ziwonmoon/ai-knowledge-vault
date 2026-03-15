---
date created: Thursday, March 12th 2026, 1:25:19 pm
date modified: Sunday, March 15th 2026, 11:22:04 am
---
일단은 "Pytorch Deep Learning"을 메인으로 학습하자.
그리고 병행하면서 할 게 있는데, 실습(직접 모델을 구성해보기), 논문 읽기. 수학적 기반 마련하기. 이정도이다. 언급된 순서대로 하면 될 것 같다.
 - [ ] [[Deep Residual Learning for Image Recognition|ResNet]] 논문. 이미 읽기 시작해버려서 일단 마무리하자
 - [ ] Breast Cancer Wisconsin (유방암 판별 문제, 정형 데이터 처리)
 - [ ] Titanic (타이타닉 생존자 문제, 정형 데이터 처리)
 - [ ] CIFAR-10 (ResNet도 실험하기, 이미지 분류)
 - [ ] IMDB Sentiment (영화 리뷰 긍정/부정 분류, NLP)
 - [ ] UCI Human Activity Recognition (인간 행동 분류, 시계열 데이터)
 - [ ] Dogs vs Cats (이미지 분류)

논문. 
 - [ ] --딥러닝과 CNN--
	 - [ ] ImageNet Classification with Deep Convolutional Neural Networks
	 - [ ] Very Deep Convolutional Networks for Large-Scale Image Recognition
	 - [ ] Going Deeper with Convolutions
	 - [ ] [[Deep Residual Learning for Image Recognition]]
	 - [ ] Densely Connected Convolutional Networks
 - [ ] --학습 안정화와 최적화--
	 - [ ] Understanding the Difficulty of Training Deep Feedforward Neural Networks
	 - [ ] Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift
	 - [ ] Adam: A Method for Stochastic Optimization
 - [ ] --Attention & Transformer--
	 - [ ] Neural Machine Translation by Jointly Learning to Align and Translate
	 - [ ] Attention is All you Need
	 - [ ] BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding
	 - [ ] Language Models are Few-Shot Learners
 - [ ] --CNN & Transformer--
	 - [ ] An Image is Worth 16x16 Words
	 - [ ] Training Compute-Optimal Large Language Models

"Deep Learning Pytorch"책을 읽으면서는 위의 리스트 순서대로(실습,논문)을 병행하기
책을 다 읽으면 수학공부와 위의 리스트(실습,논문)을 병행하기
수학공부
 - 머신러닝을 위한 수학 - 이병준
 - Learning From Data

개인적 호기심
 - [ ] MLP를 기준으로 봤을 때, 수학적으로 표현할 수 있는 함수?  어떤 함수는 표현할 수 있고 어떤 함수는 표현할 수 있는지에 알 수 있나?
 - [ ] 배운 모델들, 코드 참고하지 말고 직접 구현해보기 nn.RNN() 같은 구현체는 사용하지 말 것 
	* [ ] 굉장히 어려울것 같은데.. 한번은 해보자 한번은.. 올인하지말고 시간 짬짬이 내서 조금씩 만들어보자.
	* [ ] 역전파 기능도 직접 구현해보기? GD,SGD, Mini-Batch GD? 가능할까? 너무 어려울까? 적어도 트라이