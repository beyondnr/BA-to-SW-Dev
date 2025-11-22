# BA to SW Dev Project

Business Analyst(BA)에서 Software Developer로 전환하는 과정을 기록하고, 실제 프로덕트(SaaS Employee Schedule Management)를 기획부터 개발까지 구현하는 프로젝트입니다.

## 📂 Repository Structure

이 프로젝트는 **기획/문서(Docs)**와 **소스 코드(Source Code)**를 분리하여 관리하는 구조를 가지고 있습니다.

```
BA-to-SW-Dev/
├── Docs/            # 기획서, 분석 자료, SRS, PRD 등 모든 문서
│   ├── 0_DEV_Tools  # 개발 보조 도구 및 프롬프트
│   ├── 1_Tools      # 비즈니스 분석 프레임워크
│   ├── 2_Docs       # PRD, SRS, Value Proposition 등 핵심 문서
│   └── ...
│
├── Proto/
│   └── Studio/      # [Submodule] 실제 소스 코드 리포지토리
│       ├── src/     # Next.js 소스 코드
│       ├── tasks/   # 개발 관련 이슈 및 태스크 관리
│       └── ...
│
├── .cursor/         # AI Agent (Cursor) 설정 및 규칙
└── .vscode/         # VS Code 개발 환경 설정
```

## 🚀 Getting Started

이 프로젝트는 **Git Submodule**을 포함하고 있습니다. 처음 프로젝트를 내려받을 때는 아래 명령어를 사용해야 소스 코드(`Studio`)까지 함께 받아집니다.

### Clone Project
```bash
# 방법 1: 한 번에 클론하기 (권장)
git clone --recursive https://github.com/beyondnr/beyondnr.git

# 방법 2: 이미 클론했다면 서브모듈 업데이트하기
git submodule update --init --recursive
```

## 🔗 Related Repositories
- **Main Repo (Docs & Config)**: [beyondnr/beyondnr](https://github.com/beyondnr/beyondnr)
- **Code Repo (Studio)**: [beyondnr/studio](https://github.com/beyondnr/studio)

