# SwimPilot App Store 배포 가이드

## 📁 폴더 구성

```
AppStore-Deploy/
├── README.md                  # 이 파일
├── index.html                 # 자동 언어 감지 리다이렉트
├── ko.html                    # 한국어 개인정보처리방침
├── en.html                    # 영어 개인정보처리방침
├── github-pages-guide.md      # GitHub Pages 배포 가이드
└── privacy-policy.html        # 원본 (ko.html과 동일)
```

## 🌐 다국어 지원

SwimPilot은 10개 언어를 지원하며, 개인정보처리방침도 다국어로 제공됩니다.

### 현재 지원 언어 (10개 언어)
- ✅ 한국어 (ko.html)
- ✅ 영어 (en.html)
- ✅ 일본어 (ja.html)
- ✅ 중국어 간체 (zh-Hans.html)
- ✅ 중국어 번체 (zh-Hant.html)
- ✅ 스페인어 (es.html)
- ✅ 프랑스어 (fr.html)
- ✅ 독일어 (de.html)
- ✅ 포르투갈어 (pt.html)
- ✅ 러시아어 (ru.html)

## 🚀 빠른 시작

### 1. 개인정보처리방침 배포

#### GitHub Pages 배포 (추천)
```bash
# 1. GitHub에서 새 저장소 생성
#    저장소 이름: swimpilot-privacy
#    Public 저장소로 생성

# 2. 로컬에서 배포
cd AppStore-Deploy
git init
git add .
git commit -m "feat: Add multilingual privacy policy"
git remote add origin https://github.com/YOUR_USERNAME/swimpilot-privacy.git
git branch -M main
git push -u origin main

# 3. GitHub Pages 활성화
#    Settings > Pages > Source: main branch > Save

# 4. 배포 완료 확인 (1-2분 소요)
#    한국어: https://YOUR_USERNAME.github.io/swimpilot-privacy/ko.html
#    영어: https://YOUR_USERNAME.github.io/swimpilot-privacy/en.html
#    자동 감지: https://YOUR_USERNAME.github.io/swimpilot-privacy/
```

### 2. App Store Connect 등록

#### Privacy Policy URL 입력 (언어별)
```
App Store Connect > My Apps > SwimPilot > App Information

한국어: https://YOUR_USERNAME.github.io/swimpilot-privacy/ko.html
영어: https://YOUR_USERNAME.github.io/swimpilot-privacy/en.html
일본어: https://YOUR_USERNAME.github.io/swimpilot-privacy/ja.html
중국어(간체): https://YOUR_USERNAME.github.io/swimpilot-privacy/zh-Hans.html
중국어(번체): https://YOUR_USERNAME.github.io/swimpilot-privacy/zh-Hant.html
스페인어: https://YOUR_USERNAME.github.io/swimpilot-privacy/es.html
프랑스어: https://YOUR_USERNAME.github.io/swimpilot-privacy/fr.html
독일어: https://YOUR_USERNAME.github.io/swimpilot-privacy/de.html
포르투갈어: https://YOUR_USERNAME.github.io/swimpilot-privacy/pt.html
러시아어: https://YOUR_USERNAME.github.io/swimpilot-privacy/ru.html
```

## 📋 필수 확인 사항

### 개인정보처리방침 수정
각 언어별 파일에서 다음 항목을 반드시 확인하세요:

#### 1. 이메일 주소
```html
이메일: <a href="mailto:o3orbit.labs@gmail.com">o3orbit.labs@gmail.com</a>
```

#### 2. GitHub Pages URL 변경
```
배포 후 생성되는 실제 URL로 각 언어별 파일 확인
```

## ✅ App Store 심사 체크리스트

### 필수 문서
- [x] 개인정보처리방침 (Privacy Policy) - 다국어

### 개인정보처리방침 확인사항
- [x] 시행일 명시
- [x] 개인정보 보호책임자 연락처
- [x] 수집하는 개인정보 항목
- [x] 이용 목적
- [x] 보유 및 파기 기간
- [x] 제3자 제공 내역
- [x] 처리 위탁 내역
- [x] 정보주체 권리 (열람·정정·삭제)
- [x] 보호 조치
- [x] HTTPS URL (GitHub Pages 자동 제공)

### URL 접근성 확인
- [ ] HTTPS 프로토콜 사용 ✅
- [ ] 공개 접근 가능 ✅
- [ ] 모바일 브라우저 렌더링 확인
- [ ] 데스크톱 브라우저 렌더링 확인
- [ ] 각 언어별 URL 정상 작동 확인

## 🔄 업데이트 방법

### 개인정보처리방침 수정 시
```bash
# 1. 해당 언어 파일 수정 (예: ko.html, en.html)

# 2. Git 커밋 및 푸시
git add ko.html en.html
git commit -m "docs: Update privacy policy"
git push

# 3. 1-2분 후 자동 반영
```

### 새로운 언어 추가 시
```bash
# 1. 기존 파일 복사 (예: 일본어 추가)
cp en.html ja.html

# 2. ja.html 내용을 일본어로 번역

# 3. index.html 수정 (언어 감지 로직 추가)
# 예:
# else if (userLang.startsWith('ja')) {
#     window.location.href = 'ja.html';
# }

# 4. Git 커밋 및 푸시
git add ja.html index.html
git commit -m "feat: Add Japanese privacy policy"
git push
```

## 📞 문의

개인정보처리방침 관련 문의:
- 이메일: o3orbit.labs@gmail.com

---

**마지막 업데이트**: 2025년 10월 20일
