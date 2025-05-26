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
