# Data for Political R&D

이 저장소에 있는 데이터는 [중앙선거관리위원회](http://www.nec.go.kr)과 [국회 의안정보시스템](http://likms.assembly.go.kr/bill/)에서 데이터를 수집하여 후처리한 것입니다. (일부 열려라 국회에서 수집)
개발 및 연구의 편의를 위해 공개하니 널리 이용해주시기 바라며 문의사항, 제안사항 또는 오류가 있는 경우 [이슈제기](https://github.com/teampopong/data-for-rnd/issues)를 해주시기 바랍니다.

데이터 수집에 이용된 코드는 [이 곳](https://github.com/teampopong/crawlers)에서 보실 수 있습니다.


## Overview
<table>
<thead>
    <tr>
        <th>Filename</th>
        <th>Description</th>
        <th>Source</th>
        <th>Created date</th>
    </tr>
</thead>
<tbody>
    <tr>
        <th>candidacies.csv</th>
        <td>1-19대 국회의원 선거 후보자 데이터</td>
        <td>중앙선거관리위원회</td>
        <td>2013-04-24</td>
    </tr>
    <tr>
        <th>cosponsorship.csv</th>
        <td>19대 국회의 대표/공동발의 횟수 데이터</td>
        <td>국회 의안정보시스템</td>
        <td>2013-07-29</td>
    </tr>
    <tr>
        <th>migrations.csv</th>
        <td>19대 국회의원의 정당 이동 데이터</td>
        <td>열려라국회</td>
        <td>2012-09-09</td>
    </tr>
    <tr>
        <th>pledges.csv</th>
        <td>19대 국회의원 후보 공약 데이터</td>
        <td>중앙선거관리위원회</td>
        <td>2013-04-24</td>
    </tr>
</tbody>
</table>

## Description
### 공통변수
- `candidacy_id`: 후보등록 고유번호. 한 인물이 복수출마할 경우 두 개 이상의 값을 가짐.
- `person_id`: 인물 고유번호. 성명 및 생년이 같은 경우 동일 인물로 판단하고 ID는 생년 + 랜덤 숫자로 생성.
- `name`: 인물의 한글 성명. 동명이인이 있을 수 있음.

### candidacies.csv
- 8 columns, 19184 rows (on 12913 unique `person_id`)
- 변수설명
    <table>
        <tr><td>candidacy_id</td><td>person_id</td><td>name</td><td>birthday</td><td>party</td><td>assembly_id</td><td>is_elected</td><td>district</td></tr>
        <tr><td>9914</td><td>19581139</td><td>이태희</td><td>19581209</td><td>한나라당(2012)</td><td>19</td><td>f</td><td>{비례대표}</td></tr>
        <tr><td>9915</td><td>19581139</td><td>이태희</td><td>19581209</td><td>무소속</td><td>15</td><td>f</td><td>"{서울특별시,광진구,갑}"</td></tr>
        <tr><td>19186</td><td>19551154</td><td>김창근</td><td>19550507</td><td>통합진보당</td><td>19</td><td>f</td><td>"{대전광역시,대덕구}"</td></tr>
    </table>

    - `birthday`: 출마 당시 후보자가 기재한 생년월일(YYmmdd). 예전 국회(1-10대)의 경우 데이터가 부정확한 경우가 있다고 보고됨.
    - `party`: 출마 당시 후보자의 소속 정당.
    - `assembly_id`: 출마 국회의원 선거 대수.
    - `is_elected`: 해당 선거의 당선 여부.
    - `district`: 출마 당시 지역구 데이터. 각 지역명은 쉼표로 분리

- 특이사항
    - 2013년 상반기 재보궐선거 (4월 24일) 데이터 포함.
    - 동명의 정당 '한나라당'은 '한나라당'과 '한나라당 (2012)'로 구분하여 표기.
    - 동명의 정당 '청년당'은 분리하여 표기되지 않음.

### cosponsorship.csv
- 7 columns, 304 rows
- 변수설명
    <table>
        <tr><td>person_id</td><td>name</td><td>gender</td><td>party</td><td>assembly_id</td><td>sponsorship</td><td>cosponsorship</td></tr>
        <tr><td>1950197</td><td>배기운</td><td>m</td><td>민주통합당</td><td>19</td><td>36</td><td>1484</td></tr>
        <tr><td>194828</td><td>박인숙</td><td>f</td><td>새누리당</td><td>19</td><td>62</td><td>878</td></tr>
        <tr><td>19521138</td><td>김성곤</td><td>m</td><td>민주통합당</td><td>19</td><td>31</td><td>835</td></tr>
    </table>

    - `gender`: 의원의 성별.
    - `party`: 출마 당시 후보자의 소속 정당.
    - `assembly_id`: 국회의원 선거 대수. 이 데이터셋에서는 전체가 19.
    - `sponsorship`: 19대 국회에서 의안을 대표발의한 횟수.
    - `cosponsorship`19대 국회에서 의안을 찬성발의하거나 공동발의한 횟수.

- 특이사항
    - 이재영 ([새누리당, 경기도 평택시](http://pokr.kr/person/19561115) / [새누리당, 경기도 김포시](http://pokr.kr/person/197515)), 김영주 ([민주당, 서울특별시 영등포구](http://pokr.kr/person/195526) / [새누리당, 비례대표](http://pokr.kr/person/19541125)) 의원은 동명이인으로 집계 수치가 정확하지 않을 수 있음.
    - [유성걸](http://pokr.kr/person/19571122) 의원은 선관위에 '유성걸', 국회에는 '류성걸'으로 등록되어 있음.

### migration.csv

- 5 columns, 786 rows
- 변수설명
    <table>
        <tr><td>person_id</td><td>name</td><td>party</td><td>start_date</td><td>end_date</td></tr>
        <tr><td>19461137</td><td>주영순</td><td>새누리당</td><td></td><td>2012-04</td></tr>
        <tr><td>19601167</td><td>강기윤</td><td>새누리당</td><td></td><td>2012-04</td></tr>
        <tr><td>19521135</td><td>한기호</td><td>한나라당</td><td>2012-02</td><td>2010-07</td></tr>
    </table>

- 특이사항
    - `start_date` 또는 `end_date`가 null인 경우가 있음.

### pledges.csv

- 3 columns, 1221 rows (on 246 unique `candidate_id`)
- 변수설명
    <table>
        <tr><td>candidacy_id</td><td>name</td><td>pledge</td></tr>
        <tr><td>7643</td><td>강창희</td><td>안영동 스포츠과학단지 조성</td></tr>
        <tr><td>7643</td><td>강창희</td><td>중앙로 문화예술 지구 명소화</td></tr>
        <tr><td>7643</td><td>강창희</td><td>도청이전부지 대전시로 소유 이전 및 부지활용</td></tr>
    </table>

- 특이사항
    - 2013년 상반기 재보궐선거 (4월 24일) 데이터 포함.
    - 인당 약 5개의 대표 공약이 있음.


## Showcase

이 데이터셋을 이용해 아래와 같은 서비스가 만들어졌습니다.
(당신의 서비스 또는 연구도 자랑해주세요!)

- 2013-10-30 안드로이드 앱 "[지켜본다](https://play.google.com/store/apps/details?id=org.sicamp.isee)"

## License

이 저장소에 공개된 데이터는 [크리에이티브 커먼즈 저작자표시 3.0 Unported](http://creativecommons.org/licenses/by/3.0/deed.ko) 라이선스에 따라 이용하실 수 있습니다. (즉, 팀포퐁이 데이터의 저작자임을 명시하기만 하면 수정, 배포를 마음껏 하실 수 있습니다.)


<a rel="license" href="http://creativecommons.org/licenses/by/3.0/deed.ko"><img alt="크리에이티브 커먼즈 라이선스" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/88x31.png" /></a>
