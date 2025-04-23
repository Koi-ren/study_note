# 포탑 선회 속도 회귀분석

- 포탑 선회 속도 분석을 위해 우선 포탑을 아래의 코드를 통해 선회 시켰다

  
  
## 실행 코드

```python

# from flask import Flask, request, jsonify

# import os

# import torch

# from ultralytics import YOLO

  

# app = Flask(__name__)

# model = YOLO('yolov8n.pt')

  

# # Move commands with weights (11+ variations)

# move_command = [

# ]

  

# # Action commands with weights (15+ variations)

# action_command = [

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0},

#     {"turret": "Q", "weight": 1.0}

# ]

  

# @app.route('/detect', methods=['POST'])

# def detect():

#     image = request.files.get('image')

#     if not image:

#         return jsonify({"error": "No image received"}), 400

  

#     image_path = 'temp_image.jpg'

#     image.save(image_path)

  

#     results = model(image_path)

#     detections = results[0].boxes.data.cpu().numpy()

  

#     target_classes = {0: "person", 2: "car", 7: "truck", 15: "rock"}

#     filtered_results = []

#     for box in detections:

#         class_id = int(box[5])

#         if class_id in target_classes:

#             filtered_results.append({

#                 'className': target_classes[class_id],

#                 'bbox': [float(coord) for coord in box[:4]],

#                 'confidence': float(box[4])

#             })

  

#     return jsonify(filtered_results)

  

# @app.route('/info', methods=['POST'])

# def info():

#     data = request.get_json(force=True)

#     if not data:

#         return jsonify({"error": "No JSON received"}), 400

  

#     print("📨 /info data received:", data)

  

#     # Auto-pause after 15 seconds

#     #if data.get("time", 0) > 15:

#     #    return jsonify({"status": "success", "control": "pause"})

#     # Auto-reset after 15 seconds

#     #if data.get("time", 0) > 15:

#     #    return jsonify({"stsaatus": "success", "control": "reset"})

#     return jsonify({"status": "success", "control": ""})

  

# @app.route('/update_position', methods=['POST'])

# def update_position():

#     data = request.get_json()

#     if not data or "position" not in data:

#         return jsonify({"status": "ERROR", "message": "Missing position data"}), 400

  

#     try:

#         x, y, z = map(float, data["position"].split(","))

#         current_position = (int(x), int(z))

#         print(f"📍 Position updated: {current_position}")

#         return jsonify({"status": "OK", "current_position": current_position})

#     except Exception as e:

#         return jsonify({"status": "ERROR", "message": str(e)}), 400

  

# @app.route('/get_move', methods=['GET'])

# def get_move():

#     global move_command

#     if move_command:

#         command = move_command.pop(0)

#         print(f"🚗 Move Command: {command}")

#         return jsonify(command)

#     else:

#         return jsonify({"move": "STOP", "weight": 1.0})

  

# @app.route('/get_action', methods=['GET'])

# def get_action():

#     global action_command

#     if action_command:

#         command = action_command.pop(0)

#         print(f"🔫 Action Command: {command}")

#         return jsonify(command)

#     else:

#         return jsonify({"turret": "", "weight": 0.0})

  

# @app.route('/update_bullet', methods=['POST'])

# def update_bullet():

#     data = request.get_json()

#     if not data:

#         return jsonify({"status": "ERROR", "message": "Invalid request data"}), 400

  

#     print(f"💥 Bullet Impact at X={data.get('x')}, Y={data.get('y')}, Z={data.get('z')}, Target={data.get('hit')}")

#     return jsonify({"status": "OK", "message": "Bullet impact data received"})

  

# @app.route('/set_destination', methods=['POST'])

# def set_destination():

#     data = request.get_json()

#     if not data or "destination" not in data:

#         return jsonify({"status": "ERROR", "message": "Missing destination data"}), 400

  

#     try:

#         x, y, z = map(float, data["destination"].split(","))

#         print(f"🎯 Destination set to: x={x}, y={y}, z={z}")

#         return jsonify({"status": "OK", "destination": {"x": x, "y": y, "z": z}})

#     except Exception as e:

#         return jsonify({"status": "ERROR", "message": f"Invalid format: {str(e)}"}), 400

  

# @app.route('/update_obstacle', methods=['POST'])

# def update_obstacle():

#     data = request.get_json()

#     if not data:

#         return jsonify({'status': 'error', 'message': 'No data received'}), 400

  

#     print("🪨 Obstacle Data:", data)

#     return jsonify({'status': 'success', 'message': 'Obstacle data received'})

  

# #Endpoint called when the episode starts

# @app.route('/init', methods=['GET'])

# def init():

#     config = {

#         "startMode": "start",  # Options: "start" or "pause"

#         "blStartX": 60,  #Blue Start Position

#         "blStartY": 10,

#         "blStartZ": 27.23,

#         "rdStartX": 59, #Red Start Position

#         "rdStartY": 10,

#         "rdStartZ": 280

#     }

#     print("🛠️ Initialization config sent via /init:", config)

#     return jsonify(config)

  

# @app.route('/start', methods=['GET'])

# def start():

#     print("🚀 /start command received")

#     return jsonify({"control": ""})

  

# if __name__ == '__main__':

#     app.run(host='0.0.0.0', port=5000)

  
  

```

  
## 회귀 분석
위 코드를 실행시켜 기록된 로그 데이터를 활용하여 csv 파일을 생성, 후 회귀 분석 진행한다

  
  

