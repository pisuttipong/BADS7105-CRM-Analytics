Class 13 - Voice of Customer Analytics-20211114

เอาข้อมูลจาก Wong Nai Review มาทำการจัดกลุ่มประเภทที่ลูกค้ารีวิว โดยใช้ K-Means Clustering & Agglomorative Clustering 

ใน Step 4 - result discussion อาจารย์ ให้ลองแก้ optimize code และสรุป result ซึ่งสิ่งที่ปรับแก้จากอาจารย์คือ

ได้ลองทำการ set new_words ใหม่เผื่อว่าจะทำให้การทำ clustering แล้วสามารถอธิบายลักษณะของแต่ละกลุ่มได้ดีขึ้น

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

Remark: ใช้ Elbow ในการพิจารณาหาค่า K ที่เหมาะสม ซึ่งก็เห็นว่า K=4 และ K=5 ค่า WCSS ไม่ค่อยเปลี่ยนแปลงแล้ว ดังนั้น ค่า K=4 จึงเหมาะสมแล้วกับข้อมูลชุดนี้

![image](https://user-images.githubusercontent.com/73054276/144161233-75c88cdf-a840-4b74-b10d-4708b1f7e41d.png)

