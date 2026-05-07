## **Control Raspberry Pi Digital Outputs with Python (LED)**

### 1. **Creating Python Files**

- nano blinking_led.py

### **2. Writing code**

```python
from gpiozero import LED
from time import sleep

led = LED(14)

while True:
    led.on()
    print("LED ON")
    sleep(1)

    led.off()
    print("LED OFF")
    sleep(1)
```

### 3. 저장하기

- nano 에디터에서:
- Ctrl + O → 저장
- Enter
- Ctrl + X → 종료

### 4. 실행하기

- python3 blinking_led.py

### 5. 멈추기

- Ctrl + C
