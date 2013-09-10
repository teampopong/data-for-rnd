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
    - [박인숙 의원](http://pokr.kr/person/194828)의 경우 sponsorship은 62건인데 반해, cosponsorship은 878건으로 다른 의원들 대비 공동발의를 많이 하는 것으로 드러남
    - 19대 국회 출범(2012년 5월 30일) 이후 한 번도 대표/공동발의하지 않은 의원은 총 2명 - [유성걸](http://pokr.kr/person/19571122), [안철수](http://pokr.kr/person/19621122)
    - 새누리당 이재영 ([경기도 평택시](http://pokr.kr/person/19561115), [경기도 김포시](http://pokr.kr/person/197515))는 동명이인으로, 정상집계되지 않음
