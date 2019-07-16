
![voronoijpg](https://user-images.githubusercontent.com/45711050/61276570-477c6a80-a7eb-11e9-822e-c2c6325efc0a.JPG)




# Voronoi Diagram


- >  MY CODE

<![if !supportEmptyParas]> <![endif]>

<![if !supportEmptyParas]> <![endif]>

from PIL import Image

import random

import math

def 보로노이_다이어그램_생성(폭, 높이, 셀_숫자):

image = Image.new("RGB", (폭, 높이))

putpixel = image.putpixel

imgx,imgy = image.size

nx = [1, 250, 250, 250, 250, 382.1, 382.1, 382.1, 382.1, 441.05, 441.05, 708.95,708.95,708.95,708.95, 650, 650, 791.975,791.975,791.975,791.975, 930]

ny = [250, 90, 135, 365, 432.5, 432.5, 365, 135, 90 , 365, 135, 90,135,365,432.5, 365, 135, 90, 135, 365, 432.5 , 250]

nr = [255,100,53,1,81,48,59,58,27,56,5,104,243,52,81,20,21,48,57,76,85,24 ]

ng = [100,150,62,83,54,1,19,107,18,209,50,151,202,103,84,75,126,12,199,43,19,51]

nb = [2,12,33,94,55,86,57,158,89,160,31,82,163,65,75,166,217,68,209,30,21,52 ]

#num_cells = len(nx)

'''

for i in range(셀_숫자):

nx.append(random.randrange(imgx))

ny.append(random.randrange(imgy))

nr.append(random.randrange(256))

ng.append(random.randrange(256))

nb.append(random.randrange(256))'''

<![if !supportEmptyParas]> <![endif]>

print(nx,"\n",ny)

print(imgx, imgy)

<![if !supportEmptyParas]> <![endif]>

for y in range(imgy):

for x in range(imgx):

dmin = math.hypot(imgx, imgy)

j = -1

for i in range(셀_숫자):

d = math.hypot(nx[i]-x, ny[i]-y)

if d < dmin:

dmin = d

j = i

putpixel((x, y), (nr[j], ng[j], nb[j]))

image.save("VoronoiDiagram.png", "PNG")

image.show()

<![if !supportEmptyParas]> <![endif]>

<![if !supportEmptyParas]> <![endif]>

if __name__== "__main__":

보로노이_다이어그램_생성(1000, 500,22)


### first method <첫번째 방법>
Drawing (그림그리기)



| voronoi | output |
| ------ | ------ |
| my think | >>>>>>> |


![voronoijpg22](https://user-images.githubusercontent.com/45711050/61276939-09337b00-a7ec-11e9-8c86-da201a3305be.JPG)




  



그리고 <나의 결과> 이다.    <OUTPUT>

![voronli4454](https://user-images.githubusercontent.com/45711050/61277324-ed7ca480-a7ec-11e9-9092-fe99583dfe5a.JPG)


