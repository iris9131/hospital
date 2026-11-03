# 네이버 병원 글 모음

네이버 블로그에서 원장이 직접 쓴 잘 쓴 글(병원 공지·원장 소개·진료 철학·브랜딩)을 모아 보는 곳.
수집은 **내 컴퓨터의 Claude Code + Aside 브라우저**로 하고, 결과는 `posts.json` 에 쌓인다.

## 1. 한 번만 준비

1. Aside 앱 실행 + 네이버 로그인, 터미널에서 `aside --version` 확인
2. 네이버 블로그 읽기 스킬 설치

```bash
npx skills add tjdwls101010/Agentic-SNS
```

3. 이 브랜치 받기

```bash
git fetch origin claude/blissful-fermi-hhmfl0 && git checkout claude/blissful-fermi-hhmfl0
```

## 2. 수집

저장소 폴더에서 `claude` 를 실행하고:

```
/naver-hospital-writing 성형외과 피부과
```

스킬(`.claude/skills/naver-hospital-writing/SKILL.md`)이 검색 → 후보 거르기 → 본문 읽기 → 채점 → `posts.json` 기록까지 한다.
다른 과목은 `/naver-hospital-writing 치과 한의원` 처럼 이어서 돌리면 쌓인다.

## 3. 보기 (로컬 서버)

```bash
python3 -m http.server 8000 -d naver-collection
```

브라우저에서 http://localhost:8000 — 과목·유형·선정 여부로 거르고, 점수순/최신순으로 정렬한다.

## 4. 링크로 공유하고 싶으면

`posts.json` 을 커밋하고 push 하면, 클라우드 세션에서 같은 화면을 링크 페이지로 올릴 수 있다.
