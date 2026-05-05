# Workshop 2: Data Manipulation พื้นฐานด้วย Pandas & NumPy

Back to [[Week 1 - Introduction to ML]]

## 📚 ส่วนที่ 1: ทฤษฎีพื้นฐาน (Theory)

ในการทำ Data Science และ Machine Learning ด้วย Python ไลบรารี **Pandas** และ **NumPy** ถือเป็นหัวใจสำคัญในการจัดการข้อมูล (Data Manipulation) ก่อนนำไปสร้างโมเดล

### 1. NumPy (Numerical Python)
NumPy เป็นไลบรารีพื้นฐานสำหรับการคำนวณทางคณิตศาสตร์และวิทยาศาสตร์
- **Core Data Structure:** `ndarray` (N-dimensional array) ซึ่งมีประสิทธิภาพสูงกว่า Python List ทั่วไปมาก
- **การใช้งานหลัก:** การจัดการข้อมูลตัวเลขแบบอาเรย์หลายมิติ, การทำ Vectorization, และฟังก์ชันทางคณิตศาสตร์ (Linear Algebra, สถิติเบื้องต้น)

### 2. Pandas (Python Data Analysis Library)
Pandas ถูกสร้างขึ้นบน NumPy อีกที ออกแบบมาเพื่อจัดการข้อมูลในรูปแบบตาราง (Tabular data) คล้ายกับ Excel หรือ SQL
- **Core Data Structures:**
  - `Series`: ข้อมูล 1 มิติ (อารมณ์เหมือน 1 คอลัมน์ในตาราง)
  - `DataFrame`: ข้อมูล 2 มิติแบบมีแถวและคอลัมน์ (ตารางข้อมูลเต็มรูปแบบ)
- **การใช้งานหลัก:** โหลดข้อมูล (CSV, Excel, SQL), การจัดการ Data (Filtering, Grouping, Merging), และจัดการ Missing Values

---

## 🛠️ ส่วนที่ 2: Workshop ปฏิบัติการ (Google Colab)

**เป้าหมาย:** เรียนรู้วิธีการใช้ Pandas ในการอ่านไฟล์ CSV และใช้ไลบรารีสร้างกราฟเบื้องต้น (เช่น `matplotlib` หรือ `seaborn`) เพื่อทำ Spatial Data Visualization 

🔗 **[เปิดดูโค้ดฉบับเต็มและรันจริงบน Google Colab คลิกที่นี่](https://colab.research.google.com/drive/1QRT955bd5ZxotTaJ5beA9d8uLMK5s8W6?usp=sharing)**

*สามารถทำตามโจทย์ด้านล่างใน Google Colab โดยใช้ไฟล์ที่เตรียมไว้ให้โดยอัตโนมัติของ Colab*

### ขั้นตอนการทดลอง

#### 1. โหลดข้อมูล (Read Data)
โหลดไฟล์ข้อมูล `california_housing_train.csv` ที่มีอยู่ในโฟลเดอร์ `sample_data` ของ Google Colab
```python
import pandas as pd

# 1. โหลดข้อมูลจากไฟล์ CSV
df = pd.read_csv('/content/sample_data/california_housing_train.csv')

# ดูข้อมูล 5 แถวแรก
df.head()
```

#### 2. พล็อตกราฟแผนที่ (Plot Graph by Lat/Lng Heat Map)
พล็อตกราฟแผนที่แบบ Scatter โดยใช้แกน x เป็น `longitude` และแกน y เป็น `latitude` และกำหนดสี (Heat map) ตามราคาบ้านเฉลี่ย (`median_house_value`)
```python
import matplotlib.pyplot as plt

# 2. พล็อตกราฟ Scatter ดูตำแหน่งและระบายสีตามราคาบ้าน
plt.figure(figsize=(10, 7))
plt.scatter(x=df['longitude'], y=df['latitude'], 
            c=df['median_house_value'], cmap='jet', alpha=0.6)
plt.colorbar(label='Median House Value')
plt.xlabel('Longitude')
plt.ylabel('Latitude')
plt.title('California Housing Prices by Location')
plt.show()
```

#### 3. สังเกตตำแหน่งบนแผนที่ (Add Scatter Location Lat/Lng)
จากกราฟในขั้นตอนที่ 2 เราจะเห็นรูปร่างของแผนที่รัฐแคลิฟอร์เนียอย่างชัดเจน กลุ่มจุดสีแดงจะแสดงถึงพื้นที่ที่มีราคาอสังหาริมทรัพย์สูง (เช่น บริเวณใกล้ชายฝั่งทะเล San Francisco และ Los Angeles)

#### 4. เพิ่มขนาดของประชากร (Add Population Size)
ปรับปรุงกราฟเดิมโดยใช้ฟีเจอร์ `population` มากำหนด**ขนาดของจุด (Size - `s`)** เพื่อตรวจสอบความหนาแน่นของประชากรในแต่ละพื้นที่
```python
# 3 & 4. เพิ่มขนาดของจุดตามจำนวนประชากร (Population)
plt.figure(figsize=(10, 7))
plt.scatter(x=df['longitude'], y=df['latitude'], 
            c=df['median_house_value'], cmap='jet', alpha=0.6,
            s=df['population']/100, # หาร 100 เพื่อไม่ให้จุดใหญ่เกินไป
            label='Population')

plt.colorbar(label='Median House Value')
plt.xlabel('Longitude')
plt.ylabel('Latitude')
plt.title('California Housing Prices: Value vs Population Density')
plt.legend()
plt.show()
```

#### 5. สรุปไลบรารีที่ใช้งาน (Libraries Documentation)
- **`pandas`:** ใช้สำหรับอ่านข้อมูล (`read_csv`) และจัดการโครงสร้างข้อมูลแบบ DataFrame เพื่อให้เรียกใช้คอลัมน์ต่างๆ ได้ง่าย
- **`matplotlib.pyplot`:** ใช้สำหรับวาดกราฟ (`scatter`, `colorbar`, `xlabel`, ฯลฯ) เพื่อสร้าง Visualization ให้เห็นความสัมพันธ์เชิงพื้นที่ (Spatial correlation) อย่างชัดเจน

---
**หมายเหตุ:** เนื่องจากไม่สามารถเข้าถึงเอกสาร NotebookLM ที่เป็น Private ได้ เนื้อหาในส่วนนี้จึงถูกสรุปและอ้างอิงจากแบบฝึกหัดที่กำหนดไว้ในแผนการเรียน (Google Colab: California Housing)

#tags #machine-learning #pandas #numpy #colab #workshop #visualization
