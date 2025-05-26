# Searching-Vedio-List_with-Youtube-API
유튜브 api 활용하여  동영상 컨텐트 목록 검색

## 기술스택
- 프론트 : React, Babel, HTML
- 백: FastAPI, Python, Google API Cleient Library, Uvicorn
- 개발 및 배포 도구 : Jinja2, pyngrok, CORS Middleware

## 애플리케이션 구조
```text
Searching_Engine
└─www
    ├─static
    │  ├─css
    │  └─js
    └─templates
```

## 사전 준비사항
1. YouTube Data API 활성화
  1) 좌측 메뉴에서 "API 및 서비스" → "라이브러리" 클릭
  2) "YouTube Data API v3" 검색
  3) 검색 결과에서 "YouTube Data API v3" 클릭
  4) "사용" 버튼 클릭

2. API 키 생성
  1) 좌측 메뉴에서 "API 및 서비스" → "사용자 인증 정보" 클릭
  2) 상단의 "+ 사용자 인증 정보 만들기" 클릭
  3) "API 키" 선택
  4) 생성된 API 키 복사 및 저장
  5) (선택) "키 제한" 클릭하여 보안 설정
   - 애플리케이션 제한사항: HTTP 리퍼러 설정
   - API 제한사항: YouTube Data API v3 선택
 
3. 아래 명령어 실행
```text
pip install fastapi uvicorn pyngrok python-multipart google-api-python-client
npm install -g create-react-app
```

## 시작하기
# ngrok 인증토큰 생성
1. ngrok 웹사이트에 가입합니다 (아직 계정이 없는 경우).
2. 가입 후 대시보드에서 인증 토큰을 확인합니다.
3. 아래 코드를 새로운 셀에 붙여넣고, YOUR_AUTH_TOKEN 부분을 본인의 토큰으로 바꿔 실행합니다:

# 로컬 실행
1. 아래 명령어 실행
```text
ngrok authtoken YOUR_NGROK_AUTH_TOKEN
```
 > `{{YOUR_AUTH_TOKEN}}`은 앞서 생성한 ngrok토큰 값

2. YouTube API키 설정
```
# app.py 파일에서 YOUR_YOUTUBE_API_KEY_HERE를 실제 API 키로 교체
import fileinput

api_key = "여기에_실제_API_키_입력"

with open('app.py', 'r') as file:
    content = file.read()

content = content.replace('YOUR_YOUTUBE_API_KEY_HERE', api_key)

with open('app.py', 'w') as file:
    file.write(content)
```

3. 아래 명령어 실행
```text
python run_server.py
```
