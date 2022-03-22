# Bert-Question-Answering
 1. AI기술 자연어 처리 과정 2기 (구름) 

    기계독해 Question Answering
 2. 개인프로젝트

    1번의 코드를 함수로 간편화하고 korquad 데이터를 이용한 기계독해 Question Answering
    
- colab, pytorch, transformers 사용

# 1. AI기술 자연어 처리 과정 2기 (구름) - 기계독해 Question Answering
 - AI기술 자연어 처리 과정 2기 (구름)에서 진행한 BERT를 이용한 한국어 기계 독해 모델입니다.
 - 사용 데이터 : 교육기관에서 한국어 기계 독해 데이터 셋 12,037 개, 기계 독해 데이터 셋(AI Hub)
   - https://www.kaggle.com/c/k-digital-goorm-2-korean-mrc/data (제공된 데이터 셋)
   - https://aihub.or.kr/aidata/86 (AI Hub 기계 독해 데이터 셋)
   - 제공된 데이터의 개수가 적어 추가적으로 데이터의 형식이 뉴스 형식으로 비슷해 AI Hub의 기계 독해 데이터셋을 가져와 학습을 진행함
 - 사전 학습 모델: 'beomi/kcbert-bert', 'kykim/bert-kor-base', 'klue/bert-base'
   - 추가적으로 Eletra Model('monologg/koelectra-base-v3-discriminator') / Roberta Model('klue/roberta-base')을 사용해 테스트를 진행함

![image](https://user-images.githubusercontent.com/89580953/159446598-45c48177-30b5-4a2c-a1ce-74d65a7437a9.png)
- 위의 표의 결과로 인해 가장 높은 성능을 보인 klue/bert-base를 최종 사전 학습 모델을 사용함
- 추가적으로 klue/bert-base는 다른 사전 학습 모델과 비교하여 더 다양한 분야의 데이터를 사용했기 때문에 향후 다른 태스크에서도 높은 성능을 보일 것으로 기대됨

# 2. 개인프로젝트
- 1번의 코드를 함수화하여 간편하게 사용할 수 있도록 만든 모델입니다
- 사용 데이터 : korquad 데이터 셋
  - !wget https://korquad.github.io/dataset/KorQuAD_v1.0_train.json -O KorQuAD_v1.0_train.json
  - !wget https://korquad.github.io/dataset/KorQuAD_v1.0_dev.json -O KorQuAD_v1.0_dev.json
- 1번의 최종 모델의 하이퍼 파라미터를 이용해 학습을 진행함 
  - 이 모델에서는 최종 모델의 배치사이즈를 사용하면 GPU 메모리에 문제가 발생함
  - 따라서 이 모델에서는 Accumulation을 적용하여 1번의 배치사이즈와 유사하게 진행함 
 ![image](https://user-images.githubusercontent.com/89580953/159452718-8dd937cc-2b57-4c02-b41a-64c5c6d4b53b.png)
