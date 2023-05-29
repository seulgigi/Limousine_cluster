## 🚦 교통약자를 위한 서울시 내 보행신호 자동연장시스템 입지 추천 🚦

### 분석배경
전체 보행사망자 중 교통약자가 차지하는 비율이 증가하면서 **교통약자의 보행사고 위험도를 줄이는 정책이 필요** <br>

**보행신호 자동연장시스템** <br>
: 보행자를 검지 및 추적하는 기술을 적용해 주어진 보행신호시간 동안 횡단을 완료하지 못하는 보행자 즉, 교통약자들의 안전횡단을 지원해주는 일련의 장치로 허용된 시간 범위 내에서 보행신호시간을 자동으로 연장해주는 시스템 <br> <br>

### 분석 프로세스
**집단별 데이터 분류 및 변수 선정** <br>
1) 노인 - 노인 생활인구와 노인 거주인구간 상관관계 파악 <br>
`사회복지시설 중 노인 관련 시설 수, 노인 교통사고건수, 의료기관 수, 유통업체 수`
2) 어린이 - 행정동별 어린이 수 파악 <br>
`어린이 교육시설 수, 어린이 교통사고건수, 유통업체 수`
4) 장애인 - 보행 취약 장애인 지수 선정 <br>
`사회복지시설 중 장애인 관련 시설 수, 의료기관 수, 유통업체 수` <br>
-> 각 특이변수 활용해 보행연장시스템 필요성이 높은 행정동을 선정
<br> <br>

### 데이터 전처리
선정한 변수를 활용해 노인, 어린이, 장애인 각각의 데이터를 군집분석 시행 <br>
**K-means**
- 특정 행정동을 선택해야 하므로 hard clustering 방법이 적합하다 판단
- 초기값 선정이 덜함
- 비교적으로 간편한 군집 분석 방법 <br><br>

### 데이터 분석
Elobow 기법 활용 : K의 값을 구함. 해당 값으로 clustering 진행
1) 노인
  - 노인생활인구-노인관련사회복지시설
  - 노인생활인구-노인교통사고
  - 노인생활인구-의료기관수
  - 노인생활인구-유통업체수
2) 어린이
  - 어린이인구수-어린이교육시설수
  - 어린이인구수-어린이교통사고수
  - 어린이인구수-유통업체수
3) 장애인
  - 보행취약장애인지수-시설수
  - 보행취약장애인지수-의료기관수
  - 보행취약장애인지수-유통업체수 <br>
**한 번의 클러스터로 군집을 뽑아낼 수 없는 경우 2차 클러스터 진행** <br><br>

### 분석 결과
계층적 군집분석 결과를 합산
1번 기준: 행정동별 클러스터링 결과 Target Cluster에 도출된 횟수 list-up <br>
2번 기준: 서로 다른 3가지 교통약자 계층 중, 행정동별 발생빈도 list-up <br>
=> 2번 기준 상위권 중 1번 기준 상위 rank에 속한 행정동을 target으로 선정 `길음1동 상계6,7동` <br><br>

### 기대효과
- 취약계층 복지 증대
- 지역주민 생활편의 제공
- 공공활용성 및 실현가능성 <br><br>

### 활용방안
- 2030 서울 미래상 활용 가능성
- 경찰청 보행신호 자동연장시스템 표준규격/운영 매뉴얼 활용 가능성 <br><br>

### 한계점
- 교통사고수 데이터가 행정동 단위가 아닌 법정동 단위라 이에 행정동 단위 대입을 위해 특정 법정동에 해당하는 값을 동일하게 적용
- 관련 데이터 시점이 상이해 동일한 시점으로 적용할 시 다른 결과 도출 가능성이 있음
- 보행신호 자동 연장으로 인한 신호 정체 및 교통체증에 대한 대안책이 부족함<br><br>

### 👩‍👩‍👧‍👦 팀원
홍준기(팀장), 박민영, 정은정, 류슬기
