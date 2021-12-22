**Class 9 - Cross-selling models-20211017**

หา Product ที่มี Transection เกิดร่วมกันบ่อยๆ เพื่อพิจารณา ทำ Cross Selling ซึ่ง Rule ที่เลือกใช้คือ

![image](https://user-images.githubusercontent.com/73054276/146981182-b989dc01-bf43-4304-98c0-9314ccfeabbb.png)

![image](https://user-images.githubusercontent.com/73054276/146981225-9c5a8b46-8ec7-49df-bf8c-c42cd9b57cd9.png)

เลือก Top15 ผลลัพธ์ที่ได้ sort ตามค่า Support เห็นดังนี้ครับ

![image](https://user-images.githubusercontent.com/73054276/146628289-7c2e9809-4cd0-41d5-99fa-1e5e09003ebd.png)

![image](https://user-images.githubusercontent.com/73054276/146628261-7adc1475-4e45-4eb2-be7d-945071fb0e50.png)

///////////////////////////////////

**code detail**

![image](https://user-images.githubusercontent.com/73054276/147032394-49adbcd2-b04a-4d90-adcd-894c903d41bb.png)

![image](https://user-images.githubusercontent.com/73054276/147032877-7ba798ef-7ab4-4e43-b28c-72dff65a2818.png)

ทำ association_rules เลือก min_support=0.5 ได้ frequent_itemsets ตัวอย่างดังนี้

![image](https://user-images.githubusercontent.com/73054276/147032924-d6ab2e1e-e11f-4390-bb4a-f7ef12b9661c.png)

เลือก Top15 ที่ lift >=1 ,  confidence >= 0.5 , support >= 0.5 ได้ผลดังตารางที่สรุปไว้ตอนต้นครับ



