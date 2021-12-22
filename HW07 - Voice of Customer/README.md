**Class 13 - Voice of Customer Analytics-20211114**

เอาข้อมูลจาก **Wong Nai Review** มาทำการจัดกลุ่มประเภทที่ลูกค้ารีวิว โดยใช้ **K-Means Clustering** & **Agglomorative Clustering** 

ใน Step 4 - result discussion อาจารย์ ให้ลองแก้ optimize code และสรุป result 

ซึ่งสิ่งที่ปรับแก้จากอาจารย์คือ

ได้ลองทำการ **set new_words** ใหม่เผื่อว่าจะทำให้การทำ clustering แล้วสามารถอธิบายลักษณะของแต่ละกลุ่มได้ดีขึ้น

โดยดูคำที่อาจจะรวมกันแล้วมีความหมาย เช่น **หัว-หิน,ราช-เทวี,อ-เม-ซอน,รสชาติ-ดี,ชานม-ไข่มุก, เค้า-ดาว** ไปทำเป็น new_words 

**new_words = {"สตารบัก","หัวหิน","ราชเทวี","อเมซอน","รสชาติดี","ชาไข่มุก","ชานม","ชานมไข่มุก", "เค้าดาว"}**

นอกจากนั้นยังเจอคำ **กก** ที่เกิดจากการพิมพ์ซ้ำ เช่น **ยากกกกก**, **มากกกกกก** ควรจะต้องแก้ตอนทำ regex cleansing word 

ทำการเพิ่ม result ของทั้ง K-Means Clustering & Agglomorative Clustering ให้เป็น **Top20** เพื่อจะได้เห็นภาพกว้างขึ้น

สรุปคือพิจารณาดูแล้ว **KMEANS** จัดกลุ่มได้มีความหมายมากกว่า **Agglomorative Clustering** ดังนี้ครับ

**KMEANS Result**

![image](https://user-images.githubusercontent.com/73054276/144158575-26cf5009-afdb-4495-b631-64b83c2ff14d.png)

**KMEANS Definition**

**กลุ่ม** :  **defind group**

**0**   :   **รีวิวร้านอาหาร**

**1**   :   **รีวิวร้านกาแฟ**

**2**   :   **รีวิวอาหารที่ร้านกาแฟ**

**3**   :   **รีวิวชานมไข่มุก**


**Agglomorative Result**

![image](https://user-images.githubusercontent.com/73054276/144158705-c31bcd4b-7835-4cbb-bd85-fedde4f57942.png)

จะเห็นว่า Agglomorative ดูแล้วไม่สามารถ ให้ความหมายของแต่ละกลุ่มได้เลยครับ

///////////////////////////////////////////////////////////////////////////////////////////////////////////////

**code detail**

ทำ document embedding and dimension reduction เพื่อที่จะเปรียบเทียบรีวิวที่พูดถึงเรื่องคล้ายๆกัน ไปอยู่กลุ่มเดียวกัน

![image](https://user-images.githubusercontent.com/73054276/147036294-a56dd1e3-a4d7-4cd1-b5e3-5f3d8972db4d.png)

 ทำ KMeans ก่อนโดย ใช้ Elbow ในการพิจารณาหาค่า K ที่เหมาะสม ซึ่งก็เห็นว่า K=4 และ K=5 ค่า WCSS ไม่ค่อยเปลี่ยนแปลงแล้ว ดังนั้น ค่า K=4 จึงเหมาะสมแล้วกับข้อมูลชุดนี้

![image](https://user-images.githubusercontent.com/73054276/144161233-75c88cdf-a840-4b74-b10d-4708b1f7e41d.png)

ได้กลุ่ม cluster review ออกมา 4 กลุ่ม

![image](https://user-images.githubusercontent.com/73054276/147036551-64f6daaa-4a01-49c6-9df0-6a94a203701e.png)

ทำ regex 

![image](https://user-images.githubusercontent.com/73054276/147036644-5b2e6a2c-b9b4-47a2-ba7d-9eff9336da6b.png)

define a function to tokenize a sentence into words and create new_words ในการทำ clean and tokenize sentences

![image](https://user-images.githubusercontent.com/73054276/147036718-37860846-eda5-4595-90e3-5cb881603877.png)
  
ผลลัพธ์ Kmeans 

![image](https://user-images.githubusercontent.com/73054276/147036894-5c8c2c97-3762-4dce-89a8-9d490bcc9597.png)

Agglomorative Clustering with cosine similarity

![image](https://user-images.githubusercontent.com/73054276/147036950-aff1c71f-e6d1-4576-880d-6fbaf48c93da.png)

ผลลัพธ์ Agglomorative 

![image](https://user-images.githubusercontent.com/73054276/147036985-4607a403-ed21-4bb3-a40f-2e971e15d29c.png)

