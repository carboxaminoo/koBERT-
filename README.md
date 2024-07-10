# 스트레스 받아 닭발 주문하는 손가락 멈춰!

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white"> <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=PyTorch&logoColor=white"> <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white">

## Background

### 1. Covid-19
<img src=https://github.com/carboxaminoo/koBERT-Project/assets/149589697/46499a5b-7fc6-4023-aac7-32a186464175 width=30%>

#### Corona Blue: 코로나19 + 우울증
Covid-19의 장기화로 인해 지쳐버린 마음이 우울함과 무기력함 등으로 발현되는 상태
#### Corona Red(Angry): 코로나19 + 분노
장기화되는 감염병 상황에서 생겨난 우울이나 불안 등이 분노로 폭발하는 상태


### 2. 감정과 음식의 도식화
![image](https://github.com/carboxaminoo/koBERT-Project/assets/149589697/d2c56218-242b-4abd-9620-b69ef7478535)

<img src=https://github.com/carboxaminoo/koBERT-Project/assets/149589697/b191f2be-2e4e-480c-8a0c-0192fa6e3722 width = 70%> 

사람들은 특정 감정을 가지고 있을 때 찾게되는 음식이 있고 이를 도식화하여 어떤 기분일때 먹어야 하는 음식을 정해둔다. <br>
실제 대학생을 대상으로 특정 감정에서 먹는 음식을 조사한 결과 슬픈 상황에서 초콜렛, 분노한 상황에서 매운 음식이 상위를 차지하고 있다.(김지예 & 이상희, 2014). <br><br>
<strong>But,</strong> 이러한 음식이 스트레스나 기분을 좀 더 개선할 수 있는 효과를 가지고 있기에 사람들이 자주 찾게 되지만 캡사이신, 카페인을 과도하게 섭취하면 위염, 위궤양이 올 수 있어 섭취를 줄이는 것이 좋다.

## Problem Definition
#### 3년동안 이어진 펜데믹에 의한 감정 소모
#### 몸에 좋지 않은 음식으로 감정 해소
#### ⭐ 사용자의 기분에 따라 건강한 음식을 추천해주면 어떨까?

## Data Preparation
#### 한국어 감정 정보가 포함된 단발성 대화 데이터셋(AIHUB)
- 짧은 대화 텍스트와 해당 텍스트에 드러난 감정, 총 2개의 컬럼
- 공포, 놀람, 분노, 슬픔, 중립, 행복, 혐오
- 총 38,594 문장

#### 무료 레시피 데이터 (농식품 빅데이터 거래소-만개의레시피)
- 레시피 요리 플랫폼인 '만개의레시피'에 존재하는 레시피 데이터
- 레시피 일련 번호, 레시피 제목, 요리 명 등 총 18개의 칼럼

#### 부정적 감정과 음식 데이터
- 부정적 감정들과 완화에 도움이 되는 식재료 및 도움 성분에 대한 데이터
- 직접 조사 및 생성된 데이터
- 감정, 식재료, 완화 성분 총 3개의 칼럼
 
## Model
#### KoBERT (Korean Bidirectional Encoder Representations from Transformers) [github](https://github.com/SKTBrain/KoBERT)
- 구글에서 발표한 기계번역 모델 BERT를 SKT Brain에서 한국어 데이터로 학습시켜 공개한 모델
- Transformer Encoder를 쌓아올린 구조
- Optimizer: AdamW
- Loss Function: Cross Entropy
- [코드 참조](https://github.com/deepseasw/bert-naver-movie-review)


## Result
![image](https://github.com/carboxaminoo/koBERT-Project/assets/149589697/5e27a1a0-de46-4971-9858-00b908896107)

## Limitation
#### 사람의 복잡한 감정을 세분하여 추천할 수 없다.
#### 사람이 싫어하는 음식이 추천될 수 있다.
#### 감정 완화 성분에 대한 데이터의 한정성으로 한정적인 답변만 할 수 있다.

## Reference
김지예, & 이상희. (2014). 대학생들의 정서에 따른 컴포트 푸드의 차이: 성차를 중심으로. 감성과학, 17(3), 15-28.
