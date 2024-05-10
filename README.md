● Visual Studio 2022에 OpenCV를 설치하는 과정

1. OpenCV 다운로드 
- 사이트 = https://opencv.org/releases/
- C드라이브에 다운로드(표준) 예) C:/opencv

2. Visual Studio 프로젝트 속성 설정
- 새로운 프로젝트를 생성하거나 기존 프로젝트를 연 후, 상단 바에 있는 프로젝트(P) 클릭 ▶ 속성(P) 클릭
- 구성속성 ▷ C/C++ ▶ 일반 ▶ 추가 포함 디렉터리 ▶ <편집...> 클릭 ▶ C:\opencv\build\include 입력 후 확인
- 구성속성 ▷ 링커 ▶ 일반 ▶ 추가 라이브러리 디렉터리 ▶ <편집...> 클릭 ▶ C:\opencv\build\x64\vc16\lib 입력 후 확인
- 구성속성 ▷ 링커 ▶ 입력 ▶ 추가 종속성 ▶ <편집...> 클릭 ▶ opencv_world490d.lib 입력 후 확인

3. 윈도우 시스템 환경변수 설정
- 구성속성 ▶ 디버깅 ▶ 환경 ▶ <편집...> 클릭 ▶ PATH=C:\opencv\build\x64\vc16\bin;%PATH% 입력 후 확인
