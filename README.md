# Project Summary
> rnkakaomaps
React-native kakao-maps module for Android

- 개발기간
  + 기획 및 API 결정 / UI 디자인 / 이미지 선별 및 수정 / 기본세팅 및 프로젝트 구조, 라이브러리 설치 : 1일
  + 코드작성 : 3일
  + 테스트 및 리팩토링: 3일
  
- 특징 및 기능  
  + 카카오맵을 React-Native에서 사용하기 위한 모듈
  + DaumMap SDK 1.4.1.0 , 카카오맵 안드로이드 API를 사용하여 개발
  + https://apis.map.kakao.com/download/android/sdk/Android_DaumMap_SDK_1.4.1.0.zip
  + 클러스터링 기능을 커스텀으로 개발 (k-means 알고리즘 사용, 효율을 위해 안드로이드단에서 개발)
  + 타입스크립트
 
- Project Common Dependencies

  [![React](https://img.shields.io/badge/React-v16.13.1-white?style=flat&labelColor=blue&logoColor=black&logo=react)](https://github.com/facebook/react)
[![RN](https://img.shields.io/badge/React--Native-v0.63.4-white?style=fla&labelColor=blue&logoColor=blackt&logo=react)](https://github.com/facebook/react-native)
[![Typescript](https://img.shields.io/badge/Typescript-v4.1.3-white?style=flat&labelColor=blue&logoColor=black&logo=typescript)](https://github.com/microsoft/TypeScript)
[![DaumMap SDK](https://img.shields.io/badge/kakaoMaps--Android--SDK-v1.4.1.0-white?style=flat&labelColor=blue&logoColor=black&logo=weather)](https://apis.map.kakao.com/download/android/sdk/Android_DaumMap_SDK_1.4.1.0.zip)


</br></br></br>
***
## 시작 화면
![1_intro](https://user-images.githubusercontent.com/25360777/110412133-07a87c00-80cf-11eb-82d9-72a2712d8ee9.gif)
- [![DaumMap SDK](https://img.shields.io/badge/DaumMap--SDK-white?style=flat&labelColor=blue&logoColor=black&logo=weather)](https://apis.map.kakao.com/download/android/sdk/Android_DaumMap_SDK_1.4.1.0.zip)
- 성능모니터상 안드로이드 에뮬레이터에서도 쾌적하게 동작
- 안드로이드 에뮬레이터에서 실행 후 뷰까지 12초, 리액트 네이티브 자체 로드가 빠른편이 아니기 때문에 큰 문제는 없다고 생각. (실기에서는 디바이스 성능에 따라 다를듯)

</br></br></br>
***

## 맵스타일 변환
![2_change_map_style](https://user-images.githubusercontent.com/25360777/110412143-0bd49980-80cf-11eb-958e-935e88168181.gif)
- sdk에서 제공하는 맵스타일 변화 기능을 리액트 네이티브 단에서 처리

</br></br></br>
***

## 맵 마커 클러스터링
+ 클러스터링 화면 (완성 화면)  
![3_clustering](https://user-images.githubusercontent.com/25360777/110412149-0e36f380-80cf-11eb-86f3-c1dd9c0a68ff.gif)   
- K-Means 알고리즘을 적용하여 개발
- 화면의 중점이나, 확대/축소값이 변경 되었을 경우 처리가 되도록 개발
- 집단의 크기별 마커이미지 차이를 두고, 선택시 몇개의 마커가 존재하는지 표시함.
- 문제점 1: 내장 MapCircle 를 활용하여 최적화처리를 시도 하였으나, MapCIrcle이 정상적으로 표시되지 않음, 
- 해결 1: png 이미지로 크기별 커스텀 마커를 제작.
- 문제점 2: 마커 선택시 기본마커와 말풍선으로 변경됨
- 해결 2: Time solves

+ 클러스터링 알고리즘 (개발중 테스트 화면)  
![3-1_boundary_algorithum](https://user-images.githubusercontent.com/25360777/110412157-11ca7a80-80cf-11eb-9b99-a3d6679704ff.gif)   
- 화면상의 5점의 무게중심(Centroid)을 선택하여 중심과 가까운 마커들의 좌표끼리 군집화 처리
- 문제점 : 중점과 상대적 먼거리에 마커들이 모여 있을 경우 무게중심과 큰 차이가 발생.
- 개선 : 바운더리API를 사용하여 현재 화면상의 마커들의 위치들 중에서 랜덤하게 무게중심을 선택하는 것으로 변경.
- 유클리드 거리 / 맨하튼 거리 둘다 테스트 한 결과 공식의 복잡도에 비해 차이가 크게 없음. 표본수(365개)가 너무 작아서 그런듯

+ 상호작용   
![3-2_boundary_callout](https://user-images.githubusercontent.com/25360777/110412169-15f69800-80cf-11eb-8e73-a1c80afffc0d.gif)   
- 몇개의 위치들이 존재하는지 표시

</br></br></br>
***

## 맵마커 최적화
![4_boundary_loading](https://user-images.githubusercontent.com/25360777/110412175-18f18880-80cf-11eb-9267-59e2acafcb8b.gif)
- getMapPointBounds() + getPOIItems() 조합으로 개발
- 화면상의 바운더리를 값을 마커 좌표와 비교하여 해당 마커만 표시하도록 처리

</br></br></br>
***
## 기타 기능
![5_location_change](https://user-images.githubusercontent.com/25360777/110412185-1bec7900-80cf-11eb-93eb-1e2f18ea1573.gif)
- 리액트네이티브단과 상호작용 이벤트 처리
- 지정 장소로 위치 이동
- 중앙값 , 확대/축소 값 공유
   
</br></br></br>
***

## 참고문서
+ https://apis.map.kakao.com/android/
+ https://en.wikipedia.org/wiki/K-means_clustering
+ https://github.com/asata/react-native-daummap

## 후기 및 계획
+ 딜레이 및 깜빡임 현상은 실기에서는 나타나지 않음.
+ 리액트 네이티브 Socket.io 모듈 개발 이후 오랜만에 네이티브 모듈개발
+ 리액트 네이티브에서 사용하기 위한 맵 모듈 검색 중, 카카오맵 모듈은 없어서 개발.
+ 개발해보니 카카오맵 안드로이드 SDK는 2019년 버젼을 사용하고 있음. (react-native-daummap이 업데이트가 없는 이유인듯)
+ jniLibs 폴더는 android/app/main/src/main/ 에 복붙헤야 함. (공식문서와 다름)
+ 안드로이드 에뮬레이터에서 실행시 *.so 라이브러리 찾을 수 없다는 에러발생
- 원인 : 현재 daumMap SDK는 x86, x64를 지원하지 않음. (실기에서는 동작하는 이유)
- 해결 : build.gradle 빌드시 ndk.abiFilters "armeabi-v7a", "arm64-v8a" 로 제한
+ MapCircle 사용시 에뮬레이터에서는 이미지가 화려하게 깨져보이는 현상 발생 -> 커스텀 마커이미지로 변경
+ 추가기능 구현 검색, 리버싱 변환은 시간날때 적용 예정 (검색은 어차피 API호출이라...)
+ 다음 프로젝트 ???
