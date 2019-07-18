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
  nx = [135 , 260, 260, 260, 260, 390, 390, 390, 390, 450, 450, 570, 570, 630, 630, 630, 630,  730, 730, 730, 730, 850 ]
  ny = [250, 420, 300, 190, 80 , 420, 300, 190, 80 , 300, 190, 300, 190, 420, 300, 190, 80 ,  420, 300, 190, 80 ,  250]
  nr = [102, 153,  204, 255, 153, 102, 255,  51, 153, 255, 153, 51,  000, 0,     0, 0, 0,0,  0,  0,  51,   0 ]
  ng = [0  , 0  ,  0 ,  0 ,  0  , 0  , 0  ,  0 , 51 , 102,  0,  51,  000, 0,     0, 0, 0,0,  0,  0,  51,   0 ]
  nb = [0  , 0  ,  0 ,  0 ,  0  , 51 , 0  ,  0 , 51 , 102,  0,  255, 255, 102, 153, 102,0,0,102,255,255, 153 ]
  
  
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



### Result

![sfsf](https://user-images.githubusercontent.com/45711050/61435976-b933f000-a974-11e9-9072-f34587a80f20.JPG)



