
## LLM - 거대 언어 모델

1. 대량의 텍스트 데이터
	- Weight(가중치)가 큼 
2. transformer
3. 학습 모델(자연어 이해, 생성)

### LLM - 거대 언어 모델 활용방안

|        | OpenAPI  | 전이 학습                      | 파인 튜닝                 | RAG + AI Agent |
| :----- | :------- | -------------------------- | :-------------------- | -------------- |
| 모델의 위치 | 클라우드     | 로컬                         | 로컬                    | 로컬             |
| 특징     | 그냥 사용 가능 | 학습된 weight값은 그대로 사용        | 학습된 weight을 일부 조정 가능  | 환각문제 줄어듬       |
|        |          | NN 분류를 따로 학습 추가            | 나만의 데이터에 대한 특성 정보를 반영 | 개인화            |
|        |          | 학습된 weight이 나만의 데이터에 특화 안됨 | 개인화 = 특화된 도메인         |                |
|        |          |                            | 대량의 추가 데이터 요구(보안 문제)  | 보안문제 줄어듬       |
|        |          |                            | 학습시간 필요               |                |

검색은 키워드 중심
증강은 문맥(벡터라이징 정보) 중심

추론 : 내가 질의를 할 때 웹에서 검색할 지, 센서에서 가져올 지 등 질의의 내용에 맞춰 정보의 출처를 선택하게 해야한다 

추론을 하는 것 : AI Agent

## Langchain 이란?

랭체인(LangChain) v0.1.0 버전은 2024년 1월에 출시

LLM 애플리케이션을 구축하기 위한 기본 프레임워크로 빠르게 성장

Langchain 프레임워크 구성
1. **랭체인 라이브러리(LangChain Libraries):** 
	- 파이썬과 자바스크립트 라이브러리를 포함
	- 다양한 컴포넌트의 인터페이스와 통합
	- 컴포넌트들을 체인과 에이전트로 결합할 수 있는 기본 런타임,
	- 체인과 에이전트의 사용 가능한 구현이 가능
    
2. **랭체인 템플릿(LangChain Templates):** 
	- 다양한 작업을 위한 쉽게 배포할 수 있는 참조 아키텍처 모음
	- 템플릿은 개발자들이 특정 작업에 맞춰 빠르게 애플리케이션을 구축 가능하게 도움을 줌
    
3. **랭서브(LangServe):** 
	- 랭체인 체인을 REST API로 배포할 수 있게 하는 라이브러리
	- 개발자들은 자신의 애플리케이션을 외부 시스템과 쉽게 통합 가능
    
4. **랭스미스(LangSmith):** 
	- 개발자 플랫폼
	- LLM 프레임워크에서 구축된 체인을 디버깅, 테스트, 평가, 모니터링 가능
	- 랭체인과의 원활한 통합을 지원

### 필수 라이브러리 설치

#### Langchain 설치
- pip 사용:

```python
pip install langchain
```

- conda 사용:

```python
conda install langchain -c conda-forge
```

#### OpenAI 의존성 패키지(langchain-openai)

OpenAI 모델을 사용할 때 필요한 의존성 라이브러리를 설치하는 방법
- langchain-openai 라이브러리: GPT-3.5, GPT-4 등 LLM 모델과 기타 보조 도구를 포함

```python
pip install langchain-openai
```

- tiktoken 라이브러리: OpenAI 모델이 사용하는 토크나이저(Tokenizer)

```python
pip install tiktoken
```

#### OpenAI 인증키 등록

다음 코드는 환경 변수 OPENAI_API_KEY를 설정하는 방법

이 환경 변수는 OpenAI API를 사용할 때 인증을 위해 필요한 API 키를 저장하는 데 사용

앞의 코드에서 'OPENAI_API_KEY' 부분을 실제 OpenAI API 키 값으로 교체

```python
import os
os.environ['OPENAI_API_KEY'] = 'OPENAI_API_KEY'
```

환경변수로 등록해서 사용하는 것이 인증키를 함수의 매개변수로 직접 입력하는 것보다 안전한 방법입

API 키는 민감한 정보이므로 안전하게 관리하고 노출되지 않도록 주의 필요

### 랭체인의 프레임워크/처리 과정

![[Langchain 강의 요약-20250327.png]]![[Langchain 강의 요약-20250327-1.png]]

### 랭체인의 구성요소

