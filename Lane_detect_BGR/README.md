BGR 색공간을 이용한 Lane detection
=============
&nbsp;&nbsp; 
>### 📌 **목표**

&nbsp;&nbsp; color 이미지의 ROI를 설정하고, 흰색 차선만을 검출하여 출력한다

&nbsp;&nbsp;
>### 📌 **ROI 설정**

&nbsp;&nbsp; Donkey car를 주행하여 얻은 test image에서 도로 부분만을 ROI로 설정한다

- 가로: 0 ~ width, 세로: (height/2) ~ height

<img width="500" alt="ROI image" src="https://user-images.githubusercontent.com/52990642/72594637-34d62000-394b-11ea-8c4b-a83b28f3f9a0.PNG">

&nbsp;&nbsp;
>### 📌 **비트 연산**
&nbsp;&nbsp; 비트 연산 중 bitwise_and를 이용하여 ROI와 원본 이미지를 합친다

>📍 **Input**
- 원본 영상 두개 (0이면 검은색, 1이면 흰색)


&nbsp;&nbsp; <img width="300" alt="원본 1" src="https://user-images.githubusercontent.com/52990642/72595744-dd857f00-394d-11ea-9aa9-15d9fa8c7c48.PNG"> &nbsp;&nbsp; <img width="300" alt="원본 2" src="https://user-images.githubusercontent.com/52990642/72595751-dfe7d900-394d-11ea-8be0-01bf20c3c672.PNG">



>📍 **bitwise_and()**
- 두 영상에서 모두 흰색인 부분(1)만 나타난다

<img width="800" alt="and 연산" src="https://user-images.githubusercontent.com/52990642/72596044-8d5aec80-394e-11ea-83ee-7b2fc9bb2f04.PNG">


>📍 **bitwise_or()**
- 두 영상에서 모두 검은색인 부분(0)만 나타난다

<img width="800" alt="or 연산" src="https://user-images.githubusercontent.com/52990642/72596064-99df4500-394e-11ea-824f-979454d24245.PNG">


>📍 **bitwise_xor()**
- 두 영상에서 값이 서로 같으면 검은색(0), 같지 않으면 흰색(1)으로 나타난다 

<img width="800" alt="xor 연산" src="https://user-images.githubusercontent.com/52990642/72596109-aa8fbb00-394e-11ea-884e-5b00b12fa928.PNG">


                                (이미지 출처 : https://copycoding.tistory.com/156)


&nbsp;&nbsp;


>### 📌 **Threshold**
&nbsp;&nbsp; BGR 값이 일정 Threshold 값 미만이면 (150,150,150) 검은색으로 채운다


<img width="400" alt="Lane" src="https://user-images.githubusercontent.com/52990642/72595074-5edc1200-394c-11ea-8120-5b70bd3d7421.PNG">
