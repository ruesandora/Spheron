# Spheron

> Shpheron Network'ün Fizz Node'unu kurdum, bir süredir test ediyorum sorunsuz bir şekilde puan kazanıyorum gördüğünüz gibi.

<img width="933" alt="Ekran Resmi 2024-10-04 22 19 25" src="https://github.com/user-attachments/assets/717f26b1-4a10-475f-ba9b-f5e488127e06">

> Donanım olarak 4 vCPU 8 RAM bir sunucu kullandım.

> Kurulumu hatırladığım kadarıyla yazıyorum 3 gün önce kurdum net aklımda değil her step, zaten kolay yaparsınız siz.

# Kurulum

> [Buradan](https://fizz.spheron.network/) cüzdanınızı bağlıyorsunuz.

> Sonra ilerlemeniz gereken bir kaç step var onları tamamlayıp node kurulum sayfasına geçiyorsunuz.

> Sonra lokasyonunuza yakın olan (sunucu lokasyonu) bir provider seçiniz ve görseldeki setup kısmına geliniz.

<img width="790" alt="Ekran Resmi 2024-10-04 22 29 00" src="https://github.com/user-attachments/assets/c1bde16d-56c4-4da1-920a-113d6aba9a44">

> Setup dosyasını indiirp sunucunuzun içine atınız (WinSCP gibi bir program ile veya termius)

```console
# komutlarımızı tek tek girelim
sudo apt install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io

sudo systemctl start docker
sudo systemctl enable docker

sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

sudo fallocate -l 4096M /swapfile

sudo chmod 600 /swapfile

sudo mkswap /swapfile

sudo swapon /swapfile
```

```console
# dosya izinlerini verelim
chmod +x /root/fizzup.sh

screen -S fizz

# iki komuttan birisi ile başlatabilirsiiz.
bash /root/fizzup.sh
sh /root/fizzup.sh
```


```console
#log kontrol
docker compose -f ~/.spheron/fizz/docker-compose.yml logs -f
```

> Fazla detay ekleyemedim şimdilik bu kadar, eksik varsa sabah/gece düzenlerim. Yorumsuz bir repo için üzgünüm gn.







