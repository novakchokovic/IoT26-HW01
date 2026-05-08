# 5월 6일 16:00~18:00

1. sd카드에 라즈베리파이 os 깔기
username: iot
hostname: 임현준의 iPhone
             pw: abcd1234         으로 설정
2. ssh 연결 시도
→실패
-실패원인) 핫스팟 신호가 약해 불안정한 네트워크였음.
                    putty를 활용하려고 하였지만 호환 오류가 발생하였음.
→다음날 개인카페에서 보안 네트워크 사용하기로 함.

# 5월 7일 13:00~16:00

1. sd카드에 라즈베리파이 os 깔기
username: pi
hostname: raspberrypi
             pw: 김민준         으로 설정
2. ssh 연결 시도
-1) sd카드 부트에 ssh 파일 만들고
-2) sd카드 부트에 wpa_supplicant.conf 설정 파일 만들고
      다음과 같은 코드 넣기
    
    > ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
    update_config=1
    country=KR
    network={
    ssid="U+NetD49C_5G"
    psk="4AJACE#679"
    key_mgmt=WPA-PSK
    }
    > 
    
    →성공
    
    [처음으로 ssh 접속한 순간](attachment:ce644c28-7fb9-4ec8-a0fd-416888029da2:KakaoTalk_20260508_214539704.mp4)
    
    처음으로 ssh 접속한 순간
    

![개인카페 보안네트워크](attachment:dbe2a0c1-456f-4f59-ae0e-9cb089b5915e:KakaoTalk_20260508_214533214.jpg)

개인카페 보안네트워크

## **Control Raspberry Pi Digital Outputs with Python (LED)**

### 1. 조립하기

- 홈페이지를 참고하여 똑같이 만들

### 2. Python 파일 만들기

- nano blinking_led.py

### **3.** 코드 작성

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

![나노 편집기에서 코드를 저장한 모습](attachment:44598619-bd59-4547-8156-9f462b2c75f0:7986c9ac-84b9-4330-8f79-b0e87a13c4f0.png)

나노 편집기에서 코드를 저장한 모습

### 4. 실행

- python3 blinking_led.py

[실행했을때 작동되는 모습](attachment:3295afe1-334d-4fab-b391-6f09d55f437f:KakaoTalk_20260508_214538228.mp4)

실행했을때 작동되는 모습
