# Discord GitHub 알림 시스템

GitHub에서 PR이 생성되거나 승인될 때 Discord로 실시간 알림을 보내는 시스템입니다.

## 🚀 기능

- ✅ PR 생성/업데이트/머지/닫기 알림
- ✅ 커밋 푸시 알림
- ✅ 한국어 메시지 지원
- ✅ 이모지와 마크다운 포맷팅

## 📋 설정 방법

### 1. Discord Webhook 생성

1. Discord 서버에서 알림을 받을 채널 선택
2. 채널 설정 → 웹후크 → 새 웹후크 생성
3. 웹후크 URL 복사 (예: `https://discord.com/api/webhooks/...`)

### 2. GitHub Secrets 설정

1. GitHub 저장소 → Settings → Secrets and variables → Actions
2. "New repository secret" 클릭
3. 이름: `DISCORD_WEBHOOK_URL`
4. 값: Discord에서 복사한 웹후크 URL 입력

### 3. 워크플로우 파일 확인

`.github/workflows/discord-notify.yml` 파일이 저장소에 있는지 확인

## 🔧 알림 이벤트

- **PR 생성**: 🔔 새로운 PR이 생성되었습니다!
- **PR 머지**: ✅ PR이 머지되었습니다!
- **PR 닫기**: ❌ PR이 닫혔습니다!
- **PR 재오픈**: 🔄 PR이 다시 열렸습니다!
- **커밋 푸시**: 🚀 새로운 커밋이 푸시되었습니다!

## 📝 메시지 예시

```
🔔 새로운 PR이 생성되었습니다!

📁 저장소: hanwj75/discord_test
🙋 작성자: hanwj75
📝 제목: 새로운 기능 추가
🔗 링크: https://github.com/hanwj75/discord_test/pull/1
```

## ⚠️ 주의사항

- GitHub Webhook을 Discord에 직접 연결하면 HTTP 400 에러가 발생합니다
- 이 시스템은 GitHub Actions를 사용해서 올바른 형식으로 메시지를 변환합니다
- Discord 웹후크 URL은 절대 공개하지 마세요!
