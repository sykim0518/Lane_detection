HSV 색공간을 이용한 Lane detection
=============
&nbsp;&nbsp; 
>### 📌 **목표**

&nbsp;&nbsp; color 이미지의 ROI를 설정하고, 흰색 차선과 주황색 중앙선을 검출하여 출력한다

&nbsp;&nbsp;
>### 📌 **ROI 설정**

&nbsp;&nbsp; Donkey car를 주행하여 얻은 test image에서 도로 부분만을 ROI로 설정한다

- 가로: 0 ~ width, 세로: (height/2) ~ height

<img width="500" alt="ROI image" src="https://user-images.githubusercontent.com/52990642/72594637-34d62000-394b-11ea-8c4b-a83b28f3f9a0.PNG">

&nbsp;&nbsp;
>### 📌 **HSV(색상,채도,명도)**
&nbsp;&nbsp; 영상이나 이미지를 색상을 검출 하기 위해 사용합니다. 채널을 Hue, Saturation, Value로 분리하여 변환할 수 있다
- 색상 (Hue) : 색의 질, 빨강, 노랑, 파랑이라고 하는 표현으로 나타내는 성질
- 채도 (Saturation) : 색의 선명도, 아무것도 섞지 않아 맑고 깨끗하며 원색에 가까운 것을 채도가 높다고 표현
- 명도 (Value) : 색의 밝기, 명도가 높을수록 백색에, 명도가 낮을수록 흑색에 가까움

<img width="800" alt="색범위" src="https://user-images.githubusercontent.com/52990642/72599102-70291c80-3954-11ea-9963-b23f27349c27.PNG">


&nbsp;&nbsp;
>📍 **주황색 검출**

- lower_orange = (8, 50, 50), upper_orange = (20, 255, 255)

&nbsp;&nbsp; 1️⃣ cv2.COLOR_BGR2HSV : BGR 색공간을 HSV 색공간으로 변환한다

&nbsp;&nbsp; 2️⃣ cv2.inRange(이미지, lower_orange, upper_orange) : 주황색의 범위를 제한한다

&nbsp;&nbsp; 3️⃣ cv2.bitwise_and() : 원본 이미지와 주황색을 추출한 마스크 이미지를 합친다

&nbsp;&nbsp;

>📍 **흰색 검출**

- lower_white = (0, 0, 180), upper_white = (255, 255, 255)

&nbsp;&nbsp; 1️⃣ cv2.COLOR_BGR2HSV : BGR 색공간을 HSV 색공간으로 변환한다

&nbsp;&nbsp; 2️⃣ cv2.inRange(이미지, lower_white, upper_white) : 흰색의 범위를 제한한다

&nbsp;&nbsp; 3️⃣ cv2.bitwise_and() : 원본 이미지와 흰색을 추출한 마스크 이미지를 합친다

&nbsp;&nbsp;


>### 📌 **Merge**
&nbsp;&nbsp; bitwise_or()를 이용하여 흰색 차선과 주황색 차선을 합친다


<img width="500" alt="결과" src="https://user-images.githubusercontent.com/52990642/72599352-e037a280-3954-11ea-8475-8fd4e8ccbc49.PNG">
