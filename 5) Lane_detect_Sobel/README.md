Sobel 알고리즘을 이용한 Lane detection
=============
&nbsp;&nbsp; 
>### 📌 **목표**

&nbsp;&nbsp; color 이미지의 ROI를 설정하고, Sobel 알고리즘을 이용하여 edge를 출력한다

&nbsp;&nbsp;
>### 📌 **ROI 설정**

&nbsp;&nbsp; Donkey car를 주행하여 얻은 test image에서 도로 부분만을 ROI로 설정한다

- 가로: 0 ~ width, 세로: (height/2) ~ height

<img width="500" alt="ROI image" src="https://user-images.githubusercontent.com/52990642/72594637-34d62000-394b-11ea-8c4b-a83b28f3f9a0.PNG">

&nbsp;&nbsp;
>### 📌 **Sobel Edge Detection**
&nbsp;&nbsp; Gaussian smoothing과 미분을 이용한 방법으로, 노이즈가 있는 이미지에 적용하면 좋다. X축과 Y축을 미분하는 방법으로 경계값을 계산한다.

<img width="800" alt="함수설명" src="https://user-images.githubusercontent.com/52990642/72681705-84624a80-3b09-11ea-8943-fac4152e5db0.PNG">

&nbsp;&nbsp;

>### 📌 **Result**
<img width="300" alt="결과물" src="https://user-images.githubusercontent.com/52990642/72681741-dc994c80-3b09-11ea-81f4-a75a3bd717b6.PNG">
