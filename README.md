# Bert-Classification
1. AI기술 자연어 처리 과정 2기 (구름)
   
   영어 문장 감성 분석
 2. 개인 프로젝트
    
    앞서 만든 영어 문장 긍/부정 분류기에 이어 함수를 간편화하고 다중 분류의 문제도 해결할 수 있도록 만들었습니다

 - colab, pytorch, transformers 사용

# 1. Text Classification
 - AI기술 자연어 처리 과정 2기 (구름)에서 진행한 BERT를 이용해 영어 문장 긍정/부정 분류하는 팀 프로젝트입니다
 - 사용 데이터 : 교육기관에서 제공한 영어 긍/부정 문장 약 45만 개 
     - https://www.kaggle.com/c/goormtextclassificationproject2/data
 - 사전 학습 모델 : 'bert-base-uncased' (허깅페이스에 등록되어 있어 사용하기 편리함)


# 2. Bert_Classification
  - 앞서 만든 영어 문장 긍/부정 분류기에 이어 함수를 간편화하고 다중 분류의 경우에도 문제를 해결할 수 있도록 만들었습니다
    - 함수를 생성해 간편하게 모델을 학습 테스트 해볼 수 있도록 만듦
  - 사용 데이터 : NSMC, 한국어 감정 정보가 포함된 단발성 대화 데이터셋(AI Hub)
    - !git clone https://github.com/e9t/nsmc.git # NSMC 
    - https://aihub.or.kr/opendata/keti-data/recognition-laguage/KETI-02-009 (AI Hub 데이터 셋)
 
  - 사전 학습 모델 : 'klue/bert-base' (허깅페이스에 등록되어 있어 사용하기 편리함)
    - kcbert나 kobert에 비해서 더 다양한 분야의 데이터를 사용했기 때문에 성능향상에 더 적합하다고 판단

  - 해당 모델을 사용하기 위해 전처리 함수를 만들어 놓았으나 데이터에 어느 정도의 전처리가 필요
    - 전처리 함수 들어가면 중복 데이터, 결측치, id컬럼을 제거함
    - text 데이터의 컬럼은 sentences로 통일함
    - label의 데이터 타입이 str인 경우 str_label 컬럼을 만들어 줌
  
