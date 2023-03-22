

# 주요 고려사항
1. 요구사항 준수
2. 프로그램 실행 시 Producer는 Single Thread, Consumer는 Multi Thread(5개) 생성
3. Partition 수에 따른 Queue 수 생성
4. Queue에 데이터 입력 또는 추출 시 Queue의 Min 또는 Max 데이터를 가진 Queue 선택
5. 중복 단어 검증 시 dataMart를 활용하여 검증

<img width="880" alt="image" src="https://user-images.githubusercontent.com/36123687/226855783-7153ccfe-c13b-42b3-b60c-f3ab18ee9f04.png">





# 클래스 설명
1. Main Class
  - Main 클래스
  
2. FileUtils Class
  - File에 대한 입,출력 관리 클래스
 
3. Message Class
  - Queue를 통해 word 전달을 위한 Message 객체(word = 단어, partitionSeq = 파티션 순서)
 
4. MessageQueue Class
  - Queue에 Message를 넣고, 빼는 클래스
  - 파티션 수에 따라 병렬 처리 기능
  - 중복된 단어(Mart) 있을 시 이전에 넣은 파티션 시퀀스에 해당 Message 삽입 

5. Producer Class
  - Queue에 데이터 삽입

6. Consumer Class
  - Queue에서 데이터 추출
 
# 실행
$ java -jar textSplitment.jar FileName Directory Partition
