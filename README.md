# Project Summary
> rnkakaomaps
React-native kakao-maps module for Android

- 개발기간
  + 기획 및 API 결정 / UI 디자인 / 이미지 선별 및 수정 / 기본세팅 및 프로젝트 구조, 라이브러리 설치 : 1일
  + 코드작성 : 3일
  + 테스트 및 리팩토링: 4일
  
- 특징 및 기능
  + 타입스크립트
  + 카카오맵을 React-Native에서 사용하기 위한 모듈
  + kakao-maps, Android library 사용하여 개발 (DaumMap SDK 1.4.1.0)
  + https://apis.map.kakao.com/download/android/sdk/Android_DaumMap_SDK_1.4.1.0.zip
  + 
 
- Project Common Dependencies

  [![React](https://img.shields.io/badge/React-v16.13.1-white?style=flat&labelColor=blue&logoColor=black&logo=react)](https://github.com/facebook/react)
[![RN](https://img.shields.io/badge/React--Native-v0.63.4-white?style=fla&labelColor=blue&logoColor=blackt&logo=react)](https://github.com/facebook/react-native)
[![Typescript](https://img.shields.io/badge/Typescript-v4.1.3-white?style=flat&labelColor=blue&logoColor=black&logo=typescript)](https://github.com/microsoft/TypeScript)

  [![DaumMap SDK](https://img.shields.io/badge/DaumMap--SDK-white?style=flat&labelColor=blue&logoColor=black&logo=weather)](https://apis.map.kakao.com/download/android/sdk/Android_DaumMap_SDK_1.4.1.0.zip)


</br></br></br>
***
## 시작 화면
![1_intro](https://user-images.githubusercontent.com/25360777/110412133-07a87c00-80cf-11eb-82d9-72a2712d8ee9.gif)
- [![DaumMap SDK](https://img.shields.io/badge/DaumMap--SDK-white?style=flat&labelColor=blue&logoColor=black&logo=weather)](https://apis.map.kakao.com/download/android/sdk/Android_DaumMap_SDK_1.4.1.0.zip)
- 기상청 API를 사용한 실시간 날씨 정보
- 
</br></br></br>
***

## 맵스타일 변환
![2_change_map_style](https://user-images.githubusercontent.com/25360777/110412143-0bd49980-80cf-11eb-958e-935e88168181.gif)
- 기상청 API를 사용한 실시간 날씨 정보
- 
</br></br></br>
***

## 맵 마커 클러스터링
- 클러스터링 화면   
![3_clustering](https://user-images.githubusercontent.com/25360777/110412149-0e36f380-80cf-11eb-86f3-c1dd9c0a68ff.gif)   

- 클러스터링 알고리즘   
![3-1_boundary_algorithum](https://user-images.githubusercontent.com/25360777/110412157-11ca7a80-80cf-11eb-9b99-a3d6679704ff.gif)   

- 상호작용   
![3-2_boundary_callout](https://user-images.githubusercontent.com/25360777/110412169-15f69800-80cf-11eb-8e73-a1c80afffc0d.gif)   

- 기상청 API를 사용한 실시간 날씨 정보
- 
</br></br></br>
***

## 맵마커 최적화
![4_boundary_loading](https://user-images.githubusercontent.com/25360777/110412175-18f18880-80cf-11eb-9267-59e2acafcb8b.gif)

</br></br></br>
***
## 기타 기능
![5_location_change](https://user-images.githubusercontent.com/25360777/110412185-1bec7900-80cf-11eb-93eb-1e2f18ea1573.gif)

</br></br></br>
***

## 후기 및 계획
- 달력기능 몇개 추가 (년,월 을 직접 선택을 위한 컨텍스트 메뉴 )
- 자동으로 사용자의 위치정보를 받아서 날씨 정보 업데이트 -> 디바이스 자원소비량 증가 (베터리 및 네트워크 사용량)
- 개선 : 수동버튼 처리 -> 사용자 동의사항 감소가 추가로 개선
- React Component 생명주기 개선 및 간단한 코드 리펙토링으로 UI 성능향상.
- 다음 프로젝트를 위한 분석데이터 준비해야 할듯.
