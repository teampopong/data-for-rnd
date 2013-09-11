# Data for Political R&D

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
        <td>cosponsorship.csv</td>
        <td>19대 국회의 대표/공동발의 횟수 데이터</td>
        <td>person_id, name, gender, party, assembly_id, sponsorship, cosponsorship</td>
        <td>popongdb</td>
        <td>2013-07-29</td>
    </tr>
    <tr>
        <td>migrations.csv</td>
        <td>19대 국회의원의 정당 이동 데이터</td>
        <td>person_id, name, party, start_date, end_date</td>
        <td>열려라국회</td>
        <td>2012-09-09</td>
    </tr>
</tbody>
</table>

## Comments
### cosponsorship.csv
- 변수설명
    - `sponsorship`: 19대 국회에서 의안을 대표발의한 횟수
    - `cosponsorship`19대 국회에서 의안을 찬성발의하거나 공동발의한 횟수
- 특이사항 (2013년 7월 29일까지 유효)
    - `sponsorship`과 `cosponsorshop`의 상관계수는 약 0.6
    - 이재영 ([새누리당, 경기도 평택시](http://pokr.kr/person/19561115) / [새누리당, 경기도 김포시](http://pokr.kr/person/197515)), 김영주 ([민주당, 서울특별시 영등포구](http://pokr.kr/person/195526) / [새누리당, 비례대표](http://pokr.kr/person/19541125)) 의원은 동명이인으로, 정상집계되지 않음
    - [유성걸](http://pokr.kr/person/19571122) 의원은 이름이 선관위에는 '유성걸', 국회에는 '류성걸'으로 등록되어 있어, 이름이 서로 달라 정상집계되지 않음.
