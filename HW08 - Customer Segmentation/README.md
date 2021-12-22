**Class08 Customer Segment**

อาจารย์แบ่งกลุ่ม **Group9	Pisuttipong Mekdang/Thanisorn Saraphan/Wuttipon Assawaniramol** แล้วให้ช่วยกัน edit code ทำ KMeans จัดกลุ่มลูกค้า และตั้งชื่อกลุ่มเหล่านั้นแบบเก๋ๆ ตัวอย่างเช่น...

![InterPreting KMeans Result](https://user-images.githubusercontent.com/73054276/146485155-7faa20bb-1323-4efd-bce6-3a2c17255ba3.PNG)

ใช้ DT ช่วยในการหาความหมายของทั้ง 5 กลุ่ม คือ DT จะแสดงให้เราเห็นว่า classifier แต่ละกลุ่มด้วย criteria อะไร เพื่อที่เราจะได้นำค่า criteria เหล่านั้นมาหาความหมายหรือตั้งชื่อกลุ่มนั้นๆ ซึ่งผลลัพธ์ที่ได้ดังรูปครับ

![image](https://user-images.githubusercontent.com/73054276/146575494-a8328fc7-81da-4663-9713-405e66b51b78.png)

สรุป Criteria ที่ DT ใช้แบ่งกลุ่ม และตั้งชื่อกลุ่ม + หา Solution ในการทำ recomendation ให้แต่ละกลุ่ม

![image](https://user-images.githubusercontent.com/73054276/146492992-3b53852f-6868-4c9a-a3e6-eb6568fd7f0e.png)

![image](https://user-images.githubusercontent.com/73054276/146983963-22d03d79-7d9e-4013-9ab9-fa9931a33279.png)

//////////////////////////////////////////////////

**code detail**

ตรวจสอบ null data

![image](https://user-images.githubusercontent.com/73054276/147025504-58ba5cc8-3a47-4df6-954d-d22a3db91b24.png)

ทำ customer single view สรุป feature ที่ใช้ ดังนี้

![image](https://user-images.githubusercontent.com/73054276/147025624-4df480ed-b0f3-4f9c-a8a0-a712fde36b68.png)

ลองใช้ feature Shop Weekday/ Shop hour เพื่ออยากแบ่งกลุ่มลูกค้าตามช่วงเวลาที่ซื้อ และลองเลือก Basket Dominant มาลองดูกลุ่มประเภทสินค้าที่ซื้อ

![image](https://user-images.githubusercontent.com/73054276/147026320-d725eaaa-6189-4a52-a07e-bc7ecf29e47a.png)

model & metric ที่ใช้

![image](https://user-images.githubusercontent.com/73054276/147027046-7986e04f-8a3e-484f-b25e-7ab79bcd1ab1.png)

![image](https://user-images.githubusercontent.com/73054276/147027104-57f9c154-3d00-4e7d-b630-b4500fd10c4c.png)

Spectral Clustering Clustering & KMEANS Clustering ให้ผลที่ดี

![image](https://user-images.githubusercontent.com/73054276/147028303-43bbcd9e-5e1f-4f5a-8616-601c9c66fbfd.png)

![image](https://user-images.githubusercontent.com/73054276/147028366-8eefb776-3ded-4a72-b1c0-4d6f104e1f42.png)

![image](https://user-images.githubusercontent.com/73054276/147028455-03d3da1d-4e0b-4465-ba9a-9c3ff2886733.png)

![image](https://user-images.githubusercontent.com/73054276/147028497-1102056a-6894-449b-b82e-b7441a8b5eba.png)

![image](https://user-images.githubusercontent.com/73054276/147028600-e29913a9-7b56-42f6-8b89-71e14395a7f5.png)





