# sonarqube-vm

 วิธีที่แนะนำ (แก้ถาวร): ลบ Docker ที่ติดตั้งผ่าน Snap แล้วติดตั้งใหม่ผ่าน Docker official
🔻 ลบ Docker Snap:
```
sudo snap remove docker
```
✅ ติดตั้ง Docker แบบปกติ (จาก repo ของ Docker เอง):
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin

```
```
docker compose version
docker compose up -d
```
#  client
1. ติดตั้ง SonarScanner บน Windows
```
https://docs.sonarsource.com/sonarqube-server/10.8/analyzing-source-code/scanners/sonarscanner/
```
-แตกไฟล์ zip ไปไว้ที่เช่น C:\sonarscanner

-เพิ่ม path C:\sonarscanner\bin ไปใน Environment Variable (PATH)

🧾 2. สร้างไฟล์ sonar-project.properties ในโฟลเดอร์ htdocs
```
sonar.projectKey=my-xampp-project
sonar.projectName=XAMPP Project
sonar.projectVersion=1.0

sonar.sources=.
sonar.language=php

sonar.sourceEncoding=UTF-8
sonar.host.url=http://10.20.252.26:9000
sonar.login=YOUR_SONARQUBE_TOKEN
```

▶️ 3. เปิด Command Prompt แล้วรันคำสั่งนี้ใน htdocs:
```
cd C:\xampp\htdocs
sonar-scanner
```
จะส่งข้อมูลไปที่ SonarQube server
