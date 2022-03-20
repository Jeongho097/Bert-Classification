# Bert-Classification
1. AI기술 자연어 처리 과정 2기 (구름)
   영어 문장 감성 분석
 2. 개인 프로젝트 (추가 예정)
    감성 분석(Sentiment Classification), 문서 쌍 분류(NLI)를 하기 위한 Bert Classification Model을 만듬

 - colab을 사용

# 1. Text Classification
 - AI기술 자연어 처리 과정 2기 (구름)에서 진행한 BERT를 이용해 영어 문장 긍정/부정 분류하는 Text Classfication Task입니다
 - 사용 데이터 : 교육기관에서 제공한 영어 긍/부정 문장 약 45만 개 


# 2. Bert_Sentences_Classification
  - 1번에 이어 BERT를 이용해 한국어 긍/부정 분류, 다중 분류, 문서 쌍 분류(NLI)하는 Text Classfication Task입니다
    - 사용 데이터 : NSMC, 한국어 감정 정보가 포함된 단발성 대화 데이터셋(AI Hub), 카카오 브레인 데이터셋

  - 해당 모델을 사용하기 위해 전처리 함수를 만들어 놓았으나 데이터에 어느 정도의 전처리가 필요
    - 변수명의 통일이 필요함 document_1, document_2(문서 쌍 분류의 경우), label
  - 전처리 함수 들어가면 중복 데이터, 결측치, id컬럼을 제거함
  - label의 데이터 타입이 str인 경우 str_label 컬럼을 만들어 줌
  
