# 10장. 웹 검색과 YouTube 요약

이 장에서는 LLM이 단순히 내부 지식만 사용하는 것이 아니라, 외부 웹 정보를 검색하고 활용하는 방식에 대해 학습합니다. 특히 웹 검색, 검색 엔진 API, YouTube 영상 요약을 연결하는 흐름을 실습하며, AI 에이전트가 실제 정보를 가져와 답변을 구성하는 과정을 익힙니다.

## 실습 내용

- 웹 검색 도구를 활용한 정보 탐색
- DuckDuckGo 기반 검색 실습
- Tavily 검색 결과 활용
- YouTube 링크를 이용한 영상 요약
- Streamlit 기반 검색/요약 앱 구성

## 파일 구성

```text
chap10/
├── chap10_1_duckduckgo_search.ipynb   # DuckDuckGo 검색 실습
├── chap10_2_tavily_search.ipynb        # Tavily 검색 API 실습
├── chap10_3_youtube_summary.ipynb      # YouTube 요약 실습
├── chap10_4_streamlit_web_search.py    # 웹 검색 Streamlit 앱
├── chap10_5_streamlit_youtube_search.py # YouTube 검색/요약 Streamlit 앱
├── pyproject.toml                      # 프로젝트 의존성
├── README.md                           # 장별 설명
├── uv.lock                             # 패키지 락 파일
└── .python-version                     # Python 버전 정보
```

## 핵심 개념

### 1. 웹 검색 기반 RAG

검색 엔진을 이용해 최신 정보나 외부 문서를 가져온 뒤, LLM에 전달하는 방식입니다. 단순한 지식 기반 응답이 아니라, 실시간 정보와 최신 문맥을 반영한 답변을 만들 수 있습니다.

### 2. 도구 호출과 외부 정보 활용

AI가 생각만 하는 것이 아니라, 실제 검색 도구를 호출해 필요한 정보를 수집하고, 그 결과를 바탕으로 최종 답변을 생성하게 됩니다. 이는 AI 에이전트의 핵심 패턴 중 하나입니다.

### 3. YouTube 영상 요약

영상 URL을 입력받아 내용을 추출하고, 필요한 핵심 내용을 정리해 전달하는 흐름을 실습합니다. 텍스트 기반 검색뿐 아니라 멀티미디어 자료를 활용하는 확장형 애플리케이션 구현에 유용합니다.

## 실행 방법

```bash
cd chap10
uv run streamlit run chap10_4_streamlit_web_search.py
```

```bash
cd chap10
uv run streamlit run chap10_5_streamlit_youtube_search.py
```

## 학습 포인트

- 검색 도구는 단순히 키워드만 찾는 것이 아니라, 질문의 맥락에 맞는 정보를 추출하는 데 쓰인다.
- LLM과 검색 도구를 연결하면 최신 정보 반영이 가능하다.
- 텍스트 응답 외에도 동영상, 문서, 웹 페이지를 활용할 수 있다.
- 최종 사용자 경험을 위해 UI를 붙여 실제 서비스처럼 구성할 수 있다.

