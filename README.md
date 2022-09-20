# FastAPI를 통한 Replicate 서버 만들기

## 1. 가상환경설정 및 설치

### 1) FastAPI 설치

> In Bash

1. `python -m venv venv`

2. `source venv/Scripts/activate`

3. `pip install "fastapi[all]"`
   
   - fastapi 자체와 서버 역할을 하는 uvicorn을 동시 설치
   
   - 따로 설치하는 것도 가능하다

### 2) Replicate 설치

> In Bash

```bash
pip install replicate
```

### 3) 서버 실행

> In Bash

```bash
uvicorn main:app --reload
```

### 4) 환경 변수 설정

> Docker Container 내부에 환경 변수가 설정되어 있다면 할 필요 없다.

1. Bash에 환경변수 집어넣기

```bash
export REPLICATE_API_TOKEN={exportkey}
```

2. .env파일 생성하기
   
   - .env 파일 생성
     
     - REPLICATE_API_TOKEN='{api-key}'
   
   - dotenv 패키지 설치
     
     - `pip install dotenv`
   
   - import module
     
     - `from dotenv import dotenv_values`
   
   - import os
     
     - `envDict = dotenv_values('.env')`
       
       `os.environ["REPLICATE_API_TOKEN"] = envDict['REPLICATE_API_TOKEN']`
