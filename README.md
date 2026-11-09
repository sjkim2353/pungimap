# **PungiMap**

<br>

## 풍이맵 안내

해당 페이지는 풍덕동 행정 업무 지원을 목표로 작성한 맞춤형 지도 정보 제공 사이트입니다.

코드 작성에는 오픈소스로 공개되어 있는 행정동 경계 자료와 KAKAO Maps API 유틸을 사용했습니다.

- 행정동 경계 자료: HangJeongDong_ver20261001.geojson Seungbum KIM. (2026). admdongkor. GitHub. https://github.com/vuski/admdongkor/tree/master.
- 카카오 지도 API: Kakao Developers. https://developers.kakao.com.

<br>

## 라이브러리 안내

웹페이지 구성에 사용된 자료는 아래와 같습니다.

### data

- suncheon_dong.geojson: HangJeongDong_ver20261001.geojson 파일에서 순천시 읍·면·동 경계 정보만을 추출한 자료
- poi.json: 주요 관심 지역(Point of Interests) 정보
- poc.json: 민원 다발 지역(Point of Complaints) 정보

### images

- pungi*.jpg, pungi*.png: 풍덕동 마스코트 풍이 이미지 파일
- tunaroundview: 로드뷰 아이콘(카카오맵 동동이 대체) 활용 이미지 파일, 회전 각도 별 16개 이미지로 구성
- background.png: 웹 페이지 기본 배경 이미지

<br>

## 주요 기능

1. 지도 생성 중심점: 풍덕동 행정복지센터(전남광주통합특별시 순천시 풍덕1길 40)
2. 주소 검색
    - kakao.maps.services.places.keywordSearch() 매서드 활용
    - 왼쪽 검색 목록에서 원하는 장소 또는 주소를 검색
    - 지도 중심점 기준 반경 5km 이내에서만 키워드 검색 수행
    - 이후 검색 또는 드래그를 통해 지도 위치가 변경되면 중심 좌표도 변경
    - 검색 후 원하는 장소를 선택하면 지도에 마커로 표시, 생성된 마커는 지도 관련 기능의 기준점이 됨
3. 로드뷰
    - 주소 검색으로 생성한 마커 또는 지도에서 선택한 지점을 시작점으로 로드뷰 기능 활성화
    - 지도 좌측 상단의 버튼을 통해 On/Off
4. 지도 레이어
    - 풍덕동 또는 인근 지역 복지관, 관공서, 은행의 위치 정보를 마커로 표시
    - 행정구역 경계: 순천시 읍·면·동 경계 정보를 지도에 표시, 지도에서 선택한 지점의 행정동 영역은 강조 처리
    - 민원 다발 지역: 민원 다발 지역 위치를 지도에 표시, 활성화 시 관련 정보 목록 생성
