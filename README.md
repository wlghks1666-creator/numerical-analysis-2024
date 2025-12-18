Framingham 심혈관 질환 위험도 분석
📌 프로젝트 개요

본 프로젝트는 Framingham Heart Study 데이터셋을 활용하여
10년 이내 관상동맥 심장질환(CHD) 발생 위험 요인을 분석하는 것을 목표로 합니다.

연령, 성별, 흡연 여부, 고혈압, 당뇨병 등 주요 인구학적·임상적 변수들이
심혈관 질환 발생률에 어떤 영향을 미치는지 기초 통계 분석과 비교 분석을 통해 확인하였습니다.

📊 데이터셋 정보

출처: Framingham Heart Study

총 표본 수: 4,240명

남성: 1,820명

여성: 2,420명

타겟 변수

TenYearCHD

0: 10년 이내 심장질환 미발생

1: 10년 이내 심장질환 발생

주요 변수 설명
변수명	설명
age	나이
sex	성별
currentSmoker	현재 흡연 여부
cigsPerDay	하루 흡연량
BPMeds	혈압약 복용 여부
prevalentHyp	고혈압 여부
diabetes	당뇨병 여부
totChol	총 콜레스테롤
sysBP	수축기 혈압
diaBP	이완기 혈압
BMI	체질량지수
heartRate	심박수
glucose	혈당
🔍 수행한 분석

결측치 처리 및 데이터 정제

심장질환 발생률(%) 계산

흡연 여부별

성별

연령대별

고혈압 여부별

당뇨병 여부별

pandas.groupby()를 활용한 그룹별 평균 비교

🛠️ 사용 기술

google colab

pandas

numpy

matplotlib

📈 예시 코드
age_group_rate = (
    df.groupby("age_group", observed=True)["TenYearCHD"]
      .mean() * 100
)

📌 주요 결과

흡연자는 비흡연자에 비해 심장질환 발생률이 높게 나타남

연령이 증가할수록 심장질환 위험이 급격히 증가

고혈압 및 당뇨병은 심장질환 발생과 강한 상관관계를 보임

전체적으로 남성의 심장질환 발생 위험이 여성보다 높음

필요 라이브러리 설치

pip install pandas numpy matplotlib


분석 코드 실행

python analysis.py

📚 참고 자료

세계보건기구(WHO): 심혈관 질환 통계 자료

Framingham Heart Study 공개 데이터셋

👤 작성자 : 박지환
