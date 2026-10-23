# dlwldP.github.io

백엔드 · 클라우드 인프라 개발자 포트폴리오 — **https://dlwldp.github.io**

Jekyll + [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) 테마 기반의 한 페이지 포트폴리오입니다.

## 내용 수정

화면의 내용은 모두 `_data/` 파일에서 나옵니다.

| 파일 | 내용 |
| --- | --- |
| `_data/projects.yml` | 프로젝트 카드 (`rank`: 대표 프로젝트 순서, `category`: 부가 프로젝트 분야, `live: true`: Live 배지, `notice`: 안내 한 줄, `metrics`: 운영 지표) |
| `_data/categories.yml` | 부가 프로젝트 분야 이름 · 순서 |
| `_data/career.yml` | 경력 타임라인 (오래된 순으로 작성, 화면에는 최신순) |
| `_data/skills.yml` | 기술 스택 |
| `_data/domains.yml` | 업무 도메인 |
| `_config.yml` | 사이트 제목 · 설명 · 연락처 이메일 |

각 파일 맨 위 주석에 작성 규칙이 있습니다.

## 로컬 실행

```bash
bundle install
bundle exec jekyll serve   # http://localhost:4000
```

## 배포

`main` 브랜치에 push하면 GitHub Actions(`.github/workflows/pages-deploy.yml`)가 빌드 · 검사 후 GitHub Pages에 배포합니다.
