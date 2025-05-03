# 🤖 Line Follower and Obstacle Avoiding Car Robot

This embedded systems project combines **line tracking** and **obstacle avoidance** into a single autonomous robotic car. Built using an Arduino UNO, IR sensors, ultrasonic distance sensor, servo motor, and motor drivers, the robot is designed to follow a defined path while actively detecting and avoiding obstacles.

---


## 🔧 Components Used

| Component                   | Quantity |
|----------------------------|----------|
| Arduino UNO                | 1        |
| 4-wheel Robot Car Kit      | 1        |
| IR Sensors                 | 2        |
| Ultrasonic Sensor (HC-SR04)| 1        |
| Mini Servo Motor (SG90)    | 1        |
| L298 Motor Driver          | 1        |
| Buzzer                     | 1        |
| RGB LED                    | 1        |
| Breadboard                 | 1        |
| Battery Holder + 2x 18650 Batteries | 1        |
| Jumper Wires (M-M, M-F)    | Assorted |

---

## 📐 Pin Configuration

| Component     | Arduino Pin |
|---------------|-------------|
| IR Left       | A0          |
| IR Right      | A1          |
| Echo (Ultrasonic) | 3       |
| Trigger (Ultrasonic) | 2    |
| Servo Motor   | 11          |
| RGB LED       | R:12, G:1, B:4 |
| Buzzer        | 13          |
| Motor Pins    | IN1:6, IN2:7, IN3:8, IN4:9 |
| Enable Pins   | ENA:10, ENB:5 |

---

## 🧠 Code Functionality

- **Line Tracking**: Uses IR sensors to detect black/white lines and direct the motors accordingly.
- **Obstacle Detection**: Uses an ultrasonic sensor mounted on a servo to scan in front and to both sides.
- **Avoidance Logic**: Upon detecting an obstacle, the robot stops, scans left/right, and chooses a free path.
- **Multicolor RGB**: Displays a sequence via RGB LED.
- **Sound Feedback**: Emits a buzzer sound upon obstacle detection.

---

## 🛠 How It Works

1. Robot is powered on using 18650 Li-thium batteries.
2. Sensors detect black line and move forward accordingly.
3. If an obstacle is detected within 20 cm:
   - The robot stops.
   - Servo rotates ultrasonic sensor left and right.
   - The robot chooses a clear path and resumes line following.
4. RGB LED cycles through colors during operation.

---

## 💻 Code Snippet (Initialization)

```cpp
void setup() {
  pinMode(R,OUTPUT);
  pinMode(B,OUTPUT);
  pinMode(G,OUTPUT);
  pinMode(buzzerPin,OUTPUT);
  Serial.begin(9600);
  pinMode(echo, INPUT);
  pinMode(trigger, OUTPUT);
  myservo.attach(servo);
  myservo.write(70);
  pinMode(MOT0, OUTPUT); pinMode(MOT1, OUTPUT);
  pinMode(MOT2, OUTPUT); pinMode(MOT3, OUTPUT);
  pinMode(IRL, INPUT); pinMode(IRR, INPUT);
  analogWrite(pwmA, 150); analogWrite(pwmB, 150);
}
```

## 🎯 Usage Scenarios

- Follows curved or Straight lines
- Avoids obstacles 
- Emits alerts and color indicators

---


