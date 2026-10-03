# 🦙 11장. 로컬 LLM과 DeepSeek-R1

Ollama에서 실행하는 로컬 언어 모델을 LangChain 애플리케이션에 연결하고, DeepSeek-R1 기반 대화와 RAG 챗봇을 실습합니다. 9장에서 만든 Chroma 벡터 저장소의 문서를 검색해 답변에 활용하는 흐름도 다룹니다.

## 🧪 실습 내용

- Ollama에서 `DeepSeek-R1:14B` 모델 다운로드 및 실행
- LangChain `ChatOllama`를 이용한 로컬 모델 호출
- Chroma에서 관련 문서를 검색해 답변에 사용하는 RAG 구현
- Streamlit 에서 검색 문서와 생성 답변 표시
- 로컬 LLM의 장점과 제약 살펴보기

## 🗂️ 파일 구성

| 파일 | 설명 |
| --- | --- |
| `chap11_1_deepseek_simple_chatbot.ipynb` | Ollama와 DeepSeek-R1 설치 및 기본 대화 실습 |
| `rag.py` | DeepSeek-R1과 문서 검색을 연결한 Streamlit RAG 앱 |
| `retriever.py` | 임베딩, Chroma 검색기, 질의 보강 및 문서 답변 체인 구성 |
| `pyproject.toml` | 챕터 의존성 및 Python 버전 요구사항 |

## ⚙️ 실행 준비

Python 3.11 이상과 [Ollama](https://ollama.com/)가 필요합니다. 모델을 내려받고 실행합니다.

```bash
ollama run deepseek-r1:14b
```

RAG Streamlit 앱을 실행하려면:

```bash
uv run streamlit run rag.py
```

