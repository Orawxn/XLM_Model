# XLM_Model

🧠 โมเดล deepset/xlm-roberta-base-squad2 
เครื่องมือที่ใช้
- Transformers
- PEFT (LoRA)
- Accelerate
- Evaluate / Datasets
- Pandas

# สร้าง virtual environment
python -m venv venv
venv\Scripts\activate   # สำหรับ Windows
# source venv/bin/activate  สำหรับ Linux / Mac

# ติดตั้ง library ที่จำเป็น
pip install -r requirements.txt
หากยังไม่มีไฟล์ requirements.txt
pip install torch transformers datasets peft accelerate evaluate scikit-learn pandas

# ดูตัวอย่างคำถาม-คำตอบ ใน dataset
python Model/src/LoRA.py

# โหลดโมเดล
python Model/src/model.py
  
# ทดสอบการตอบโมเดลก่อน fine-tune
python Model/src/testmodel.py

# หาค่า F1 score ของ baseline
python Model/src/evaluate_Model.py
ค่า F1 ของแต่ละคำถามอยูในไฟล์  \archive\evaluation_results_baseline.csv

# Fine-tune โมเดลด้วย LoRA 
python Model/src/LoRA.py


# ทดสอบโมเดลหลัง fine-tune 
python Model/src/test_LoRA.py

# หาค่า F1 score หลังจาก fine-tune และ parameter 3 ชุด
python Model/src/evaluate_LoRA.py
ค่า F1 และ Em บันทึกลงในโฟลเดอร์ result  
\results\exp_1\evaluation_results.json
\results\exp_2\evaluation_results.json
\results\exp_3\evaluation_results.json

# test set (จากพารามิเตอร์ที่ดีที่สุด)
python Model/src/testset.py
บันทึกค่าไว้ที่ "D:\Paper NLP\evaluation_val_test.csv"




