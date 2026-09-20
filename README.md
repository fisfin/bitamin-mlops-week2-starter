# BITAmin MLOps 2주차 시작 코드

참가자용 발표자료를 보며 진행하는 Git/GitHub 협업 실습입니다. 사전 ZIP이나 역할 카드 없이 수업 중 이 템플릿으로 조별 저장소를 만듭니다. 구체적인 실습 순서와 역할별 코드는 최신 참가자용 발표자료를 기준으로 합니다.

## 시작 환경

1. **VS Code**를 실행하고 상단 **Terminal(터미널) → New Terminal(새 터미널)**을 선택합니다.
2. 터미널 오른쪽 **+ 옆 ▼ → Select Default Profile**에서 **Windows는 PowerShell**, **macOS는 zsh**를 선택합니다. 휴지통 버튼으로 기존 터미널을 닫고 **+**로 새 터미널을 엽니다.
3. 웹 브라우저에서 GitHub에 본인 계정으로 로그인합니다. 사전세팅에서 Git 설치와 작성자 이름·이메일 설정을 마쳤다면 다시 설정할 필요는 없습니다.

명령은 **VS Code 내장 터미널**에 입력합니다. 파일은 왼쪽 **Explorer(탐색기)**에서 열어 편집하고, Windows는 **Ctrl+S**, macOS는 **⌘S**로 저장합니다. GitHub 조작은 웹 브라우저, PDF·사진 복사는 Windows **파일 탐색기** 또는 macOS **Finder**에서 합니다.

push 인증이 필요하면 발표자료의 **‘첫 git push 때 GitHub 인증’**을 참고합니다. Username / Password 질문이나 인증·작성자 오류는 **‘도움말 · push 인증과 오류’**를 참고합니다. GitHub 웹사이트 로그인과 터미널의 Git 인증은 별개입니다.

## 수업 중 조별 저장소 생성

조장 한 명이 **Use this template → Create a new repository**를 누릅니다. Owner는 조장, 이름은 `bitamin-mlops-조번호`, 공개 범위는 Public으로 정합니다. Include all branches는 끄고 Create repository를 누릅니다.

Settings → Collaborators → Add people에서 조원을 초대하고, 조원은 본인 계정으로 초대를 수락합니다. 전원은 생성된 조별 저장소의 **Code → Local → HTTPS** 주소를 복사합니다.

VS Code 내장 터미널에서 아래 명령을 **한 줄씩 입력하고 Enter**를 누릅니다. Windows PowerShell과 macOS zsh에서 같습니다.

```text
cd ~
git clone https://github.com/OWNER/bitamin-mlops-TEAM.git
cd bitamin-mlops-TEAM
pwd
```

`git clone` 뒤 주소는 복사한 조별 저장소 주소로 바꿉니다. OWNER는 조장 GitHub ID, TEAM은 실제 조 번호입니다.

VS Code의 **File(파일) → Open Folder(폴더 열기)**에서 `pwd`로 확인한 폴더를 엽니다. **Terminal → New Terminal**을 열고 왼쪽 Explorer에 `app.py`, `requirements.txt`, `week1`, `week2`가 보이는지 확인합니다. 이후 파일 편집과 명령은 이 **조별 폴더(app.py가 있는 저장소 루트)**에서 진행합니다.

## week1에는 지난주 제출 PDF

조장은 VS Code Explorer의 **week1 폴더 우클릭 → Windows: Reveal in File Explorer / macOS: Reveal in Finder**를 선택합니다. 열린 파일 관리자에서 **week1 폴더 안으로 들어가** 지난주 제출 PDF를 복사합니다. 자세한 순서는 [week1 안내](week1/README.md)를 참고합니다.

개인별 제출이었다면 조원들의 기존 PDF를 모으고, 조별 제출이었다면 조별 PDF 한 개를 넣습니다. 같은 파일명은 이름을 붙여 구분합니다. 복사한 PDF를 더블클릭해 실제 내용을 확인합니다. README에 이미 제출한 내용을 다시 작성할 필요는 없습니다.

루트 `app.py`는 이번 주 시작 코드입니다. 기존 1주차 `app.py`를 복사해 덮어쓰지 않습니다.

조장은 발표자료의 **‘.gitignore 파일 작성’ → ‘.gitignore 작동 확인’ → ‘공통 시작 상태 push’** 순서로 진행합니다. `.gitignore`는 VS Code에서 루트에 생성하고, 실제 PDF와 함께 commit·push합니다.

## 코드 실행과 협업

코드 담당 A~D는 발표자료의 **‘기존 Python부터 확인’ → ‘가상환경 생성과 활성화’** 안내에 따라 Python 3.10~3.13 중 사용 가능한 버전을 확인하고 `.venv`를 생성·활성화합니다.

터미널 앞의 **(.venv)** 표시와 Python 실행 경로를 확인한 뒤, 같은 VS Code 터미널에서 아래 명령을 **한 줄씩 입력**합니다. 가상환경이 활성화되어 있으면 두 OS 모두 `python`을 사용합니다.

```text
python -m pip install -r requirements.txt
python app.py
```

새 터미널은 **‘도움말 · 터미널과 폴더 복구’**에서 다시 활성화합니다. Windows에서 활성화가 차단되면 **‘도움말 · Python 환경 오류’**의 대체 명령을 사용합니다.

현재 코드는 Logistic Regression 한 개와 accuracy, f1을 출력합니다. A 전처리, B Logistic Regression, C Random Forest, D 평가 지표 담당은 **같은 시작 commit**에서 각각 branch를 만듭니다. 필요한 변경 코드는 발표자료의 각 역할별 코드 수정 단계에 있습니다.

A~D의 PR 4개와 리뷰가 준비되면 A → D → B 순으로 merge하고, C의 충돌을 해결한 뒤 C의 PR을 merge합니다. 최종 코드는 두 모델과 다섯 지표를 출력합니다.

5인 조의 문서 담당은 공통 Git 준비와 타인 PR 리뷰 1건을 수행하고, A~D의 최종 main 확인이 끝나면 **‘실습 증거 모으기’ → ‘문서 PR과 최종 제출’**을 진행합니다. 문서 담당이 자료 정리·push·PR 생성·merge를 맡고, 조장은 문서 PR을 확인합니다. 4인 조는 A~D 중 한 명이 문서를 겸임합니다.

`week2/README.md`는 **체크포인트 제목과 실제 캡처 사진 7장**으로 정리합니다. 이미지 경로가 이미 있으므로 `week2/images`에 발표자료의 **‘도움말 · 화면 캡처와 파일명’**과 같은 이름으로 사진을 넣고, **‘도움말 · README 이미지 확인’**에서 표시 여부를 확인합니다. 별도의 PR·리뷰 링크 목록이나 장문 보고서는 요구하지 않습니다.

## 출처

- 완성 코드: https://github.com/Bo0sung/bitamin-mlops-2-snapshot/tree/1caa97f51e38bf2e71e534dca992adfca4bbbf97
- 데이터(원본 저장소 안내): https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data
- 시작 코드는 완성본에서 역할별 변경을 되돌려 구성했습니다. 수행 완료 증거나 정답 branch는 포함하지 않습니다.
