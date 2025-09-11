# 🚀 StockPulse

**글로벌 뉴스 + 주가 데이터 → AI 분석 → 매일 아침 종목 추천 웹앱**

## 📋 프로젝트 개요

StockPulse는 AI를 활용하여 글로벌 뉴스와 주가 데이터를 분석하고, 매일 아침 최적의 종목을 추천하는 웹 애플리케이션입니다.

## 🏗️ 아키텍처

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │   Backend       │    │   Data Collector │
│   (Next.js)     │◄──►│   (FastAPI)     │◄──►│   (Node.js)     │
│   Vercel        │    │   Render/Railway│    │   Cron Jobs     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 ▼
                    ┌─────────────────┐
                    │   Supabase      │
                    │   PostgreSQL    │
                    │   Edge Functions │
                    └─────────────────┘
```

## 🛠️ 기술 스택

### Frontend
- **Next.js 14** (React 18)
- **TailwindCSS** (스타일링)
- **Recharts** (차트)
- **PWA** (모바일 앱 지원)
- **Vercel** (배포)

### Backend (AI 분석)
- **Python FastAPI**
- **HuggingFace FinBERT** (뉴스 감성 분석)
- **Facebook Prophet** (시계열 예측)
- **Render/Railway** (배포)

### Data Collection
- **Node.js** (크롤러)
- **Yahoo Finance API**
- **Google News API**
- **Vercel Cron Jobs** (스케줄링)

### Database & Infrastructure
- **Supabase** (PostgreSQL + 인증 + Edge Functions)
- **Vercel** (프론트엔드 배포 + Cron)

## 📁 프로젝트 구조

```
StockPulse/
├── frontend/                 # Next.js 프론트엔드
│   ├── src/
│   │   ├── app/             # App Router
│   │   ├── components/      # React 컴포넌트
│   │   ├── lib/             # 유틸리티 함수
│   │   └── types/           # TypeScript 타입
│   ├── public/              # 정적 파일
│   └── package.json
├── backend/                  # Python FastAPI AI 서버
│   ├── app/
│   │   ├── models/          # AI 모델
│   │   ├── services/        # 비즈니스 로직
│   │   └── api/             # API 엔드포인트
│   ├── requirements.txt
│   └── Dockerfile
├── data-collector/           # 데이터 수집 크롤러
│   ├── src/
│   │   ├── collectors/      # 각종 데이터 수집기
│   │   ├── schedulers/      # 스케줄러
│   │   └── utils/           # 유틸리티
│   └── package.json
├── supabase/                 # Supabase 설정
│   ├── migrations/           # DB 마이그레이션
│   └── functions/           # Edge Functions
├── vercel.json               # Vercel 설정
└── docker-compose.yml        # 로컬 개발 환경
```

## 🚀 시작하기

### 1. 저장소 클론
```bash
git clone <repository-url>
cd StockPulse
```

### 2. 의존성 설치
```bash
npm install
```

### 3. 환경 변수 설정
각 워크스페이스의 `.env.example` 파일을 참고하여 `.env.local` 파일을 생성하세요.

### 4. 개발 서버 실행
```bash
# 프론트엔드
npm run dev

# AI 서버
npm run ai-server

# 데이터 수집기
npm run collector
```

## 📊 데이터 흐름

1. **매일 07:00 AM**: Cron Job 실행
2. **데이터 수집**: 주가 + 뉴스 데이터 수집
3. **AI 분석**: NLP + 시계열 예측
4. **결과 저장**: 추천 종목을 Supabase에 저장
5. **사용자 접속**: 웹앱에서 추천 종목 확인

## 🔧 주요 기능

- 📈 **실시간 주가 데이터** (미국/한국)
- 📰 **글로벌 뉴스 분석** (AI 감성 분석)
- 🤖 **AI 기반 종목 추천**
- 📱 **모바일 최적화** (PWA)
- ⏰ **자동 스케줄링** (매일 아침 갱신)

## 📝 라이선스

MIT License
