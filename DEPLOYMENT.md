# 무료 배포 가이드

이 프로젝트를 무료로 배포하는 여러 방법을 안내합니다.

## 🚀 배포 옵션

### 1. GitHub Pages (가장 추천 ⭐)

**장점:**
- 완전 무료
- 설정이 매우 간단
- HTTPS 자동 제공
- 커스텀 도메인 지원

**단계:**

1. **GitHub 저장소 생성**
   ```bash
   # 현재 디렉토리에서
   git init
   git add restaurant-react.html
   git commit -m "Initial commit"
   ```

2. **GitHub에 저장소 생성 후 푸시**
   - GitHub.com에 로그인
   - "New repository" 클릭
   - 저장소 이름 입력 (예: `restaurant-list`)
   - "Create repository" 클릭
   - GitHub에서 제공하는 명령어 실행:
   ```bash
   git remote add origin https://github.com/사용자명/restaurant-list.git
   git branch -M main
   git push -u origin main
   ```

3. **GitHub Pages 활성화**
   - 저장소 페이지에서 "Settings" 탭 클릭
   - 왼쪽 메뉴에서 "Pages" 클릭
   - Source: "Deploy from a branch" 선택
   - Branch: "main" 선택, "/ (root)" 선택
   - "Save" 클릭

4. **파일 이름 변경 (선택사항)**
   - `restaurant-react.html`을 `index.html`로 변경하면 더 깔끔한 URL 제공
   ```bash
   git mv restaurant-react.html index.html
   git commit -m "Rename to index.html"
   git push
   ```

5. **배포 완료**
   - 몇 분 후 `https://사용자명.github.io/restaurant-list/` 접속 가능

---

### 2. Netlify (드래그 앤 드롭)

**장점:**
- 매우 간단한 배포 (드래그 앤 드롭)
- 자동 HTTPS
- 커스텀 도메인 지원

**단계:**

1. **Netlify 접속**
   - https://www.netlify.com 접속
   - "Sign up" (GitHub 계정으로 로그인 가능)

2. **파일 배포**
   - 대시보드에서 "Add new site" → "Deploy manually"
   - `restaurant-react.html` 파일을 드래그 앤 드롭
   - 파일 이름을 `index.html`로 변경 (선택사항)

3. **배포 완료**
   - 자동으로 URL 생성 (예: `random-name-123.netlify.app`)
   - Settings에서 사이트 이름 변경 가능

---

### 3. Vercel

**장점:**
- Git 연동으로 자동 배포
- 매우 빠른 성능
- 무료 HTTPS

**단계:**

1. **Vercel 접속**
   - https://vercel.com 접속
   - GitHub 계정으로 로그인

2. **프로젝트 배포**
   - "Add New Project" 클릭
   - GitHub 저장소 선택
   - "Deploy" 클릭

**참고:** Vercel은 보통 Node.js 프로젝트에 최적화되어 있지만, 정적 파일도 배포 가능합니다.

---

### 4. Surge.sh (명령줄)

**장점:**
- 명령줄로 빠른 배포
- 매우 간단

**단계:**

```bash
# npm 설치 필요
npm install -g surge

# 배포
surge
# 이메일 입력
# 비밀번호 입력
# 프로젝트 경로 입력: ./
# 도메인 입력 (예: my-restaurant-list.surge.sh)
```

---

## ⚠️ 주의사항

### CORS 문제

공공데이터포털 API를 직접 호출하면 CORS 오류가 발생할 수 있습니다.

**해결 방법:**

1. **CORS 프록시 사용**
   - API 호출 시 프록시 서버 사용
   - 예: `https://cors-anywhere.herokuapp.com/` (제한적)

2. **백엔드 프록시 서버 구축** (권장)
   - Node.js Express 서버로 API 프록시 생성
   - Vercel Serverless Functions 또는 Netlify Functions 사용

3. **브라우저 확장 프로그램 사용**
   - 개발/테스트 용도로만 사용

---

## 📝 배포 전 체크리스트

- [ ] API 키가 코드에 포함되어 있는지 확인 (보안상 문제없음 - 공개 API)
- [ ] 파일 이름을 `index.html`로 변경 고려
- [ ] 모바일 반응형 테스트
- [ ] 브라우저 호환성 테스트

---

## 🔗 각 서비스 비교

| 서비스 | 난이도 | 속도 | 커스텀 도메인 | 무료 한도 |
|--------|--------|------|---------------|-----------|
| GitHub Pages | ⭐⭐ | 빠름 | ✅ | 넉넉함 |
| Netlify | ⭐ | 매우 빠름 | ✅ | 넉넉함 |
| Vercel | ⭐⭐ | 매우 빠름 | ✅ | 넉넉함 |
| Surge | ⭐⭐⭐ | 빠름 | ✅ | 제한적 |

---

## 💡 추천 방법

**처음 배포하는 경우:** GitHub Pages 또는 Netlify 추천
- 설정이 가장 간단
- 문서화가 잘 되어 있음
- 무료 한도가 충분함

