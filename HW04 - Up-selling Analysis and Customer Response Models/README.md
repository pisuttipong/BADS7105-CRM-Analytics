Campaign_Response_Model (อาจารย์ให้ลองปรับจูน parameter ให้ได้ AUC ดีกว่าอาจารย์)

จาก Code อาจารย์สิ่งที่เห็นคือ 

1. Data imbalance มาก

![image](https://user-images.githubusercontent.com/73054276/146980291-401a036b-44ff-43e8-9649-c979db09c01e.png)

2. Model ค่อนข้าง Overfit โดยดูจาก precision/recall/f1 ของ test set นั้นต่ำกว่า train set มาก

![image](https://user-images.githubusercontent.com/73054276/146980239-1349d25b-79f5-45b6-8f1d-b18e0ed86f6c.png)

จาก ref. https://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-xgboost-with-codes-python/ พบว่า parameter tuning ของ Xgboost ที่เกี่ยวกับ overfit & Imbalance คือ

![image](https://user-images.githubusercontent.com/73054276/146975132-100f97ca-7c8d-4320-9ef1-ac8d3960dc1f.png)

![image](https://user-images.githubusercontent.com/73054276/146975298-3b3e065b-5f4e-4ea5-8bc9-a0facccce0ef.png)

![image](https://user-images.githubusercontent.com/73054276/146975866-1112ac6c-fb6c-4062-a1e9-61551ef81a01.png)

![image](https://user-images.githubusercontent.com/73054276/146976006-4071809e-c3a9-4a93-b97e-7e58f12fdc3f.png)

สิ่งที่ได้ทำลองปรับในส่วนของ parameter Xgboost คือ

![image](https://user-images.githubusercontent.com/73054276/146976160-6a4f7861-ea71-4f7a-af52-1a83a92f6144.png)

ค่าหลังเครื่องหมาย '#' คือค่าเดิมของอาจารย์ครับ

ผลที่ได้ดังนี้ครับ

1.XGBoost model - SMOTE RFM

![image](https://user-images.githubusercontent.com/73054276/146976428-42cf71c7-7dca-4948-91ab-8df3e1e14caf.png)

2.XGBoost model - SMOTE CLV 

![image](https://user-images.githubusercontent.com/73054276/146976488-a2f88068-3b13-478c-8ade-033762f7fceb.png)

หลังจากนั้นทดลองทำ grid search เพื่อหา best parameter

![image](https://user-images.githubusercontent.com/73054276/146978988-61002ace-c198-4e4c-abe3-e94e2ec5b47b.png)

ซึ่งเมื่อเอา best parameter ไป predict ค่าก็ยังไม่ดีมาก

Best AUC (0.709), Test Set Precision (0.18), Recall (0.77), F1 (0.29)

![image](https://user-images.githubusercontent.com/73054276/146979275-06edd4f3-6b2f-4cd1-babf-c78be1733c01.png)

สรุป

0.XGBoost model best parameter grid search CLV ของอาจารย์ --> Best AUC (0.708), Test Set Precision (0.18), Recall (0.77), F1 (0.29)

1.XGBoost model - SMOTE RFM --> Test Set AUC (0.678), Precision (0.17), Recall (0.80), F1 (0.28)

2.XGBoost model - SMOTE CLV --> Test Set AUC (0.691), Precision (0.17), Recall (0.80), F1 (0.28)

3.XGBoost model best parameter grid search CLV --> Best AUC (0.709), Test Set Precision (0.18), Recall (0.77), F1 (0.29)

////////////////////////////////////////////////////////////////////

**code detail**

data set ที่ใช้มี response กับ transactions

![image](https://user-images.githubusercontent.com/73054276/146974220-92ea81f6-47c1-4a75-b20e-910f4fd58bb8.png)

prepare data ให้เป็น RFM variables และ CLV variables

RFM

![image](https://user-images.githubusercontent.com/73054276/146974561-595d447d-eefd-4bac-8791-94a72fedac91.png)

CLV

![image](https://user-images.githubusercontent.com/73054276/146974608-2cc67029-015d-415a-9685-606dc54e3d7d.png)

split data train/ test แล้ว plot scatter เพื่อดูความสัมพันธ์ ระหว่าง feature RFM(3 feature) และ CLV (5 Feature) ยกตัวอย่างของ CLV

![image](https://user-images.githubusercontent.com/73054276/146978219-1156fc4c-ea4e-4fad-9035-f0acccda0341.png)

![image](https://user-images.githubusercontent.com/73054276/146978269-8b478288-b6f7-4f06-8460-c2a34bf40b74.png)

![image](https://user-images.githubusercontent.com/73054276/146978299-2ac9cb8b-8487-40bd-97ce-03e61e31a16f.png)

![image](https://user-images.githubusercontent.com/73054276/146978338-342bdc90-7577-4df8-8fdd-2f24f2e6089f.png)

จากนั้นใช้ SMOTE ช่วย FIX Imbalance 

![image](https://user-images.githubusercontent.com/73054276/146978445-79d11029-9e76-42c9-9202-a94ae24eb7bc.png)

แล้วลองไปเข้า Model Logistic Regression

logistic regression model - SMOTE RFM

![image](https://user-images.githubusercontent.com/73054276/146978540-711c452d-7667-4f57-beed-17668e26dcb2.png)

logistic regression model - SMOTE CLV

![image](https://user-images.githubusercontent.com/73054276/146978588-8c7e9199-3c71-4517-9b35-fb3d4fe3363f.png)

พบว่าค่าที่ได้ระหว่าง RFM vs CLV ไม่ค่อยต่างกันเท่าไหร่

ส่วนใช้ Xgboot และมีการปรับแก้ parameter อธิบายไว้ด้านบนแล้วครับ
