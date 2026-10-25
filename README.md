# 📚 Do it! LLM을 활용한 AI 에이전트 개발 입문

책 『Do it! LLM을 활용한 AI 에이전트 개발 입문』의 예제를 직접 실습하며, LLM 기반 애플리케이션과 AI 에이전트 개발 개념을 학습하는 프로젝트입니다.



## 🗂️ 프로젝트 구성

```text
learn_doit_llm_agent/
├── chap02/                 # LLM / OpenAI API 기초
├── chap03/                 # 프롬프트 엔지니어링 및 대화형 애플리케이션
├── chap04/                 # PDF 문서 처리 및 요약
├── chap05/                 # 음성 인식 / 화자 분리 / 텍스트 정제
├── chap06/                 # 이미지 이해 / 퀴즈 / TTS
├── chap07/                 # Function Calling / 외부 도구 연동
├── chap08/                 # LangChain / LCEL / @tool 사용
├── chap09/                 # RAG 기반 문서 질의응답
├── chap10/                 # 웹 검색 / YouTube 요약 / 검색형 앱
├── chap11/                 # Ollama 로컬 LLM / DeepSeek-R1
├── chap12/                 # LangGraph 상태 관리 / 메모리 / 도구 호출
├── chap13/                 # LangGraph 기반 조건부 라우팅 RAG
├── chap14/                 # LangGraph 멀티에이전트 / 책 목차 작성
├── etc/                    # 추가 자료 및 실험 기록
├── README.md               # 프로젝트 소개
├── .gitignore
└── .python-version
```

> 현재 프로젝트는 각 챕터별 실습이 디렉터리 단위로 구성되어 있으며, 각 디렉터리 안에 해당 챕터의 노트북, 스크립트, 설정 파일이 포함되어 있습니다.



## ⚙️ 실행 환경

이 프로젝트는 Python 3.12 기반 환경을 기준으로 구성되어 있으며, 각 챕터별로 독립적인 `pyproject.toml`과 가상환경을 사용합니다.


## 🧪 주요 실습 내용

### 2장. GPT API 기초

- OpenAI API를 활용한 기본 호출
- 간단한 프롬프트 응답 실습
- 기본 대화형 예제 구성

### 3장. 프롬프트 엔지니어링

- Zero-shot, One-shot, Few-shot
- 멀티턴 대화 처리
- `streamlit` 기반 챗봇 구현

### 4장. 문서 처리와 요약

- PDF 문서를 텍스트로 변환
- 문서 내용 추출 및 요약
- 검색 가능한 텍스트 구조 만들기

### 5장. 음성과 이미지 처리

- Whisper 기반 음성 인식
- 화자 분리
- 이미지 설명 및 이미지 퀴즈
- TTS 실습

### 6장. Function Calling과 에이전트 구성

- 외부 함수 호출
- API 기반 도구 사용
- 검색 결과와 도구 실행 흐름 연결

### 7장. LangChain 활용

- 프롬프트 템플릿 구성
- 도구 정의 및 체인 구성
- LCEL 기반 애플리케이션 설계

### 8장. 도구 기반 AI 애플리케이션

- `@tool` 데코레이터를 활용한 함수 등록
- LangChain 도구 호출 흐름 이해
- 재사용 가능한 에이전트 함수 설계

### 9장. RAG 구현

- 문서 로딩
- 임베딩 생성
- 벡터 데이터베이스 저장
- 검색 후 답변 생성

### 10장. 웹 검색과 YouTube 요약

- DuckDuckGo 기반 웹 검색 실습
- Tavily API를 활용한 검색 결과 수집
- 검색 결과를 LLM에 전달해 답변 생성
- YouTube 영상 링크를 요약하는 실습
- `streamlit` 기반 검색 및 요약 앱 구현

### 11장. 로컬 LLM과 DeepSeek-R1

- Ollama에서 `DeepSeek-R1:14B` 모델 실행
- LangChain의 `ChatOllama`로 로컬 모델과 대화
- Streamlit 앱에 Chroma 벡터 저장소의 검색 결과를 활용한 RAG 챗봇 구현

### 12장. LangGraph와 상태 관리

- LangGraph 기본 그래프 구조와 노드/엣지 이해
- 상태 기반 대화 흐름 구성
- 대화 메모리와 세션 상태 관리
- 외부 도구를 그래프에 연결하는 실습
- 툴 호출을 통한 에이전트형 워크플로우 구현

### 13장. LangGraph 기반 RAG

- 질문을 벡터 저장소 검색 또는 일상 대화로 분기
- 검색 문서의 질문 관련성을 평가하고 관련 문서만 필터링
- 질문과 검색 문맥을 이용한 답변 생성
- 라우터, 검색, 문서 평가, 답변 생성 노드를 LangGraph로 연결
- 조건부 엣지를 사용한 RAG 워크플로우 구성

### 14장. LangGraph 멀티에이전트

- Supervisor 에이전트가 작업을 분배하고 라우팅을 제어
- content strategist, communicator, vector search, web search 역할 분리
- 벡터 DB와 웹 검색을 함께 활용하는 자료 수집 흐름
- Pydantic 기반 구조화된 출력으로 안정적인 에이전트 제어
- 새로운 정보를 수집하고 목차를 작성하는 멀티에이전트 워크플로 구현


## 📖 참고 자료

- 책: 『Do it! LLM을 활용한 AI 에이전트 개발 입문』
- 원본 예제 저장소: https://github.com/saintdragon2/gpt_agent_2025_easyspub
