# 환경 빅데이터 분석 플랫폼(2018년)  
## 수집-저장 1. Open Data Map 구축  
### KEI 발간자료 중 보고서에 사용된 참고 온라인 문헌 추출 및 추출과정 자동화  
  
1) 시범운영 서버에 전자도서관 자료 백업(2018.03.01 기준)  
2) 패턴 매칭 방식으로 URL 추출 및 검색, 메타 정보 수집 및 수집과정 자동화  
3) 초기 모델 출시(2018.04) 후 지속적으로 업데이트  
4) 원 보고서 분류기준으로 참고 온라인 문헌 지도 작성 및 작성과정 자동화  
→ 홈페이지 DB와 전자도서관 DB 검토
5) 보고서 제목의 키워드 분석결과를 반영해 분류기준 확장 등  
  
### 데이터 수요조사를 바탕으로 환경연구 데이터 DB 구축  
1) 2018년 세부과제 실시 전 연구활용 데이터 DB 구축  
2) 데이터 수요조사를 통한 연구 활용 데이터 우선순위 도출  
→ 내부 70명 이상, 외부전문가 DB 활용  
3) 2017년 수요가 높은 데이터 우선 DB 구축 : 에어코리아 등  
→ 부 및 원내 공개를 통해 연구 활용 데이터 이슈를 지속적으로 반영, 개선하고자 함  
  
## 수집-저장 2. 환경 빅데이터 수집방법 보완  
### IoT Data DB 구축  
1) 기존 방법(공공데이터포털 OpenAPI, 에어코리아 등) 외 스마트 센서 기반 데이터 수집방법 보완  
→ PM2.5 기준 세종시 2개 지역이상 데이터 수집 및 공개  
→ 1개소 당 센서(Plantower PMS 7003) 3기 설치 및 DB 구축(6월) 및 과정 자동화 추진  
→ 2019년 미시 미세먼지 예측 모델 기초연구 발굴 예정  
2) 2018년 하반기부터 3개년 이상 데이터 축적 및 단계적 공개 예정  
  
## 분석-처리 1. 실증적인 분석플랫폼 발전방안 마련  
### 분석플랫폼 구성방안 업데이트  
1) 정보기술의 급격한 발전, 컴퓨팅 여건변화 반영   
2) 연구자 눈높이에 맞는 분석플랫폼 활용(안) 반영  
3) 연구성과 공유 로드맵 작성  
→ K 라이브러리, K 엔진, 대시보드, 데이터 수집기 및 OpenAPI 개발 등  
  
### 시범운영 서버 개선  
1) 환경연구 기초 데이터 배포 강화 : 웹 다운로드, DB 접근방식  
→ 데이터 다운로드 UI 및 라이브러리 개발(2019년 이후)  
2) 우분투(Ubuntu) 및 아나콘다(Anaconda) 등 소프트웨어 업데이트  
3) 서버 메모리 증설(32GB * 18개까지 페어로 추가 가능)  
4) 코드 및 소프트웨어 이력은 모두 github에 공개(비식별화 필수)  
5) 개선결과 분석플랫폼 구성방안에 반영  
  
## 분석-처리 2. 연구성과 확산 및 재구축  
### 기존 연구성과 재생 및 재구축  
1) 텍스트 마이닝을 이용한 KEI 연구동향 분석(김도연)  
→ R기반 연구재생 진행 중(2018.03)  
→ Python기반 연구재구축 진행 예정(2018.04)  
2) 딥러닝을 활용한 환경리스크 예측(이동현)  
3) 미세먼지 발생요인 패턴 분석(김진형)  
4) 기후변화에 따른 감염성 질병 예측(강선아)  
  
### 연구성과 재생절차(안) 마련  
1) 코드 재생  
2) 코드 통합(자동화)  
3) 코드 활용(일반화) : 2018년  
4) 라이브러리화 : 2019~2020년  
5) 코드 변환(트랜스코딩) : 2020년 이후  
6) 코드 튜닝 : 2020년 이후  
  
## 시각화-예측 1. 환경 빅데이터 분석 환경(UI) 제공  
### 사용목적별 UI 차별화  
1) 연구재생용 : 기존 연구재생을 위한 UI 및 사용자 가이드 제공  
2) 연구분석용 : Spark 등 연구분석을 위한 UI 및 코드 가이드 제공  
3) 환경구축용 : 전용 UI 구축을 위한 터미널 제공, 코드 및 시스템 활용이 가능한 연구자에게 제한적으로 제공  
→ pyenv, virtualenv 등 개인환경 설정 가능, 개별 설치가이드 제공  
  
### 단계별 개방  
1) 본 과제 참여자 중심으로 개방 및 개선조치 후(2018년)  
2) 원내 개방 및 개선조치 실시(2019년~2020년)  
3) 원외 개방은 중장기적 검토 후 추진(2021년 이후)  