```python

import pandas as pd

log_data = pd.read_csv("log.csv")

log_data.head(4)

  

import pandas as pd

  

columns = ['Time', 'Distance', 'Player_Pos_X', 'Player_Pos_Y', 'Player_Pos_Z',

           'Player_Speed', 'Player_Health', 'Player_Turret_X', 'Player_Turret_Y',

           'Player_Body_X', 'Player_Body_Y', 'Enemy_Pos_X', 'Enemy_Pos_Y',

           'Enemy_Pos_Z', 'Enemy_Speed', 'Enemy_Health', 'Enemy_Turret_X',

           'Enemy_Turret_Y', 'Enemy_Body_X', 'Enemy_Body_Y']

  

log_data = pd.read_csv('log.csv', sep=',', usecols=range(0, 20))

  

log_data.head(5)

```

|   | Time | Distance | Player_Pos_X | Player_Pos_Y | Player_Pos_Z | Player_Speed | Player_Health | Player_Turret_X | Player_Turret_Y | Player_Body_X | Player_Body_Y | Enemy_Pos_X | Enemy_Pos_Y | Enemy_Pos_Z | Enemy_Speed | Enemy_Health | Enemy_Turret_X | Enemy_Turret_Y | Enemy_Body_X | Enemy_Body_Y |
|---|------|----------|--------------|--------------|--------------|--------------|---------------|-----------------|-----------------|---------------|---------------|-------------|-------------|-------------|-------------|--------------|----------------|----------------|--------------|--------------|
| 0 | 0.12 | 260.99   | 59.35        | 7.9890       | 27.23        | 8.72         | 100.0         | 355.36          | 0.0             | 0.0           | 0.0           | 0.0         | 135.46      | 8.9338      | 276.87      | 0.57         | 100.0          | 180.0          | 0.0          | 180.0        |
| 1 | 0.24 | 260.99   | 59.35        | 7.9967       | 27.23        | 0.06         | 100.0         | 350.23          | 0.0             | 0.0           | 0.0           | 0.0         | 135.46      | 8.7599      | 276.87      | 1.35         | 100.0          | 180.0          | 0.0          | 180.0        |
| 2 | 0.38 | 260.99   | 59.35        | 7.9774       | 27.23        | 0.15         | 100.0         | 344.95          | 0.0             | 0.0           | 0.0           | 0.0         | 135.46      | 8.5987      | 276.87      | 1.22         | 100.0          | 180.0          | 0.0          | 180.0        |
| 3 | 0.50 | 260.99   | 59.35        | 7.9990       | 27.23        | 0.17         | 100.0         | 339.92          | 0.0             | 0.0           | 0.0           | 0.0         | 135.46      | 8.5996      | 276.87      | 0.01         | 100.0          | 180.0          | 0.0          | 180.0        |
| 4 | 0.63 | 260.99   | 59.35        | 7.9848       | 27.23        | 0.11         | 100.0         | 334.79          | 0.0             | 0.0           | 0.0           | 0.0         | 135.46      | 8.6000      | 276.87      | 0.00         | 100.0          | 180.0          | 0.0          | 180.0        |

  
  
  
```python
from sklearn.model_selection import train_test_split

  

# 독립 변수(X)와 종속 변수(y) 추출

X = log_data["Time"].values.reshape(-1, 1)  

y = log_data["Player_Turret_X"].values

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

  

from sklearn.linear_model import LinearRegression

  

model = LinearRegression()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)

import matplotlib.pyplot as plt

%matplotlib inline

  

plt.scatter(y_test, y_pred, alpha=0.4)

plt.xlabel("Time")

plt.ylabel("Turret_angle")

plt.title("LINEAR REGRESSION")

plt.show()

```

  
  

![png](output_5_0.png)

  
  
  

```python

print(f"Slope (Coefficient): {model.coef_[0]:.4f}")

print(f"Intercept: {model.intercept_:.4f}")

```

  

    Slope (Coefficient): -35.9728

    Intercept: 346.7683

  

### 포탑 회전 수는 다음과 같이 회귀된다

$$

y = -35.9728 * x + 346.7683

$$

