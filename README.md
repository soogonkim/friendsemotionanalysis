# friendsemotionanalysis


<프로젝트 목적>
 - 2020 년 가을학기 임희석 교수님 수업(디지털 금융공학 위한 자연언어처리기술)의
   시트콤 Friends(영문대사) 감정 분석 모델 구축

- Dain Lee가 공개한 Source Code 참조
  - https://github.com/ailohc/friends-classification

- 공개 된 코드분석 및 수정을 통해 주석을 달아 감정분석기 모델 이해도 증진 및 <br>
  감정분석 평가율 제고를 위해 노력했습니다.
  
 <이용 모델>
 - transformer - RoBERTa Model
 
 <경로 및 max_len 설정>
 - Test Data 로서 en_data 파일 사용
 - 결과 File 저장명 지정
 - utterance max 값 80으로 설정

<데이터 불러오기>
학습 Data Type Dictionary형으로 정의

-Data 확대를 위해 train+dev+test 전체 활용

Bert 이용 위한 전처리
Bert 모델 활용 위해, 클래스 구분자 '[CLS]'및 문장 구분자 '[SEP]'사용

감정 레이블 Data를 category형으로 지정

Mapping : label을 str -> index(long)으로 변환

<데이터 전처리>
RoBERTa Model 활용 Token화 진행
Large 모델 활용
대소문자 구분
*Large 모델이 Base 모델보다 시간은 더 걸리지만, 정확도 향상에 도움
대소문자 미구분이(소문자화 = true) 구분 시(flase) 보다 정확도 향상
[RoBERTa] 에 대한 설명은 하기 링크 참조
https://brunch.co.kr/@choseunghyek/7
https://blog.naver.com/beneyh3000/222074120459

<모델링>
RoBERTa Model 활용 진행
optimizer adamw 설정
[Tip3]
BERT-Large 정확도 향상 한계 존재
RoBERTa 모델 통해 정확도 향상

<Training 및 Validation>
Epoch 반복

제출용 Data 예측
