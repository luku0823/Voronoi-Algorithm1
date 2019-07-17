---
# Voronoi Diagram
____

- Making a Stadium Shape Using Boronoy Diagram
- choose a correct dimensions of the photo
- choose a correct number of initial points
- choose exact positions of initial points (not randomly)
![KakaoTalk_20190715_091642507](https://user-images.githubusercontent.com/45711050/61309226-c3e36d80-a82c-11e9-9a91-d9caa332bc68.png)

### MY CODE 

```python
from PIL import Image
import random
import math
 
def 보로노이_다이어그램_생성(폭, 높이, 셀_숫자): 
  image = Image.new("RGB", (폭, 높이))
  putpixel = image.putpixel
  imgx,imgy = image.size
  nx = [1, 250, 250, 250, 250,   382.1, 382.1, 382.1, 382.1, 441.05, 441.05, 708.95,708.95,708.95,708.95, 650,  650,  791.975,791.975,791.975,791.975,  930]
  ny = [250, 90,  135, 365, 432.5, 432.5, 365,   135,   90   ,  365,   135,    90,135,365,432.5,            365, 135,  90, 135, 365,           432.5  , 250]
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

  print(nx,"\n",ny)
  print(imgx, imgy)

  
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


if __name__== "__main__":
  보로노이_다이어그램_생성(1000, 500,22)
```



