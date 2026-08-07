# dlwldP.github.io

[Jekyll](https://jekyllrb.com/) + [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) 테마로 만든 기술 블로그 겸 포트폴리오입니다. 전시(display) 목적이라 댓글 기능은 사용하지 않습니다.

## 배포 설정

- ~~**GitHub Pages 소스 변경**~~ ✅ 완료 (`Settings > Pages` → Source: GitHub Actions). `main` 브랜치에 push하면 `.github/workflows/pages-deploy.yml` 워크플로우가 자동으로 빌드/배포합니다.
- **프로필/프로젝트 정보 수정**: `_config.yml`의 `title`, `tagline`, `social` 값, `_tabs/about.md`(소개), `_tabs/projects.md`(프로젝트)를 원하는 내용으로 수정하세요.

## 글 작성 방법

`_posts/` 폴더에 아래 형식으로 마크다운 파일을 추가하면 됩니다.

```
_posts/YYYY-MM-DD-제목.md
```

```markdown
---
title: 글 제목
date: 2026-08-05 09:00:00 +0900
categories: [카테고리1, 카테고리2]
tags: [태그1, 태그2]
---

본문 내용
```

`main` 브랜치에 push하면 자동으로 빌드되어 사이트에 반영됩니다.

## 로컬에서 미리보기

```bash
bundle install
bundle exec jekyll serve
```

`http://localhost:4000` 에서 확인할 수 있습니다.
