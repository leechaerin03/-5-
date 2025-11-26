# 🦁 nDRIMS AI Agent: LAM-based Automation Service
> **Large Action Model(LAM)을 활용한 동국대학교 학사행정시스템(nDRIMS) 지능형 자동화 에이전트**

<br>

## 📅 Project Overview
**"복잡한 메뉴 찾기는 그만!!, AI에게 말로 시키세요."**

동국대학교 학사행정시스템(nDRIMS)은 방대한 기능을 담고 있지만, 복잡한 메뉴 구조(Depth)와 직관적이지 않은 UI로 인해 학생들이 원하는 기능을 찾는 데 어려움을 겪어왔습니다.
본 프로젝트는 기존 LLM의 언어 이해 능력을 넘어, **실질적인 행동(Action)을 수행하는 LAM(Large Action Model) 기술**을 도입하여 이 문제를 해결했습니다.

사용자가 자연어로 명령(예: "이번 학기 성적표 보여줘")을 내리면, AI 에이전트가 이를 해석하고 브라우저를 직접 제어하여 해당 페이지로 이동하거나 기능을 실행합니다.

<br>

## 🧠 Model Architecture & Hugging Face
이 서비스는 사용자의 의도를 파악하여 행동 계획을 수립하는 Base Model(Plan)과, 실제 웹 UI 요소와 상호작용하는 Adapter Model(Action)의 구조로 동작합니다.

| Role | Model Name | Link | Description |
| :--- | :--- | :---: | :--- |
| **Base Model**<br>(Planner) | `PlanModel_v1` | [![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-PlanModel-FFD21E)](https://huggingface.co/leeChaerin/PlanModel_v1) | 사용자의 자연어 명령을 분석하여 수행해야 할 작업 순서(Plan)를 생성하는 모델 |
| **Adapter Model**<br>(Action) | `ActionModel_v5` | [![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-ActionModel-FFD21E)](https://huggingface.co/leeChaerin/ActionModel_v5) | DOM Tree 및 UI 요소를 인식하고 클릭, 입력 등의 구체적인 제어 신호를 생성하는 모델 |

<br>

## 💡 Key Features
* **Natural Language Command:** "휴학 신청 어디서 해?", "강의 시간표 확인해줘" 등 구어체 명령 완벽 지원
* **Zero-Click Navigation:** 사용자가 메뉴를 클릭할 필요 없이, AI가 목적지 페이지까지 자동으로 이동
* **LAM Technology:** 단순 텍스트 생성이 아닌, 웹 브라우저의 DOM을 이해하고 이벤트를 발생시키는 행동형 AI 구현
* **Robust UI Control:** 동적 렌더링(SPA) 환경에서도 정확한 요소를 찾아내는 고도화된 식별 알고리즘 적용

<br>

## 🛠 Tech Stack

<div align="left">
  <h3>AI & Model</h3>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=PyTorch&logoColor=white"/>
  <img src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat&logo=HuggingFace&logoColor=black"/>
  <img src="https://img.shields.io/badge/Transformers-FFD21E?style=flat&logo=HuggingFace&logoColor=black"/>
  <br>
  <h3>Automation & Backend</h3>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white"/>
</div>

<br>

## 🚀 How to Run

### 1. Installation
```bash
git clone [https://github.com/YourID/nDRIMS-Agent.git](https://github.com/YourID/nDRIMS-Agent.git)
cd nDRIMS-Agent
pip install -r requirements.txt
