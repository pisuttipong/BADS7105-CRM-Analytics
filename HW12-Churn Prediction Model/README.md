**Class 12 - Churn Prediction Model-20211107**

**PATH1: PREPARE DATABASE**

ทดลองสร้าง table ใน Big Query โดยใช้ไฟล์ Supermarket Data.csv

Ref.

https://yo-thorn.medium.com/gcp-series-%E0%B8%A1%E0%B8%B2%E0%B8%A5%E0%B8%AD%E0%B8%87%E0%B9%83%E0%B8%8A%E0%B9%89-google-bigquery-%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%94%E0%B8%B5%E0%B8%81%E0%B8%A7%E0%B9%88%E0%B8%B2-1a0f2f2c6049

https://yo-thorn.medium.com/gcp-series-%E0%B8%A1%E0%B8%B2%E0%B8%A5%E0%B8%AD%E0%B8%87%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99-google-cloud-%E0%B8%81%E0%B8%B1%E0%B8%99-%E0%B9%80%E0%B8%A3%E0%B8%B4%E0%B9%88%E0%B8%A1%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%AA%E0%B8%A1%E0%B8%B1%E0%B8%84%E0%B8%A3%E0%B9%80%E0%B8%A5%E0%B8%A2-bf5f71fdf06f

ตัวอย่าง Schema and table บน Big Query เมื่อ create เสร็จแล้ว

![image](https://user-images.githubusercontent.com/73054276/144172708-77e22720-53ca-4a27-9f72-1b993be9254d.png)


////////////////////////////////////////////////////////////////////////////////////////////

**PATH2: Churn Dashboard!!!**


1.Script SQL : Query on Google Big Query

ส่วนแรก Customer จะเป็น Preparation data Detail of Customer

ส่วนที่2 Status จะเป็น flag label NewCustomer, RepeatCustomer, ReactivatedCustomer

New Customer คือ repeat_customer =1 หรือ repeat_month = null คือลูกค้าใหม่ 

Repeat Customer คือ repeat_month =1 เดือนที่แล้วก็มา

Reactivated Customer เดือนที่แล้วไม่มา repeat_month >1 


ส่วนที่3 Churn จะเป็น flag label Churn

Churn Customer ใช้การเช็ค Last_purchase_date = SHOP_DATE เป็นวันสุดท้ายที่เค้ามา แล้วเช็คว่าวันสุดท้ายต้องห่างจาก วัน reference 2008-06-01 มากกว่า 30 วัน จึงนับว่า cust นั้น churn

![image](https://user-images.githubusercontent.com/73054276/144172895-e7f0dead-bc03-4c89-b484-a75faec10b27.png)

ส่วนที่4 จะเป็นการ aggregate customer flag by year_month

![image](https://user-images.githubusercontent.com/73054276/144183253-5258e4a7-276f-4e23-9480-bb5218e7b847.png)


2.Example Data Label!!



![image](https://user-images.githubusercontent.com/73054276/144171558-e33b4a4f-0c85-46ee-a64e-c765054ef572.png)

3.Visualize by Tableau!!

ลองทำบน data studio แล้ว plot graph ไม่เป็นครับ จึงใช้วิธี export csv มาทำบน tableau แทนครับ

![image](https://user-images.githubusercontent.com/73054276/144035544-3785f2bc-dd01-4ec4-bc7e-b25a60ff5a4b.png)
