Class 13 - Voice of Customer Analytics-20211114

เอาข้อมูลจาก Wong Nai Review มาทำการจัดกลุ่มประเภทที่ลูกค้ารีวิว โดยใช้ K-Means Clustering & Agglomorative Clustering

ใน Step 4 - result discussion อาจารย์ ให้ลองแก้ optimize code และสรุป result ซึ่งสิ่งที่ปรับแก้จากอาจารย์คือ

ใน Step2# ได้ลองทำการ set new_words ใหม่เผื่อว่าจะทำให้การทำ clustering แล้วสามารถอธิบายลักษณะของแต่ละกลุ่มได้ดีขึ้น

โดยดูคำที่อาจจะรวมกันแล้วมีความหมาย เช่น หัว-หิน,ราช-เทวี,อ-เม-ซอน,รสชาติ-ดี,ชานม-ไข่มุก, เค้า-ดาว ไปทำเป็น new_words 

new_words = {"สตารบัก","หัวหิน","ราชเทวี","อเมซอน","รสชาติดี","ชาไข่มุก","ชานม","ชานมไข่มุก", "เค้าดาว"}

นอกจากนั้นยังเจอคำ กก ที่เกิดจากการพิมพ์ซ้ำ เช่น ยากกกกก, มากกกกกก ควรจะต้องแก้ตอนทำ regex cleansing word แต่ยังหาวิธีทำไม่ทันครับ

ทำการเพิ่ม result ของทั้ง K-Means Clustering & Agglomorative Clustering ให้เป็น Top20 เพื่อจะได้เห็นภาพกว้างขึ้น

สรุปคือพิจารณาดูแล้ว KMEANS จัดกลุ่มได้มีความหมายมากกว่า Agglomorative Clustering ดังนี้ครับ

KMEANS Result

![image](https://user-images.githubusercontent.com/73054276/144158575-26cf5009-afdb-4495-b631-64b83c2ff14d.png)

KMEANS Definition

กลุ่ม :  defind group

0   :   รีวิวร้านอาหาร

1   :   รีวิวร้านกาแฟ

2   :   รีวิวอาหารที่ร้านกาแฟ

3   :   รีวิวชานมไข่มุก

Agglomorative Result

![image](https://user-images.githubusercontent.com/73054276/144158705-c31bcd4b-7835-4cbb-bd85-fedde4f57942.png)

จะเห็นว่า Agglomorative ดูแล้วไม่สามารถ ให้ความหมายของแต่ละกลุ่มได้เลยครับ

///////////////////////////////////////////////////////////////////////////////////////////////////////////////

**Code!!**

Step 0 - install and import dependencies

![image](https://user-images.githubusercontent.com/73054276/144159011-6a455cd3-bcdc-478b-9ba2-4147ae47ab76.png)

Step 1 - document embedding and dimension reduction

![image](https://user-images.githubusercontent.com/73054276/144161169-43cf0e65-34ea-433f-a8d5-eb4e643e1a1d.png)

Step 2 - document clustering using KMeans

ใช้ Elbow ในการพิจารณาหาค่า K ที่เหมาะสม ซึ่งก็เห็นว่า K=4 และ K=5 ค่า WCSS ไม่ค่อยเปลี่ยนแปลงแล้ว ดังนั้น ค่า K=4 จึงเหมาะสมแล้วกับข้อมูลชุดนี้

![image](https://user-images.githubusercontent.com/73054276/144161233-75c88cdf-a840-4b74-b10d-4708b1f7e41d.png)

![image](https://user-images.githubusercontent.com/73054276/144161514-67bb73e4-45e8-4348-8301-5519d6c02d98.png)

![image](https://user-images.githubusercontent.com/73054276/144161591-371ccb0b-5c2d-41d2-92c6-26c4f1760f2e.png)

![image](https://user-images.githubusercontent.com/73054276/144161641-c0f4c4f9-bd1d-427d-a22d-ecc92fa67a7a.png)

![image](https://user-images.githubusercontent.com/73054276/144161675-d5d0d8f6-6d33-4d23-8c54-5e3d41cac17a.png)

Step 3 - document clustering using Agglomorative Clustering with cosine similarity

![image](https://user-images.githubusercontent.com/73054276/144161721-1cd1a1dd-4593-4c76-a6f0-e7ae9b42addb.png)

![image](https://user-images.githubusercontent.com/73054276/144161776-a5a63ed1-a503-4e5a-90fe-89eac51930f2.png)
