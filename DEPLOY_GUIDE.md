# Netlify 배포 가이드

이 프로젝트는 정적 웹사이트(Static Website)로 구성되어 있어 Netlify를 통해 무료로 쉽게 배포할 수 있습니다.

## 방법 1: GitHub 연동 (추천 - 자동 배포)

코드가 GitHub에 올라가 있다면 이 방법이 가장 좋습니다. 코드를 수정하고 푸시할 때마다 자동으로 배포됩니다.

1. [Netlify](https://app.netlify.com/)에 로그인 후 **"Add new site"** > **"Import an existing project"** 클릭
2. **GitHub** 선택 후 `july-0703/dev` 저장소 선택
3. 설정 확인:
   - **Base directory:** (비워둠)
   - **Publish directory:** `landing-page`
4. **Deploy Site** 버튼 클릭

## 방법 2: Netlify Drop (간편)

1. [Netlify Drop](https://app.netlify.com/drop) 사이트에 접속합니다.
2. `e:\Web-Design\marketing_dev` 폴더를 통째로 브라우저 창에 드래그 앤 드롭합니다.
3. 배포가 완료되면 제공된 URL로 접속하여 확인합니다.

## 방법 3: Netlify CLI (터미널 사용)

터미널에서 직접 배포하려면 다음 명령어를 실행하세요. (Netlify 계정이 필요합니다)

1. Netlify CLI 설치 (없을 경우):
   ```bash
   npm install -g netlify-cli
   ```

2. 로그인:
   ```bash
   netlify login
   ```

3. 배포 (현재 폴더에서 실행):
   ```bash
   netlify deploy --prod
   ```
   - *Publish directory*를 물어보면 `landing-page`라고 입력하거나, 이미 `netlify.toml`에 설정되어 있어 자동으로 감지될 수 있습니다.

## 방법 4: Vercel 배포 (가장 빠름)

Vercel은 한국에서도 속도가 빠르고 설정이 간편합니다.

1. [Vercel](https://vercel.com/) 로그인 후 **"Add New..."** > **"Project"** 클릭
2. GitHub의 `july-0703/dev` 저장소 **Import** 클릭
3. **Configure Project** 화면에서:
   - **Framework Preset:** Other
   - **Root Directory:** `Edit` 버튼을 누르고 `landing-page` 폴더를 선택하세요. (중요!)
4. **Deploy** 클릭

## 설정 정보

- **Publish Directory (배포 폴더):** `landing-page`
- **설정 파일:** `netlify.toml` (이미 생성해 두었습니다)

## 🚀 한국 사용자 유입 늘리기 (SEO & 마케팅)

한국에서 방문자를 늘리기 위해서는 **검색 엔진 등록**이 필수입니다.

### 1. 네이버 서치어드바이저 등록 (필수)
한국 사용자는 네이버 검색을 많이 사용하므로, 네이버에 사이트를 알려야 합니다.
1. [네이버 서치어드바이저](https://searchadvisor.naver.com/) 접속 및 로그인
2. **웹마스터 도구** > 사이트 등록 (Netlify에서 발급받은 URL 입력)
3. **HTML 태그** 방식 선택 후, 제공되는 메타 태그 복사
4. `landing-page/index.html` 파일의 `<meta name="naver-site-verification" ... />` 부분에 붙여넣기 후 재배포
5. **검증** 완료 후, [요청] > [사이트맵 제출] 메뉴에서 `sitemap.xml` 제출

### 2. 구글 서치 콘솔 등록
1. [구글 서치 콘솔](https://search.google.com/search-console) 접속
2. URL 접두어 방식으로 사이트 주소 입력
3. HTML 태그 복사 후 `landing-page/index.html`의 `<meta name="google-site-verification" ... />` 부분에 붙여넣기 및 재배포
4. `sitemap.xml` 제출

### 3. 사이트맵(sitemap.xml) 설정 주의사항
`landing-page/sitemap.xml` 파일을 열어 `https://yoursite.netlify.app` 부분을 **실제 발급받은 Netlify 주소**로 모두 변경해주세요. (예: `https://my-awesome-site.netlify.app`)
