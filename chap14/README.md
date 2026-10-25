# 🧠 14장. LangGraph 멀티에이전트와 작업 분배

이 장에서는 단일 LLM이 모든 일을 처리하는 방식이 아니라, 여러 에이전트가 역할을 나누어 협업하는 멀티에이전트 구조를 실습합니다. 특히 LangGraph를 활용해 Supervisor, Content Strategist, Communicator, Vector Search Agent, Web Search Agent가 서로 협력하도록 구성하고, 책 목차 작성 흐름을 자동화하는 과정을 학습합니다.

## 🧪 실습 내용

- 멀티에이전트 시스템의 기본 구조와 역할 분리
- `supervisor` 에이전트가 작업을 분배하고 라우팅 제어
- `content_strategist`가 목차를 작성하고 파일로 저장
- `vector_search_agent`가 Chroma 벡터 DB에서 관련 문서를 검색
- `web_search_agent`가 Tavily로 추가 정보를 확보하고 DB에 적재
- 일상적인 커뮤니케이션과 작업 진행을 담당하는 `communicator`
- Pydantic 기반 구조화된 출력으로 안정적인 에이전트 제어

## 🗂️ 파일 구성

```text
chap14/
├── book_writer.py           # 멀티에이전트 워크플로우 메인 로직
├── book_writer.png          # 그래프 시각화 이미지
├── models.py                # Pydantic Task 모델 정의
├── tools.py                 # 검색, 문서 로딩, Chroma 적재, RAG 검색 도구
├── utils.py                 # 상태 및 목차 저장 유틸리티
├── data/                    # outline.md, state.json, resources_*.json, chroma_store
├── pyproject.toml           # 의존성 관리
├── README.md                # 장별 설명
├── uv.lock                  # 패키지 잠금 파일
├── .python-version          # Python 버전 정보
└── chap14_summary.md        # 14장 핵심 정리 문서
```

## ⚙️ 실행 준비

챕터 의존성을 설치합니다.

```bash
cd chap14
uv sync
```

실행을 시작하려면:

```bash
uv run python book_writer.py
```

이후 사용자 질문 또는 작업 요청을 입력하면, 시스템이 Supervisor를 통해 역할별 에이전트들이 기능을 수행합니다.

## 🔍 핵심 개념

### 1. Supervisor 기반 작업 분배

`supervisor`는 입력된 사용자 요청을 분석하고, 어떤 에이전트가 다음 작업을 맡아야 하는지 결정합니다. 이때 작업을 문자열로 단순히 넘기기보다 Pydantic 모델을 사용해 구조화된 결과를 받아 안정적으로 라우팅합니다.

### 2. 역할별 전문 에이전트

- `content_strategist`: 목차 작성과 계획 수립
- `communicator`: 사용자와의 메시지 전달
- `vector_search_agent`: 벡터 DB를 활용한 문서 검색
- `web_search_agent`: 외부 검색으로 지식 보충

각 에이전트는 고유 목적을 갖고 협력하면서 복잡한 과제를 분해해 처리합니다.

### 3. RAG와 웹 검색의 결합

벡터 DB만으로는 부족한 정보가 있을 수 있으므로, 웹 검색 결과를 가져와 다시 Chroma에 적재한 뒤 RAG를 수행합니다. 이 구조는 최신 정보 반영과 지식 보완에 유리합니다.

### 4. 상태 관리와 작업 이력

`state.json`, `task_history`, `references`, `messages` 등을 관리하여 시스템이 이전 작업을 기억하고 다음 단계로 연결할 수 있습니다. 이는 멀티에이전트 시스템에서 매우 중요한 부분입니다.

## 💡 학습 포인트

- 멀티에이전트는 단순히 여러 모델을 붙이는 것이 아니라, 각 역할과 상태 흐름이 분리된 구조다.
- 에이전트 간 라우팅을 안정적으로 만들기 위해서는 구조화된 출력이 중요하다.
- 문서 기반 검색과 웹 검색을 함께 활용하면 지식 부족을 보완할 수 있다.
- LangGraph는 상태와 작업 흐름을 시각적으로 관리하는 데 적합하다.

## 정리

14장은 LangGraph를 기반으로 한 멀티에이전트 시스템을 구성하는 실습으로, AI 에이전트가 단순한 챗봇을 넘어서 실제 작업을 분담하고 수행하는 흐름을 이해하는 장입니다. 이후 더 복잡한 멀티에이전트 협업과 자율적 업무 수행 구조의 기초가 됩니다.
