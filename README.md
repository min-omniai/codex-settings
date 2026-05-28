# codex-settings

개인 Codex 설정 백업 저장소입니다.

게임 클라이언트 개발자이자 강사용 Codex 전역 지침, 설치할 공식 스킬 목록, 커스텀 스킬을 관리합니다.

## 관리 대상

이 저장소에 포함하는 파일:

- `AGENTS.md`: Codex 개인 전역 지침
- `skill-install-list.txt`: 새 PC에서 다시 설치할 공식 스킬 목록
- `skills/`: 직접 만든 커스텀 스킬
- `README.md`: 복원 방법

이 저장소에 포함하지 않는 파일:

- `auth.json`
- `config.toml`
- `logs_*.sqlite`
- `state_*.sqlite`
- `sessions/`
- `cache/`
- `.system/` 기본 스킬
- 플러그인 캐시

## 새 PC 복원 방법

1. 이 저장소를 원하는 위치에 clone합니다.

```powershell
git clone https://github.com/min-omniai/codex-settings.git
```

2. Codex 설정 폴더를 확인합니다.
```
$env:USERPROFILE\.codex
```

3. AGENTS.md를 Codex 설정 폴더로 복사합니다.
```
Copy-Item .\AGENTS.md $env:USERPROFILE\.codex\AGENTS.md -Force
```

4. 커스텀 스킬이 있다면 복사합니다.
```
Copy-Item .\skills\* $env:USERPROFILE\.codex\skills\ -Recurse -Force
```

5. skill-install-list.txt에 적힌 공식 스킬을 설치합니다.


현재 설치 대상:

gh-address-comments
gh-fix-ci
screenshot
security-best-practices
pdf
transcribe
Codex를 재시작합니다.

## 공식 스킬 설치 목록

공식 스킬은 저장소에 직접 포함하지 않고, skill-install-list.txt로 관리합니다.

설치 목록:

```text
gh-address-comments
gh-fix-ci
screenshot
security-best-practices
pdf
transcribe
```

## 커스텀 스킬 후보

앞으로 추가할 개인 스킬:

- game-lecture-builder: Unity/C# 강의안, 실습, 과제, 퀴즈, 해설 생성
- unity-client-review: Unity C# 코드 리뷰, 성능, 생명주기, 이벤트 해제, Addressables, UI 성능 점검
- unity-debug-workflow: Unity 에러 로그, 크래시, 프레임 드랍, 메모리 누수 분석
- game-assignment-review: 수강생 과제 코드 피드백


추가로 `.gitignore`가 잘 되어 있다면 README에는 민감 파일 주의 정도만 적어두면 됩니다. 이 README는 “미래의 나를 위한 설치 설명서” 역할이라고 생각하면 딱 맞습니다.

## OS별 복사 대상

이 저장소는 백업용입니다. Codex가 실제로 읽는 위치는 각 OS의 `.codex` 폴더입니다.

### Windows

Codex 설정 폴더:

```powershell
$env:USERPROFILE\.codex
```

예시:

```text
C:\Users\<UserName>\.codex
```

복사 대상:
```text
codex-settings\AGENTS.md
→ C:\Users\<UserName>\.codex\AGENTS.md

codex-settings\skill-install-list.txt
→ C:\Users\<UserName>\.codex\skill-install-list.txt

codex-settings\skills\
→ C:\Users\<UserName>\.codex\skills\
```

복사 명령:
```powershell
Copy-Item .\AGENTS.md $env:USERPROFILE\.codex\AGENTS.md -Force
Copy-Item .\skill-install-list.txt $env:USERPROFILE\.codex\skill-install-list.txt -Force

# 커스텀 스킬이 있을 때만
Copy-Item .\skills\* $env:USERPROFILE\.codex\skills\ -Recurse -Force
```

### macOS

Codex 설정 폴더:

```bash
~/.codex
```

예시:

```text
/Users/<UserName>/.codex
```

복사 대상:

```text
codex-settings/AGENTS.md
→ /Users/<UserName>/.codex/AGENTS.md

codex-settings/skill-install-list.txt
→ /Users/<UserName>/.codex/skill-install-list.txt

codex-settings/skills/
→ /Users/<UserName>/.codex/skills/
```

복사 명령:

```bash
mkdir -p ~/.codex/skills

cp ./AGENTS.md ~/.codex/AGENTS.md
cp ./skill-install-list.txt ~/.codex/skill-install-list.txt

# 커스텀 스킬이 있을 때만
cp -R ./skills/* ~/.codex/skills/
```

## 주의

codex-settings 저장소 자체를 .codex 폴더로 사용하지 않습니다.

```text
codex-settings
→ Git 백업 저장소

~/.codex 또는 C:\Users\<UserName>\.codex
→ Codex 실제 설정 폴더
```

## Custom Skills

Custom skills are stored in `skills/`.

- `game-lecture-builder`: Unity/C# 강의안, 실습, 과제, 피드백 제작
- `unity-client-review`: Unity 클라이언트 코드 리뷰와 성능/생명주기 점검
- `web-service-builder`: 웹페이지/웹서비스 제작, 검증, 배포 준비그리고 참고로 방금 확인해보니 현재 README는 제목만 들어 있는 상태였습니다. 위 내용을 넣고 커밋하면 다음 PC 세팅할 때 꽤 편해질 거예요.
