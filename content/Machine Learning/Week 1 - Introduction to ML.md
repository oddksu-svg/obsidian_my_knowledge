# Week 1: ภาพรวมของ ML (Overview of Machine Learning)

Back to [[Phase 1 - Foundations & Classical Machine Learning]]

## 1. ภาพรวม AI, ML และ DL
โครงสร้างความสัมพันธ์ของเทคโนโลยีปัญญาประดิษฐ์:
- **AI (Artificial Intelligence):** ปัญญาประดิษฐ์ แนวคิดกว้างๆ ในการทำให้คอมพิวเตอร์มีความสามารถเลียนแบบพฤติกรรมมนุษย์
- **ML (Machine Learning):** การเรียนรู้ของเครื่อง เป็นสับเซตของ AI ที่เน้นการให้ระบบเรียนรู้และพัฒนาจากข้อมูลโดยไม่ต้องเขียนโปรแกรมสั่งการแบบเจาะจง
- **DL (Deep Learning):** การเรียนรู้เชิงลึก เป็นสับเซตของ ML ที่ใช้โครงข่ายประสาทเทียม (Neural Networks) ที่มีหลายชั้นในการประมวลผลข้อมูลที่ซับซ้อน

*อ้างอิงรายวิชา:* **EN-013-327 การเรียนรู้ของเครื่อง (Machine Learning)**
แนะนำภาพรวมของการเรียนรู้ของเครื่องและการรู้จำรูปแบบเชิงสถิติ การเรียนรู้แบบมีผู้ดูแล (Supervised) การเรียนรู้แบบทั่วไปและการเรียนรู้แบบจำแนก (Generative/Discriminative) การเรียนรู้แบบสัมพันธ์และไม่สัมพันธ์กับตัวแปร เครือข่ายนิวรัล (Neural Networks) ซัพพอร์ตเวกเตอร์แมชชีน (SVM) การเรียนรู้แบบไม่มีผู้ดูแล (Unsupervised) การจัดกลุ่ม (Clustering) การลดมิติ (Dimensionality reduction) ระบบให้คำแนะนำ (Recommender systems) การเรียนรู้แบบลึก (Deep learning) ทฤษฎีการเรียนรู้ และการเรียนรู้แบบมีแรงเสริม (Reinforcement learning)

---

## 2. Software Engineering Basics
*อ้างอิงรายวิชา:* **EN-013-334 การออกแบบและพัฒนาซอฟต์แวร์ (Software Design and Development)**
- กระบวนทัศน์การเขียนโปรแกรม (Programming paradigms)
- หลักการออกแบบ (Design principles) และสถาปัตยกรรมซอฟต์แวร์
- การควบคุมเวอร์ชั่น (Version Control - Git)
- การทดสอบระดับยูนิต (Unit testing) และการจัดองค์ประกอบของโค้ดใหม่ (Refactoring)

### เครื่องมือพื้นฐาน (Top 20 Commands)
**Git Version Control:**
คำสั่งยอดนิยมสำหรับการจัดการ Source Code (เช่น `git init`, `git add`, `git commit`, `git push`, `git pull`)

**Conda Environment:**
คำสั่งสำหรับการจัดการสภาพแวดล้อม (Environment) และแพ็คเกจ (เช่น `conda create`, `conda activate`, `conda install`)

---

## 3. กระบวนการทำโปรเจกต์ ML แบบ End-to-End
กระบวนการพัฒนา ML Pipeline แบบครบวงจร ตั้งแต่การเตรียมข้อมูลไปจนถึงการนำโมเดลไปใช้งานจริง (อ้างอิงเนื้อหาจากการสรุปด้วย NotebookLM)

---

## 4. Workshops ประจำสัปดาห์

### Workshop 1: Environment & Version Control
- การตั้งค่า Environment (Conda/Venv)
- การใช้งาน Git Version Control พื้นฐาน

### [[Workshop 2 - Pandas and NumPy|Workshop 2: Data Manipulation ด้วย Pandas & NumPy]]
**โจทย์ตัวอย่าง (Google Colab):**
1. โหลดข้อมูล `california_housing_train.csv` จากโฟลเดอร์ `sample_data`
2. พล็อตกราฟ Heat map แผนที่ตามพิกัด Latitude/Longitude โดยใช้ค่า `median_house_value` เป็นเกณฑ์
3. เพิ่ม Scatter plot ของพิกัดที่ตั้ง (Location)
4. เพิ่มขนาดของจุด (Population size) เพื่อตรวจสอบความหนาแน่นของประชากรในแต่ละพื้นที่
5. จัดทำเอกสารอธิบายการใช้งานไลบรารี (Libraries) แต่ละตัวที่ใช้ในการวิเคราะห์

### Workshop 3: Data Cleaning & EDA
- การทำ Data Cleaning พื้นฐาน
- การทำ Exploratory Data Analysis (EDA) เพื่อทำความเข้าใจข้อมูล

### Workshop 4: First Model with Scikit-Learn
- สร้างโมเดลแรกด้วย **Linear Regression** โดยใช้ `Scikit-Learn`
- ดูผลลัพธ์และวัดประสิทธิภาพเบื้องต้น

#tags #machine-learning #git #conda #pandas #numpy #colab
