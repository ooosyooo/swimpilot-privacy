# GitHub Pages 배포 가이드

## 🎯 목표
`privacy-policy.html`을 GitHub Pages에 배포하여 공개 URL 생성

## 📋 사전 준비
- GitHub 계정
- Git 설치
- 터미널 (Mac/Linux) 또는 Git Bash (Windows)

---

## 🚀 배포 단계별 가이드

### 1단계: GitHub 저장소 생성

1. **GitHub 웹사이트 접속**
   - https://github.com 로그인

2. **새 저장소 생성**
   - 우측 상단 `+` 버튼 클릭
   - `New repository` 선택

3. **저장소 설정**
   ```
   Repository name: swimpilot-privacy
   Description: SwimPilot Privacy Policy
   Public: ✅ (필수 - GitHub Pages는 Public 저장소만 무료)
   Initialize: ❌ (체크 해제)
   ```

4. **Create repository** 클릭

---

### 2단계: 로컬에서 배포 준비

```bash
# 1. AppStore-Deploy 폴더로 이동
cd /Users/kakaovx/DanWorkspace/ooo/SwimPilot/AppStore-Deploy

# 2. Git 초기화
git init

# 3. 파일 추가
git add privacy-policy.html

# 4. 커밋
git commit -m "feat: Add SwimPilot privacy policy"

# 5. 원격 저장소 연결 (YOUR_USERNAME을 실제 GitHub 사용자명으로 변경)
git remote add origin https://github.com/YOUR_USERNAME/swimpilot-privacy.git

# 6. 브랜치 이름 변경
git branch -M main

# 7. 푸시
git push -u origin main
```

**주의**: `YOUR_USERNAME`을 실제 GitHub 사용자명으로 변경하세요!

---

### 3단계: GitHub Pages 활성화

1. **GitHub 저장소 페이지로 이동**
   - https://github.com/YOUR_USERNAME/swimpilot-privacy

2. **Settings 클릭**
   - 저장소 상단 메뉴에서 `Settings` 클릭

3. **Pages 메뉴 선택**
   - 왼쪽 사이드바에서 `Pages` 클릭

4. **Source 설정**
   ```
   Branch: main
   Folder: / (root)
   ```

5. **Save 버튼 클릭**

6. **배포 완료 대기**
   - 1-2분 후 자동 배포
   - 페이지 상단에 URL 표시됨
   - `Your site is live at https://YOUR_USERNAME.github.io/swimpilot-privacy/`

---

### 4단계: 배포 확인

1. **URL 접속 확인**
   ```
   https://YOUR_USERNAME.github.io/swimpilot-privacy/privacy-policy.html
   ```

2. **모바일 확인**
   - 스마트폰 브라우저에서 접속
   - 레이아웃 정상 표시 확인

3. **HTTPS 확인**
   - URL이 `https://`로 시작하는지 확인
   - 자물쇠 아이콘 표시 확인

---

## 🔄 업데이트 방법

### 개인정보처리방침 수정 시

```bash
# 1. privacy-policy.html 파일 수정

# 2. Git 커밋
git add privacy-policy.html
git commit -m "docs: Update privacy policy - [수정 내용]"

# 3. 푸시
git push

# 4. 1-2분 후 자동 반영
```

### 배포 상태 확인

```bash
# Actions 탭에서 배포 진행 상황 확인
https://github.com/YOUR_USERNAME/swimpilot-privacy/actions
```

---

## 🌐 커스텀 도메인 설정 (선택사항)

### 자체 도메인 사용 시

1. **도메인 구매**
   - 예: `privacy.swimpilot.app`

2. **DNS 설정**
   ```
   Type: CNAME
   Host: privacy
   Value: YOUR_USERNAME.github.io
   ```

3. **GitHub Pages 설정**
   - Settings > Pages > Custom domain
   - `privacy.swimpilot.app` 입력
   - Save 클릭

4. **HTTPS 활성화**
   - `Enforce HTTPS` 체크
   - 자동 인증서 발급 (Let's Encrypt)

---

## ❌ 문제 해결

### 1. 404 Not Found 에러

**원인**: 파일 경로 오류

**해결**:
```bash
# 파일 이름 확인
ls -la

# privacy-policy.html이 있는지 확인
# 없으면 파일명 변경
git mv index.html privacy-policy.html
git commit -m "fix: Rename file"
git push
```

### 2. 배포가 안 됨

**원인**: GitHub Actions 실패

**해결**:
1. Actions 탭 확인
2. 에러 로그 확인
3. 파일 권한 확인

### 3. HTTPS 안 됨

**원인**: GitHub Pages 활성화 직후

**해결**:
- 10-30분 대기 (자동 인증서 발급 소요 시간)
- Settings > Pages > Enforce HTTPS 체크

### 4. 접속 느림

**원인**: CDN 캐시 미적용

**해결**:
- 첫 배포 후 전 세계 CDN 적용까지 시간 소요
- 5-10분 대기

---

## 📊 GitHub Pages 제약사항

| 항목 | 제한 |
|------|------|
| **저장소 크기** | 1GB 권장 |
| **대역폭** | 100GB/월 |
| **빌드** | 시간당 10회 |
| **파일 크기** | 100MB 이하 |
| **저장소 타입** | Public만 무료 |

---

## ✅ 최종 확인 체크리스트

- [ ] GitHub 저장소 생성 완료
- [ ] privacy-policy.html 업로드 완료
- [ ] GitHub Pages 활성화 완료
- [ ] HTTPS URL 접속 확인
- [ ] 모바일 브라우저 확인
- [ ] App Store Connect에 URL 등록 완료

---

## 🔗 유용한 링크

- [GitHub Pages 공식 문서](https://docs.github.com/pages)
- [GitHub Pages 도메인 설정](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [GitHub Pages 문제 해결](https://docs.github.com/pages/setting-up-a-github-pages-site-with-jekyll/troubleshooting-jekyll-build-errors-for-github-pages-sites)

---

**마지막 업데이트**: 2025년 1월 20일
