# Bert-Question-Answering
 1. AI기술 자연어 처리 과정 2기 (구름) 

    기계독해 Question Answering
 2. 개인프로젝트

    1번의 코드를 함수로 간편화하고 korquad 데이터를 이용한 기계독해 Question Answering
    
- colab, pytorch, transformers 사용

# 1. AI기술 자연어 처리 과정 2기 (구름) - 기계독해 Question Answering
 - AI기술 자연어 처리 과정 2기 (구름)에서 진행한 BERT를 이용해 영어 문장 긍정/부정 분류하는 Text Classfication Task입니다
 - 사용 데이터 : 교육기관에서 한국어 기계 독해 데이터 셋 12,037 개, 기계 독해 데이터 셋(AI Hub)
   - https://www.kaggle.com/c/k-digital-goorm-2-korean-mrc/data (제공된 데이터 셋)
   - https://aihub.or.kr/aidata/86 (AI Hub 기계 독해 데이터 셋)
   - 제공된 데이터의 개수가 적어 추가적으로 데이터의 형식이 뉴스 형식으로 비슷해 AI Hub의 기계 독해 데이터셋을 가져와 학습을 진행함
 - 사전 학습 모델: 'beomi/kcbert-bert', 'kykim/bert-kor-base', 'klue/bert-base'
   - 추가적으로 Eletra Model('monologg/koelectra-base-v3-discriminator') / Roberta Model('klue/roberta-base')을 사용해 테스트를 진행함
![image](https://user-images.githubusercontent.com/89580953/159446598-45c48177-30b5-4a2c-a1ce-74d65a7437a9.png)
