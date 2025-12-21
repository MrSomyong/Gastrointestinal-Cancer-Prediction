# Gastrointestinal-Cancer-Prediction
AI Detect Cancer in GI system, Gastrointestinal system

# Main Idea Gastrointestinal Cancer Prediction คือ อะไร
Input VDO and Retrive Image
1. Extract Image from VDO. สามารถกำหนด Time ในการคัดเลือก Frame Image ได้ เช่น ส่งไปในทุกๆ 3 วินาที
2. สร้าง Model Decision Image เลือกภาพที่ดีที่สุดจาก Frame Image เพื่อส่งให้ Model Prediction
3. Retrive Frame Image

<img width="2935" height="1288" alt="image" src="https://github.com/user-attachments/assets/35ce77b0-e3e1-4169-a3eb-2e06b5002b61" />

# Data Flow
วิดีโอ → Frame Extraction (≥30 FPS) → Normalization → CADe Model (Detection) → CADx Model (Diagnosis) → Real-Time Overlay (แสดงผลบนหน้าจอแพทย์) → Logging (บันทึกข้อมูล)

ระบบมีส่วนประกอบหลักสามารถแบ่งออกได้เป็น 3 ส่วนหลัก คือ

1. ส่วนประมวลผลวิดีโอ (Input/Pre-Processing)
2. ส่วน Core Model (Model/Engine)
3. ส่วนแสดงผล (Output/Interface)

<img width="1004" height="671" alt="image" src="https://github.com/user-attachments/assets/8b90aad5-ad29-4ce3-bf71-a99bdb032b50" />

# สร้าง กราฟ Loss และ Accuracy
กราฟ Loss (ด้านซ้าย): เส้นควรจะ "ดิ่งลง" อย่างรวดเร็วในช่วงแรกและค่อยๆ นิ่งในช่วงปลาย ถ้าเส้นยังหัวทิ่มลงแรงๆ ตอนถึงรอบที่ 50 แปลว่าโมเดลยังเรียนรู้ต่อได้อีก (เพิ่ม Epochs ได้)

กราฟ Accuracy (ด้านขวา): เส้นควรจะ "พุ่งขึ้น" ยิ่งเข้าใกล้ 1.0 (หรือ 100%) เท่าไหร่ยิ่งดีครับ
<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/396f2012-8caf-4488-8365-e6b117ee2c29" />


# Prediction
1. Train Model ด้วย Image และ Image label
<img width="660" height="236" alt="image" src="https://github.com/user-attachments/assets/ebbad03b-f00e-4049-9153-69ee63004875" />

2. ส่ง Image เข้าไป Predicted Mask เพื่อหาจุด Mask ของรอยโรค
<img width="986" height="474" alt="image" src="https://github.com/user-attachments/assets/48c5d29a-a058-4394-a37b-e95b6a64a12d" />

3. นำ Image เข้ามา Overlay ระหว่าง Original Image และ Predicion Mask
<img width="986" height="330" alt="image" src="https://github.com/user-attachments/assets/25fce9ca-5077-47e2-a9e5-3ec2e8ea28c5" />
<img width="992" height="326" alt="image" src="https://github.com/user-attachments/assets/4ffcaebb-e433-4bc5-a5b4-97ee1dc85986" />
<img width="640" height="633" alt="image" src="https://github.com/user-attachments/assets/39143755-0f55-405b-a3d6-7a5413970f1a" />




