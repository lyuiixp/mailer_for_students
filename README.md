# 📧 수강생 대상 자동 메일 발송 도구

중간 및 최종 점수를 기준으로 수강생들에게 일괄적으로 이메일을 발송하는 파이썬 기반 도구.  
CSV 기반 점수표를 불러와, 템플릿 메일을 개별 수신자에게 자동으로 전송.

---

## 📁 구성 파일

| 파일명 | 설명 |
|--------|------|
| `mail.ipynb` | 공통 기능을 담은 메일 발송 기본 노트북 |
| `mail_middle.ipynb` | 중간 점수 산출 기반 메일 발송 |
| `mail_last.ipynb` | 최종 점수 산출 기반 메일 발송 |
| `middle_score_3기.csv` | 중간 점수표 (이름, 기수, 이메일 포함) |
| `last_score_1000.csv` | 최종 점수표 (개인 점수 및 성적 정보 포함) |

---

## ✅ 사용 방법

### 1. Gmail SMTP 사용 설정
- [보안 수준이 낮은 앱 허용](https://myaccount.google.com/lesssecureapps) → **허용**
- 또는 앱 비밀번호 사용 설정 (권장)

### 2. 메일 내용 설정
`mail_middle.ipynb` 또는 `mail_last.ipynb`에서 아래 항목들을 수정하세요:

```python
my_email = "your_email@gmail.com"
my_password = "your_password_or_app_password"
```

그리고 메일 본문 템플릿도 자유롭게 조정 가능:

```python
content = f"""
안녕하세요, {name}님.
다음은 {round_name} 점수입니다.
- 총점: {score}
감사합니다.
"""
```

---

## 📊 CSV 파일 포맷 예시

### `middle_score_3기.csv`

| 이름   | 기수     | 이메일             | 중간점수 |
|--------|----------|--------------------|----------|
| 홍길동 | DR-01123 | gil@example.com    | 85       |
| 이순신 | DR-01124 | soon@example.com   | 92       |

### `last_score_1000.csv`

| 이름   | 기수     | 이메일             | 최종점수 |
|--------|----------|--------------------|----------|
| 김유신 | DR-01125 | yushin@example.com | 98       |

---

## 📤 실행 예시

```bash
# Jupyter Notebook 내 실행
Run all cells ▶️
```

- 점수에 따라 메일이 개별 발송됨
- 중간/최종 성적에 따라 각각 다르게 메시지를 구성 가능

---

## 🔐 보안 주의사항

- 코드에 직접 비밀번호를 포함하지 말고 `.env` 파일 또는 `getpass()` 사용 권장
- Gmail → OAuth2 인증 도입 시 API 기반 확장 가능

---

## ✨ 향후 기능 확장

- 점수에 따른 성적 등급 표시
- 템플릿 HTML 메일 발송
- 메일 전송 로그 자동 기록
- 슬랙/디스코드 등과의 연동

---

> 이 도구는 교육 운영을 자동화하고 수강생과의 커뮤니케이션을 더 효율적으로 만들어줍니다.  
> 더 많은 교육 자동화 예제는 [GPTOnline.ai](https://gptonline.ai/ko/)에서 확인하세요!
