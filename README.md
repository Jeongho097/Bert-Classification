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

   감성 분석(Sentiment Classification), 문서 쌍 분류(NLI)를 하기 위한 Bert Classification Model을 만듬
   
   
   해당 모델에서는 데이터을 넣으면 감성 분석을 해야하는 경우에는 감성 분석을 문서 쌍 분류를 해야하는 경우에는 문서 쌍 분류를 하는 모델임
   해당 모델을 사용하기 위해 전처리 함수를 만들어 놓았으나 데이터에 어느 정도의 전처리가 필요
   데이터의 컬럼들은 id(있던 없던 상관없음), document_1, document_2(문서 쌍 분류의 경우), label(문자열 형식의 label도 괜찮음) 이렇게 4개를 권장함
   또한 데이터 셋은 train_data, test_data 형식으로 권장함 val_data가 있는 경우 train_data와 합쳐주거나 test_data와 합쳐주어도 괜찮음
   전처리 함수에 들어가면 중복 데이터, 결측치, id컬럼을 제거함
   컬럼의 이름을 document_1, document_2(문서 쌍 분류의 경우), str_label로 변경(label data가 문자열인 경우 str_label로 변경, 숫자열인 경우 label로 변경함)
   label 컬럼의 이름이 str_label인 경우 sklearn의 LabelEncoder를 통해 새로운 label 컬럼을 만들어 줌
   최종적으로 데이터 변수 명은 train_data, test_data로 권장함
   위의 전처리 과정을 거쳤다면 모델 학습을 위한 전처리가 필요함
   전처리 과정은 train_data의 전처리 과정과 test_data의 전처리 과정을 따로 분리 해놓음
   test_data 전처리의 겨우 label이 없다는 가정하에 진행함
   validation_data를 생성하기 때문에 test_data는 label이 없다고 가정함
