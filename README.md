# Bone Fracture Detection System

A web-based application to detect bone fractures from X-ray images using YOLOv5 and Django.

## About
Built as a mini project during B.Tech (AI & ML) at CMR Engineering College, Hyderabad.  
Patients can upload X-ray images and get fracture detection results. Doctors can view patient reports.

## Tech Stack
- Python
- Django
- YOLOv5 (custom trained model)
- OpenCV
- PyMySQL
- Matplotlib

## Features
- Patient and Doctor login system
- Upload X-ray image for fracture detection
- YOLOv5 model detects fracture and draws bounding box on the X-ray
- Results saved to MySQL database
- Patient can view past detection history
- Doctor can view reports of their permitted patients

## Project Structure
```
bone-fracture-detection/
├── FractureApp/
│   ├── views.py       # Core logic - prediction, login, upload, reports
│   ├── urls.py        # URL routing
│   ├── models.py      # Database models
│   ├── apps.py        # App config
│   ├── tests.py
│   └── __init__.py
├── results.png        # YOLOv5 training results
├── requirements.txt
└── README.md
```

## Model
- YOLOv5 custom trained on bone fracture X-ray dataset
- Model weights file: `best.pt` (not included due to file size)
- Training results shown below

![Training Results](results.png)

## Database Setup
Create a MySQL database named `fracture` with these tables:
```sql
CREATE TABLE register (
    username VARCHAR(100),
    password VARCHAR(100),
    contact_no VARCHAR(15),
    email VARCHAR(100),
    address VARCHAR(200),
    user_role VARCHAR(20)
);

CREATE TABLE patient_data (
    username VARCHAR(100),
    xray_file VARCHAR(200),
    detection_result VARCHAR(100),
    upload_date VARCHAR(20),
    permit_doctor VARCHAR(100)
);
```

## How to Run
```
pip install -r requirements.txt
python manage.py runserver
```
Then open `http://127.0.0.1:8000/index.html` in your browser.

## Status
Mini Project — completed as part of B.Tech AI & ML curriculum (2024)
