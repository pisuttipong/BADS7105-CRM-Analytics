**Class 12 - Churn Prediction Model-20211107**

ทดลองสร้าง table ใน Big Query โดยใช้ไฟล์ Supermarket Data.csv

Ref.

https://yo-thorn.medium.com/gcp-series-%E0%B8%A1%E0%B8%B2%E0%B8%A5%E0%B8%AD%E0%B8%87%E0%B9%83%E0%B8%8A%E0%B9%89-google-bigquery-%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%94%E0%B8%B5%E0%B8%81%E0%B8%A7%E0%B9%88%E0%B8%B2-1a0f2f2c6049

https://yo-thorn.medium.com/gcp-series-%E0%B8%A1%E0%B8%B2%E0%B8%A5%E0%B8%AD%E0%B8%87%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99-google-cloud-%E0%B8%81%E0%B8%B1%E0%B8%99-%E0%B9%80%E0%B8%A3%E0%B8%B4%E0%B9%88%E0%B8%A1%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%AA%E0%B8%A1%E0%B8%B1%E0%B8%84%E0%B8%A3%E0%B9%80%E0%B8%A5%E0%B8%A2-bf5f71fdf06f

**Churn Dashboard!!!**


1.Script SQL : Query on Google Big Query

![image](https://user-images.githubusercontent.com/73054276/144035194-fa89e7ad-c63f-47b1-925a-91b254f7c58f.png)

![image](https://user-images.githubusercontent.com/73054276/144035234-a7c9858d-3675-49f3-8728-09473c598ff6.png)

![image](https://user-images.githubusercontent.com/73054276/144035363-d645724e-6b35-4ad1-83de-aa31ff5c30ca.png)


2.Example Data Label!!

New Customer คือ repeat_customer =1 หรือ repeat_month = null คือลูกค้าใหม่ 

Repeat Customer คือ repeat_month =1 เดือนที่แล้วก็มา

Reactivated Customer เดือนที่แล้วไม่มา repeat_month >1 

Churn Customer ใช้การเช็ค Last_purchase_date = SHOP_DATE เป็นวันสุดท้ายที่เค้ามา แล้วเช็คว่าวันสุดท้ายต้องห่างจาก วัน reference 2008-06-01 มากกว่า 30 วัน จึงนับว่า cust นั้น churn

![image](https://user-images.githubusercontent.com/73054276/144171558-e33b4a4f-0c85-46ee-a64e-c765054ef572.png)

![image](https://user-images.githubusercontent.com/73054276/144171199-5618e6fa-270b-4a8e-88ff-7da1a28adad7.png)

3.Visualize by Tableau!!

![image](https://user-images.githubusercontent.com/73054276/144035544-3785f2bc-dd01-4ec4-bc7e-b25a60ff5a4b.png)
