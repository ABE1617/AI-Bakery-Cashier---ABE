# 🥖 AI Bakery Cashier - ABE

This Python app uses a **custom-trained YOLOv8 model** and **OpenCV** to automatically detect bakery items in real-time using your webcam. It counts item quantities, calculates the total price, and saves a receipt. Ideal for small bakeries or smart checkout experiments.

---

## ✅ What This App Does

- Detects bakery items using a webcam and a trained YOLOv8 model.
- Counts each item type and calculates total price using a fixed price list.
- Saves a receipt with item names, quantities, and total cost.

---


## 📸 About the Custom YOLOv8 Model

- The model (`Backery_best_ABE.pt`) was trained using [Ultralytics' YOLOv8 Google Colab Notebook](https://colab.research.google.com/github/roboflow-ai/notebooks/blob/main/notebooks/train-yolov8-object-detection-on-custom-dataset.ipynb).
- It was trained on **175 labeled images** of bakery items.
- Images were labeled and augmented using [Roboflow](https://universe.roboflow.com/bread-fwtjv/bread-im1j3), and then trained a YOLOv8 model using the said dataset.
- The model recognizes items like doughnuts, cookies, pandan bread, sesame buns, and more.

---

## ⚙️ Requirements

Install required libraries:

```bash
pip install ultralytics opencv-python
```
---

## 📥 Setup & Run Instructions

### 1. Clone or Download the Project Folder
Or just save `bakery_cashier.py` and the model `.pt` file in one folder.

### 2. Download the Custom Model
- Go to the [Roboflow Project](https://universe.roboflow.com/bread-fwtjv/bread-im1j3).
- Export the dataset and train the model using this [YOLOv8 Colab Notebook](https://colab.research.google.com/github/roboflow-ai/notebooks/blob/main/notebooks/train-yolov8-object-detection-on-custom-dataset.ipynb).
- Download the best-trained weight file and rename it to `Backery_best_ABE.pt`.

### 3. Run the App
```bash
python bakery_cashier.py
```

## 💰 Price List (Editable in Script)
```python
prices = {
    "Blue_doughnut": 1.50,
    "Bread_with_chocolate_filling": 2.50,
    "Bread_with_filling": 2.00,
    "Bread_with_milk_filling": 2.20,
    "Bread_with_milk_tea_filling": 2.30,
    "Bread_with_pandan_filling": 2.40,
    "Green_doughnut": 1.50,
    "Soft_bread": 2.00,
    "Soft_sesame_bun": 2.50,
    "ball": 1.00,
    "bean": 1.10,
    "castera": 2.00,
    "cookie": 1.50,
    "cream": 2.50,
    "foot": 1.20,
    "guabaegi": 1.30,
    "heart": 1.40,
    "soboro": 1.50
}

```
## 🧾 Example Output
```python
Cart items:
cookie: 2 x $1.50 = $3.00
Soft_bread: 1 x $2.00 = $2.00

Total cost is : $5.00
Receipt saved as 'receipt_2025-05-09_16-42-19.txt'
```
## 📝 Notes

- The webcam mode uses:

```python
model.track(source=0, show=True)
```
- You can also test with static images:
```python
model.track("Test3.jpg", show=True)
```