| 구분                                                                                                                                     | 구성요소                                                                                                                                                                                                                                                                                    | 역할                                                             |
| -------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| 핵심  <br>모듈                                                                                                                             | Agent                                                                                                                                                                                                                                                                                   | – 수행할 작업을 동적 체인으로 구성  <br>– 프롬프트 행동 계획 추출 기능 단순화               |
| Memory                                                                                                                                 | – 모델에 장단기 메모리 추가 지원  <br>– 최근 대화 기억, 과거 메시지 분석 지원                                                                                                                                                                                                                                       |                                                                |
| Callback                                                                                                                               | – 특정 이벤트 시 사용자 지정 콜백 핸들러 작성  <br>– 로깅, 모니터링, 스트리밍 등                                                                                                                                                                                                                                     |                                                                |
| Data Connection                                                                                                                        | – PDF 등 외부 문서 로드, [워드 임베딩](https://blog.skby.net/%ec%9b%8c%eb%93%9c-%ec%9e%84%eb%b2%a0%eb%94%a9word-embedding/) 변환, [벡터DB](https://blog.skby.net/%eb%b2%a1%ed%84%b0-%eb%8d%b0%ec%9d%b4%ed%84%b0%eb%b2%a0%ec%9d%b4%ec%8a%a4-vector-database/) 저장, 쿼리 기반 검색 등                             |                                                                |
| Chain                                                                                                                                  | – 구성요소와 [LLM](https://blog.skby.net/%ea%b1%b0%eb%8c%80-%ec%96%b8%ec%96%b4-%eb%aa%a8%eb%8d%b8-llm-large-language-model/) 활용하여 파이프라인 구축  <br>– 쿼리부터 모델 출력까지 자동화 구성                                                                                                                        |                                                                |
| Model I/O                                                                                                                              | – [LLM](https://blog.skby.net/%ea%b1%b0%eb%8c%80-%ec%96%b8%ec%96%b4-%eb%aa%a8%eb%8d%b8-llm-large-language-model/)과 상호작용 수행  <br>– 프롬프트 생성, 모델 API 호출, 결과 해석                                                                                                                             |                                                                |
| 외부  <br>도구                                                                                                                             | Data Source                                                                                                                                                                                                                                                                             | – 다양한 외부 소스에서 데이터 액세스 및 검색  <br>– PDF, 웹페이지, CSV, 관계형 데이터베이스 등 |
| [[워드 임베딩(Word Embedding)]]                                                                                                             | – 외부 소스에서 검색된 데이터를 벡터로 변환  <br>– 선택한 [LLM](https://blog.skby.net/%ea%b1%b0%eb%8c%80-%ec%96%b8%ec%96%b4-%eb%aa%a8%eb%8d%b8-llm-large-language-model/) 기반 최적 임베딩 모델 선택                                                                                                                    |                                                                |
| [Vector DB](https://blog.skby.net/%eb%b2%a1%ed%84%b0-%eb%8d%b0%ec%9d%b4%ed%84%b0%eb%b2%a0%ec%9d%b4%ec%8a%a4-vector-database/)          | – 생성된 임베딩의 유사성 검색 저장소  <br>– 다양한 소스에서 벡터 기반 저장, 검색                                                                                                                                                                                                                                      |                                                                |
| [LLM (Large Language Model)](https://blog.skby.net/%ea%b1%b0%eb%8c%80-%ec%96%b8%ec%96%b4-%eb%aa%a8%eb%8d%b8-llm-large-language-model/) | – OpenAI, Cohere, AI21 등 주류 [LLM](https://blog.skby.net/%ea%b1%b0%eb%8c%80-%ec%96%b8%ec%96%b4-%eb%aa%a8%eb%8d%b8-llm-large-language-model/)  <br>– Hugging Face 지원 오픈소스 [LLM](https://blog.skby.net/%ea%b1%b0%eb%8c%80-%ec%96%b8%ec%96%b4-%eb%aa%a8%eb%8d%b8-llm-large-language-model/) |                                                                |

### LLM 체인(LLM Chain)

#### 기본 LLM chain
```python
from langchain_openai import ChatOpenAI

# model
llm = ChatOpenAI(model="gpt-4o-mini")

# chain 실행

llm.invoke("지구의 자전 주기는?")
```

```python
from langchain_openai import ChatOpenAI
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.output_parsers import StrOutputParser

# prompt + model + output parser
prompt = ChatPromptTemplate.from_template("You are an expert in astronomy. Answer the question. <Question>: {input}")
llm = ChatOpenAI(model="gpt-4o-mini")
output_parser = StrOutputParser()

# LCEL chaining
chain = prompt | llm | output_parser

# chain 호출
chain.invoke({"input": "지구의 자전 주기는?"})
```

