# BITAmin MLOps 2주차 시작 코드

발표자료를 보면서 진행하는 Git/GitHub 협업 실습용 시작 코드입니다.

## 수업 중 시작하기

조장 한 명이 **Use this template → Create a new repository**에서
`bitamin-mlops-조번호`를 만들고 조원을 초대합니다. `Include all branches`는 선택하지 않습니다.
전원은 자신의 조별 repository를 clone합니다. 필요한 명령과 수정 코드는 발표자료에 모두 있습니다.

현재 app.py는 Logistic Regression 한 개와 accuracy, f1을 출력합니다.
문서 문자열은 최종 목표를 설명합니다. 네 역할의 변경과 PR·리뷰·충돌 해결을 거쳐 완성합니다.

```bash
conda activate mlops-week1
python -m pip install -r requirements.txt
python app.py
```

`.gitignore`는 발표자료를 보며 조장이 작성합니다.
`week1/`에는 자신의 실제 1주차 결과물을 보존하고, `week2/`에는 본인 조의 실습 증거를 기록합니다.
이 시작 상태에는 수행 완료 증거와 정답 branch를 포함하지 않습니다.

## 출처

- 완성 코드 기준: https://github.com/Bo0sung/bitamin-mlops-2-snapshot/tree/1caa97f51e38bf2e71e534dca992adfca4bbbf97
- 데이터 출처(원본 저장소 안내): https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data
- 시작 코드는 위 완성본에서 실습용 변경을 되돌려 구성했습니다.
