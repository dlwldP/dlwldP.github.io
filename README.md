# dlwldP.github.io

[Jekyll](https://jekyllrb.com/) + [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) 테마로 만든 개인 기술 블로그입니다.

## 배포 전 설정 (한 번만 해주세요)

1. **GitHub Pages 소스 변경**
   저장소 `Settings > Pages`에서 Source를 **"GitHub Actions"** 로 변경해주세요. (기본값인 "Deploy from a branch"로는 이 테마가 빌드되지 않습니다.)
   변경 후 `main` 브랜치에 push하면 `.github/workflows/pages-deploy.yml` 워크플로우가 자동으로 빌드/배포합니다.

2. **댓글(giscus) 활성화**
   - 저장소 `Settings > General > Features`에서 **Discussions**를 켜주세요.
   - [giscus.app](https://giscus.app)에 접속해 이 저장소(`dlwldP/dlwldP.github.io`)를 입력하고 안내에 따라 giscus GitHub App을 설치하세요.
   - giscus.app이 알려주는 `data-repo-id`, `data-category-id` 값을 `_config.yml`의 `comments.giscus.repo_id`, `comments.giscus.category_id`에 채워 넣으세요.

3. **프로필 정보 수정**
   `_config.yml`의 `title`, `tagline`, `social` 값과 `_tabs/about.md`를 원하는 내용으로 수정하세요.

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
