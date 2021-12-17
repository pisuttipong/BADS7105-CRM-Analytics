**Class5 - CLV Dashboard Design**

-สามารถเลือก Month_Year ที่ต้องการจะวิเคราะห์ข้อมูล

-แถวบนจะเป็นข้อมูลทั่วไปเช่น Sum Spend, Sum Quantity, Avg. Ticket Size

-Bar Chart จะดูสัดส่วนลูกค้าระหว่าง High Value & Low Value ในแต่ละเดือนที่เลือกดู การแบ่งกลุ่มลูกค้าทำได้โดยใช้ดู Distribution ของ Spend/Freq/Quantity แล้วเลือก Percentile75 ของค่าทั้ง 3 เป็นตัวแบ่งกลุ่มลูกค้า
High Value Customer: Spend > 133 / Freq > 11 / Quantity > 90 

Low Value Customer: Spend <= 133 / Freq <= 11 / Quantity <= 90 

-Scatter Chart (Avg. Ticket Size & Sum Freq) ต้องการวิเคราะห์ Up Sale / Cross Sale ในแต่ละเดือนที่เลือกดู ซึ่งจุดสีแดงคือลูกค้ากลุ่มที่ Avg. Ticket Size สูง (> 60) แต่ความถี่ในการซื้อค่อนข้างน้อย 
อาจจะเป็นลูกค้าที่ซื้อสินค้าราคาแพง หรือชิ้นใหญ่ อาจจะทำให้ความถี่ในการซื้อไม่บ่อย ลูกค้ากลุ่มนี้อาจจะทำการ Cross Sale โดยการทำ Product Recomendation และอีกกลุ่มที่ Avg. Ticket Size น้อย + ความถี่ในการซื้อน้อย 
กลุ่มนี้น่าจะทำ Promotion เพื่อ Upsale ได้ครับ

-Line Chart ด้านล่างซ้าย จะดู Trend Spending by Customer Value (High Value & Low Value) จะเป็นข้อมูลทั้งหมด ซึ่งเราต้องการ Monitor Spending ของกลุ่มลูกค้า High Value ควรจะมากขึ้น หรืออย่างน้อยไม่ควรต่ำลง และถ้าเดือนไหนมียอดจากกลุ่มนี้ต่ำลง ก็จะต้องหาสาเหตุ และแก้ไขให้ Spending ของกลุ่มนี้กลับมาปกติ

-Line Chart ด้านล่างขวา จะช่วยการ Monitor Spending ของลูกค้าได้ชัดขึ้น คือถ้า Spending เดือนนี้ต่ำกว่าหรือสูงกว่าเดือนก่อน สามารถเห็นได้เลย

///////////////////////////////////////////////////

![6220422083_Pisuttipong_Mekdang](https://user-images.githubusercontent.com/73054276/146410153-2a555071-0f72-4114-ad8b-4465fb26e5da.jpg)
