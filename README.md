# BITAmin MLOps 2주차 시작 코드

참가자용 발표자료를 보며 진행하는 Git/GitHub 협업 실습입니다. 사전 ZIP이나 역할 카드 없이 수업 중 이 템플릿으로 조별 저장소를 만듭니다.

## 시작 환경

1. Windows **시작 버튼**에서 **Ubuntu**를 검색해 실행합니다. Windows Terminal의 Ubuntu 탭도 됩니다.
2. 지난주 환경을 활성화합니다: `conda activate mlops-week1`.
3. Chrome/Edge에서 GitHub에 본인 계정으로 로그인합니다.

명령은 **WSL Ubuntu 터미널**, GitHub 조작은 **웹 브라우저**, PDF 복사는 **Windows 파일 탐색기**에서 합니다. VS Code는 필요 없습니다. 파일 편집은 `nano -I -l 파일명`을 사용합니다. Ctrl+O, Enter로 저장하고 Ctrl+X로 종료합니다. 참가자 PDF 31~37쪽에 조작 방법이 있습니다.

`gh` 설치·재로그인은 필수 절차가 아닙니다. clone/push 인증에 문제가 생긴 사람만 발표자료 2·36쪽의 해당 복구를 진행합니다. commit 작성자 오류는 이름·이메일 설정으로 따로 해결합니다.

## 수업 중 조별 저장소 생성

조장 한 명이 **Use this template → Create a new repository**를 누릅니다. Owner는 조장, 이름은 `bitamin-mlops-조번호`, 공개 범위는 Public으로 정합니다. Include all branches는 끄고 Create repository를 누릅니다.
Settings → Collaborators → Add people에서 조원을 초대하고, 조원은 본인 계정으로 초대를 수락합니다.
전원은 생성된 조별 저장소의 Code → HTTPS 주소를 복사해 clone합니다.

```bash
cd ~
git clone https://github.com/OWNER/bitamin-mlops-TEAM.git
cd bitamin-mlops-TEAM
```

OWNER는 조장 GitHub ID, TEAM은 실제 조 번호로 바꿉니다. 이후 명령은 이 **조별 폴더(app.py가 있는 저장소 루트)**에서 실행합니다.

## week1에는 지난주 제출 PDF

조장은 Ubuntu의 조별 폴더에서 `mkdir -p week1`, `explorer.exe week1`을 실행합니다.
Win+E로 원본 제출 PDF가 있는 폴더를 열어 파일을 복사(Ctrl+C)하고, 열린 week1 창에 붙여넣습니다(Ctrl+V).
개인별 제출이었다면 조원들의 기존 PDF를 모으고, 조별 제출이었다면 조별 PDF 한 개를 넣습니다. 같은 파일명은 이름을 붙여 구분합니다.
PDF를 더블클릭해 열어 확인합니다. README에 이미 제출한 내용을 다시 작성할 필요는 없습니다.

루트 app.py는 이번 주 시작 코드입니다. 기존 1주차 app.py를 복사해 덮어쓰지 않습니다.
`.gitignore`는 발표자료 7쪽의 전체 명령으로 조장이 직접 생성합니다. 이후 발표자료 8쪽에서 두 준비물을 commit·push합니다.

## 코드 실행과 협업

```bash
python -m pip install -r requirements.txt
python app.py
```

현재 코드는 LR 한 개와 accuracy, f1을 출력합니다. A 전처리, B LR, C RF, D 평가 역할이 같은 시작 commit에서 branch를 만듭니다.
필요한 함수 코드는 발표자료 12~15쪽에 있습니다. 각자 PR·타인 리뷰를 제출하고 A, D, B 순으로 merge한 뒤 C의 충돌을 해결합니다.
최종 코드는 LR·RF와 다섯 지표를 출력합니다. `week2/README.md`는 실제 PR·리뷰 링크와 캡처로 채웁니다.

## 출처

- 완성 코드: https://github.com/Bo0sung/bitamin-mlops-2-snapshot/tree/1caa97f51e38bf2e71e534dca992adfca4bbbf97
- 데이터(원본 저장소 안내): https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data
- 시작 코드는 완성본에서 역할별 변경을 되돌려 구성했습니다. 수행 완료 증거나 정답 branch는 포함하지 않습니다.
