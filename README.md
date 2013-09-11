# Data for Political R&D

이 저장소에 공개된 데이터는 [크리에이티브 커먼즈 저작자표시 3.0 Unported](http://creativecommons.org/licenses/by/3.0/deed.ko) 라이선스에 따라 이용하실 수 있습니다.<br>
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/deed.ko"><img alt="크리에이티브 커먼즈 라이선스" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/88x31.png" /></a>

## Overview
<table>
<thead>
    <tr>
        <td>Filename</td>
        <td>Description</td>
        <td>Variables</td>
        <td>Source</td>
        <td>Created date</td>
    </tr>
</thead>
<tbody>
    <tr>
        <td>candidacies.csv</td>
        <td>19대 국회의원 출마/당선 데이터</td>
        <td>candidacy&#95;id, person&#95;id, name, birthday, party, assembly&#95;id, is&#95;elected, district</td>
        <td>popongdb</td>
        <td>2012-04-11</td>
    </tr>
    <tr>
        <td>cosponsorship.csv</td>
        <td>19대 국회의 대표/공동발의 횟수 데이터</td>
        <td>person&#95;id, name, gender, party, assembly&#95;id, sponsorship, cosponsorship</td>
        <td>popongdb</td>
        <td>2013-07-29</td>
    </tr>
    <tr>
        <td>migrations.csv</td>
        <td>19대 국회의원의 정당 이동 데이터</td>
        <td>person&#95;id, name, party, start&#95;date, end&#95;date</td>
        <td>열려라국회</td>
        <td>2012-09-09</td>
    </tr>
    <tr>
        <td>pledges.csv</td>
        <td>19대 총선 공약 데이터</td>
        <td>candidacy&#95;id, name, pledge</td>
        <td>popongdb</td>
        <td>2012-04-11</td>
    </tr>
</tbody>
</table>

## Comments
### candidacies.csv
- 변수설명
    - `candidacy_id`: 출마 레코드 ID. `pledges.csv`와 결합(join)하기 위해 필요
- 특이사항
    - 2013년 상반기 재보궐선거 데이터 포함

### cosponsorship.csv
- 변수설명
    - `sponsorship`: 19대 국회에서 의안을 대표발의한 횟수
    - `cosponsorship`19대 국회에서 의안을 찬성발의하거나 공동발의한 횟수
- 특이사항 (2013년 7월 29일까지 유효)
    - `sponsorship`과 `cosponsorshop`의 상관계수는 약 0.6
    - 이재영 ([새누리당, 경기도 평택시](http://pokr.kr/person/19561115) / [새누리당, 경기도 김포시](http://pokr.kr/person/197515)), 김영주 ([민주당, 서울특별시 영등포구](http://pokr.kr/person/195526) / [새누리당, 비례대표](http://pokr.kr/person/19541125)) 의원은 동명이인으로, 정상집계되지 않음
    - [유성걸](http://pokr.kr/person/19571122) 의원은 이름이 선관위에는 '유성걸', 국회에는 '류성걸'으로 등록되어 있어, 이름이 서로 달라 정상집계되지 않음.
