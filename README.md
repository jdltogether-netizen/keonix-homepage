# KEONIX Labs — 회사 홈페이지

정적 1페이지 웹사이트 (`index.html` 단일 파일, 별도 빌드 과정 없음).

## GitHub Pages로 배포하는 방법

1. GitHub에 새 저장소를 만듭니다. (예: `keonix-website`)
2. 이 폴더의 `index.html`을 저장소 루트에 업로드합니다.
   - GitHub 웹사이트에서 "Add file → Upload files"로 드래그 앤 드롭해도 되고,
   - 로컬에 git이 설치되어 있다면 아래 명령어를 사용해도 됩니다.
   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial KEONIX homepage"
   git branch -M main
   git remote add origin https://github.com/<본인계정>/keonix-website.git
   git push -u origin main
   ```
3. 저장소의 **Settings → Pages**로 이동합니다.
4. **Source**를 `Deploy from a branch`로 설정하고, Branch를 `main` / `/ (root)`로 지정한 뒤 저장합니다.
5. 1~2분 후 `https://<본인계정>.github.io/keonix-website/` 주소에서 사이트를 확인할 수 있습니다.

## 커스텀 도메인 연결 (keonix.co.kr)

1. 저장소 루트에 `CNAME`이라는 파일을 만들고 안에 `keonix.co.kr` 한 줄만 적어 함께 업로드합니다.
2. 도메인 등록기관(DNS)에서 `keonix.co.kr`(또는 `www`)에 대해 GitHub Pages가 안내하는 A 레코드 / CNAME 레코드를 추가합니다.
3. GitHub Settings → Pages에서 Custom domain 필드에 `keonix.co.kr`을 입력하고 저장합니다.

## 내용 수정하기

`index.html` 안에서 아래 항목을 찾아 텍스트만 바꾸면 됩니다.

- 회사 소개 문구: `<section class="hero" id="home">` 내부의 `<h1 class="hero-title">`, `<p class="hero-sub">`
- 팀 소개: `<section ... id="team">` 안의 각 `<div class="member">` 블록
- 채용 공고: `<section ... id="careers">` 안의 `<a class="job">` 블록 (실제 공고가 정해지면 직무명/부서만 교체)
- 연락처: `<section ... id="contact">` 안의 `<div class="contact-item">` 블록

팀원 사진이 준비되면 각 `<div class="avatar">이니셜</div>`를 `<img src="사진경로" ...>`로 교체하면 됩니다.
