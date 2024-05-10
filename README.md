● [Visual Studio 2022에 OpenCV를 설치하는 과정]

1. OpenCV 다운로드 
- 사이트 = https://opencv.org/releases/
- C드라이브에 다운로드(표준) 예) C:\opencv


2. Visual Studio 프로젝트 속성 설정
- 새로운 프로젝트를 생성하거나 기존 프로젝트를 연 후, 상단 바에 있는 프로젝트(P) 클릭 ▶ 속성(P) 클릭
- 구성속성 ▷ C/C++ ▶ 일반 ▶ 추가 포함 디렉터리 ▶ <편집...> 클릭 ▶ C:\opencv\build\include 입력 후 확인
- 구성속성 ▷ 링커 ▶ 일반 ▶ 추가 라이브러리 디렉터리 ▶ <편집...> 클릭 ▶ C:\opencv\build\x64\vc16\lib 입력 후 확인
- 구성속성 ▷ 링커 ▶ 입력 ▶ 추가 종속성 ▶ <편집...> 클릭 ▶ opencv_world490d.lib 입력 후 확인
- 적용 및 확인


3. 윈도우 시스템 환경변수 설정
- 구성속성 ▶ 디버깅 ▶ 환경 ▶ <편집...> 클릭 ▶ PATH=C:\opencv\build\x64\vc16\bin;%PATH% 입력 후 확인
- 적용 및 확인



● [이미지를 읽어오는 간단한 코드 테스트]

#include <opencv2/opencv.hpp>
#include <iostream>

int main() {
    cv::Mat image = cv::imread("example.jpg"); // 테스트 이미지 파일
    if (image.empty()) {
        std::cout << "이미지를 불러올 수 없습니다." << std::endl;
        return -1;
    }
    cv::imshow("Image", image);
    cv::waitKey(0);
    return 0;
}


- 해당 코드 입력
- 생성한 프로젝트 파일의 위치에 example.jpg의 이미지 파일 생성
- 상단 바 프로젝트 메뉴의 속성 클릭 ▶ 구성속성 ▶ 디버깅 ▶ 명령 인수 ▶ example.jpg 입력 후, 적용 및 확인
- 로컬 Windows 디버거 클릭
![example](https://github.com/mingyu2020/opencv_set_for_vs_cpp/assets/127829026/59857369-dc66-474e-890d-94bda20054d3)



● [OpenCV 샘플 파일에 있는 C++코드 실행 테스트(edge.cpp)]
- 코드 위치 = C:\opencv\sources\samples\cpp\edge.cpp
- 프로젝트에 해당 코드 입력 후 실행
![edgeMap_sobelGradient](https://github.com/mingyu2020/opencv_set_for_vs_cpp/assets/127829026/b0e4e66c-2d6b-4355-ac59-51ec7d11b597)
![edgeMap_Scharr](https://github.com/mingyu2020/opencv_set_for_vs_cpp/assets/127829026/de9af8a1-ce21-4ec9-a222-580724c5b4b3)
