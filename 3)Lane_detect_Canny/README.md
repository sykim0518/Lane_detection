Canny 알고리즘을 이용한 Lane detection
=============
&nbsp;&nbsp; 
>### 📌 **목표**

&nbsp;&nbsp; color 이미지의 ROI를 설정하고, edge를 검출하여 출력한다

&nbsp;&nbsp;
>### 📌 **ROI 설정**

&nbsp;&nbsp; Donkey car를 주행하여 얻은 test image에서 도로 부분만을 ROI로 설정한다

- 가로: 0 ~ width, 세로: (height/2) ~ height

<img width="500" alt="ROI image" src="https://user-images.githubusercontent.com/52990642/72594637-34d62000-394b-11ea-8c4b-a83b28f3f9a0.PNG">

&nbsp;&nbsp;
>### 📌 **Canny Edge Detection**
&nbsp;&nbsp; 가장 유명한 Edge detection방법으로 여러 단계의 알고리즘을 통해 경계를 찾아낸다

<img width="800" alt="canny 함수" src="https://user-images.githubusercontent.com/52990642/72601486-d7e16680-3958-11ea-9b38-dfc1d871b355.PNG">


&nbsp;&nbsp; 1️⃣ Noise Reduction
- 이미지의 노이즈를 제거한다 (5x5의 Gaussian filter를 사용)

&nbsp;&nbsp; 2️⃣ Edge Gradient Detection
- 이미지에서 Gradient의 방향과 강도를 확인한다. 경계값에서는 주변과 색이 다르기 때문에 미분값이 급속도로 변한다

&nbsp;&nbsp; 3️⃣ Non-maximum Suppression
- 이미지의 pixel을 Full scan하여 Edge가 아닌 pixel은 제거한다

&nbsp;&nbsp; 4️⃣ Hysteresis Thresholding
- 지금까지 Edge로 판단된 pixel이 진짜 edge인지 판별하는 작업을 한다
- max val과 minVal(임계값)을 설정하여 maxVal 이상은 강한 Edge, min과 max사이는 약한 edge로 설정한다
- 약한 edge가 진짜 edge인지 확인하기 위해서 강한 edge와 연결이 되어 있으면 edge로 판단하고, 그러지 않으면 제거한다

&nbsp;&nbsp;

