# ktdsminiproject
# AWS CodePipeline & Spring Boot

## 1. 파이프라인 설정
![image](https://github.com/hj0210/ktdsminiproject/assets/68845747/6bd97db1-158c-4847-9755-1a2c4db91d99)

- 프리티어 레벨로 사용하므로 V2 선택
- 서비스역할은 프로젝트이름에 맞는 역할 새로생성
- S3 아티팩트설정은 default

## 2. 소스 스테이지 추가

![image](https://github.com/hj0210/ktdsminiproject/assets/68845747/d854aab7-2259-417e-8929-b8dbacf32257)

- 나의 github id를 넣으면 새 연결이 생성이 된다.

![image](https://github.com/hj0210/ktdsminiproject/assets/68845747/c28a2b17-789d-47b0-ab9b-101268f29a59)

- 연결준비완료 확인
- 나의 HEAD를 복제 > 즉 main 브랜치에 푸쉬되면 감지한다


## 3. 빌드 스테이지 추가

빌드프로젝트는 미리 생성 후 추가하는 방법도 있다.

![image](https://github.com/hj0210/ktdsminiproject/assets/68845747/284eae38-4d07-430f-84e9-8941569bcf53)

- 빌드해주는 툴. 보통 레거시에서는 젠킨스를 많이 사용하나 only AWS를 위해 코드빌드 사용.

![image](https://github.com/hj0210/ktdsminiproject/assets/68845747/2a967d80-e61d-4461-9435-92788447a778)

- 서비스 역할은 자동생성역할 사용
- 빌드명령 삽입이 아닌 빌드스펙 파일 사용. (buildspec.yaml)

![image](https://github.com/hj0210/ktdsminiproject/assets/68845747/e8ec9642-f716-4d38-a8b8-0ada6878a693)

- log또한 cloudwatch로 기록 설정 후 생성
  
![image](https://github.com/hj0210/ktdsminiproject/assets/68845747/a53fd5a9-29b8-4c82-8a9b-36f77f7e3b0a)

- 빌드스테이지 추가 후 완료된 모습
- 추후 소스 내에 환경변수를 따로 관리 할 것이 생긴다면 추가하면 된다.

## 4. 배포 스테이지 추가

추후 ECS로 컨테이너 환경에 배포하지만 초기 환경은 EC2 deploy로 배포


