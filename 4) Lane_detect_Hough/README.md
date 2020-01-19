Hough 알고리즘을 이용한 Lane detection
=============
&nbsp;&nbsp; 
>### 📌 **목표**

&nbsp;&nbsp; color 이미지의 ROI를 설정하고, Hough 알고리즘을 이용하여 edge를 출력한다

&nbsp;&nbsp;
>### 📌 **ROI 설정**

&nbsp;&nbsp; Donkey car를 주행하여 얻은 test image에서 도로 부분만을 ROI로 설정한다

- 가로: 0 ~ width, 세로: (height/2) ~ height

<img width="500" alt="ROI image" src="https://user-images.githubusercontent.com/52990642/72594637-34d62000-394b-11ea-8c4b-a83b28f3f9a0.PNG">

&nbsp;&nbsp;
>### 📌 **Hough Edge Detection**
&nbsp;&nbsp; 이미지에서 모양을 찾는 가장 유명한 방법으로, 이미지의 형태를 찾거나 누락된 영역을 복원할 수 있다

<img width="900" alt="함수설명" src="https://user-images.githubusercontent.com/52990642/72679379-f5960380-3af1-11ea-9ceb-025f09b3fc7e.PNG">

<img width="800" alt="허프변환" src="https://user-images.githubusercontent.com/52990642/72679365-cc757300-3af1-11ea-9f5b-679923da7671.PNG">

&nbsp;&nbsp;

>### 📌 **Result**
<img width="300" alt="결과물" src="https://user-images.githubusercontent.com/52990642/72679410-35f58180-3af2-11ea-80c5-5037eef57d5e.PNG">
