# 人臉辨識與數位美妝應用
## 1 影像處理濾波器的應用
## 2 照片特定人臉模糊處理

### 馬賽克1:
![output2](https://user-images.githubusercontent.com/89370789/139787384-c9235558-9593-46ee-9b5b-00b8a3e52aae.jpg)
````Python

from PIL import Image, ImageDraw #顯示圖片
image = face_recognition.load_image_file("face93.jpg")
faces = face_recognition.face_locations(image ,model='cnn')
print("找到臉的數量=",len(faces))
pil_image = Image.fromarray(image)
for (top, right, bottom, left) in faces: #取出座標
    draw = ImageDraw.Draw(pil_image, 'RGBA') #RGB A:透明度
    leftUpPoint = (left, top) #左上角
    rightDownPoint = (right, bottom) #右下角
    twoPointList = [leftUpPoint, rightDownPoint] #兩點畫圓
    draw.ellipse(twoPointList, fill=(166,166,166,205))
    pil_image.show()
pil_image.save("output1.jpg")
display(pil_image)
````

### 馬賽克2:
![output1](https://user-images.githubusercontent.com/89370789/139787389-ce15a8a7-a667-4100-8b70-a73d68595033.jpg)
````Python
image = face_recognition.load_image_file("face92.jpg")
faces = face_recognition.face_locations(image ,model='cnn')
print("找到臉的數量=",len(faces))
pil_image = Image.fromarray(image)
for (top, right, bottom, left) in faces: #取出座標
    draw = ImageDraw.Draw(pil_image, 'RGBA') #RGB A:透明度
    leftUpPoint = (left, top) #左上角
    rightDownPoint = (right, bottom) #右下角
    twoPointList = [leftUpPoint, rightDownPoint] #兩點
    draw.ellipse(twoPointList, fill=(166,166,166,205))
    pil_image.show()
pil_image.save("output2.jpg")
display(pil_image)
````



### 影音:
https://user-images.githubusercontent.com/89370789/140038386-66f4320f-f047-4934-bde2-30ba74fb30ab.mp4




