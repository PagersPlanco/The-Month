# The Month

<img src="https://github.com/user-attachments/assets/6831ae01-1180-4ed3-a60f-08c7db4e2d8e" width="60"/> 

**The Month - 당신의 한 달을, 캔버스에**

![image 1](https://github.com/user-attachments/assets/538c86f5-ac6e-40cb-9602-6a0458b39277)


👉🏻 [앱스토어 링크](https://apps.apple.com/kr/app/the-month/id6504983925)

현재 버전: v1.0.2

_**(⬇️ 기술 소개는 하단에...)**_

## 앱 소개
오늘의 하루를 글과 함께, 나만의 월간 캔버스에 꼴라쥬 해보세요! ☘️

#### - 월간 캔버스 🖼️

글로만 하루, 한달을 기록하기에는 조금 아쉽지 않나요?  
이제는 나만의 월간 캔버스에 하루에 하루, 나만의 사진을 넣어 꾸며보세요.  
월간 캔버스는 매달 초기화 돼요.  
그리고 가끔은 나의 한달이 아닌 그저 내가 꾸미고 싶은 놀이터가 필요할 수 있잖아요? 그래서 준비했습니다. 

#### - 나만의 커스텀 캔버스 🎨

최대 5개까지 만들 수 있는 나만의 커스텀 캔버스에  
내가 좋아하는 것, 내가 기록하고 싶은 것을 모두 자유롭게 꼴라쥬 해보세요!

#### - 더 자연스러운 누끼 ✂️

아이폰의 앨범에서 꾹 눌러서 따는 누끼를 이제 The Month 안에서 만나보세요!  
하지만 이제 더이상 울퉁불퉁한 누끼는 그만!  
부드러운 테두리의 더 자연스러운 누끼를 만나보세요!

#### - 레이어 순서 변경 🔢

캔버스에 시간이 갈수록 위로 쌓이기만 한다면 정말 곤란하겠죠?  
가장 먼저 추가한 사진이 항상 맨 아래에 있으면 아쉽죠.  
그래서 추가할 사진의 레이어 순서를 내 마음대로 조절할 수 있어요!

#### - 필터 추가 🔫

일반적인 사진만 넣으면 재미 없을 수 있으니  
여러 필터도 넣었어요! 계속 추가되고, 보완될 기능이니 기대해주세요!

#### - 텍스트 및 The Month 만의 스티커 추가 📚

사진 말고 가끔은 텍스트를 캔버스에 추가하고 싶을 때가 있겠죠?  
그때 바로 텍스트를 넣어보세요!  

그리고 꾸준하게 업데이트 될 The Month 만의 스티커도 추가해보세요!


## 기술 스택
### iOS 17.0 ~
> - SwiftUI
> - Vision
> - SwiftData
> - Swift Concurrency
> - Factory
> - MVVM
> - Firebase (Analytics, Crashlytics)
> - Clean Architecture

## 스크린샷

### - 크롭
<img src="https://github.com/user-attachments/assets/d73aa762-1da3-4be3-84cb-83cd8440a681" width="200"/> 

### - 올가미 툴

<img src="https://github.com/user-attachments/assets/4b7b6885-edab-4d14-a121-b32a1e4bde3f" width="200"/> 

### - 누끼 따기

<img src="https://github.com/user-attachments/assets/71f905b6-c4db-4aa4-a1c8-c02d54c6107d" width="200"/> <img src="https://github.com/user-attachments/assets/5a03a4a7-ab4d-4841-b3cf-982915448117" width="200"/> 

### - 레이어 조절
<img src="https://github.com/user-attachments/assets/f24b72e0-db31-4da2-b4e6-6fccc831da7e" width="200"/> 

### - 텍스트 추가 

<img src="https://github.com/user-attachments/assets/e376c7bf-4de8-4c9f-8a6f-13555be2166d" width="200"/>

### - 나의 캔버스 인스타 공유
<img src="https://github.com/user-attachments/assets/69cffe44-e49f-4cf1-97d1-77fb36f0e4ac" width="200"/>

## 코어 기술

### - CIImage
이미지를 다루는 핵심 기술은 CIImage 입니다.  
이미지의 데이터를 다루는 Class 입니다. 이미지를 처리하는 데에 있어 실제 데이터를 화면에 표시하지 않고  
이미지 속성 (크기나 색상 공간), 적용된 필터 데이터의 체인, 이미지가 변환된 정보들을 지니고 있습니다.  

여기서 포인트는 데이터입니다.
우리가 실제로 이미지를 다룰 때, 스크린에 보이게 할 때는 픽셀을 저장하고 로드해야 하기 때문에 메모리 사용량이 
급격하게 늘게 됩니다. 하지만 CIImage 는 데이터를 들고만 있고, 필요할 때 픽셀을 만들어 UIImage 로 변환합니다.  
그렇기 때문에 메모리 사용에 있어서 유용하고, GPU 를 사용하기 때문에 CPU 를 사용하는 것보다 더 빠르게 처리가 됩니다.

### - VNGenerateForegroundInstanceMaskRequest
iOS 17.0 부터 사용 가능하며, WWDC23 에서 확인 가능합니다.
해당 기능이 새롭게 풀리며, 기존에 있었던 VNGeneratePersonSegmentationRequest 보다 더 정확하고, 사람만이 아닌 객체의 마스크를 뽑아내기에 더 탁월합니다. 해당 기능에서 마스크를 추출하고, 이 추출한 대상 마스크를 Core Image 와 결합하여 더 부드러운 테두리를 가진 오브젝트를 뽑아낼 수 있습니다.

### - Factory
클린 아키텍쳐를 SwiftUI + MVVM + Coordinator 에 적용시키려면 필수적으로 의존성 주입(DI) 에 대한 툴이 필요했습니다.  
물론 직접 구현할 수 있었겠지만, 코드가 불필요하게 길어질 수 있다는 생각이 들어 Swift 로 만들어진 가벼운 Factory 라이브러리를 사용했습니다.  
의존성 생성 및 관리가 간단하고, 컴파일 단계에서 오류를 잡을 수 있게 되어 있어 사용했습니다.

## 팀원

**팀 Pagers** 는 총 3명으로 구성되어 있습니다.

심규보 - iOS, 기획, 마케팅, UIUX 피드백

황연진 - AOS, 마케팅

이지은 - Design, 마케팅


---




