# Tutorial Instalasi Taiko Node
![image](https://user-images.githubusercontent.com/101635385/210137987-bdc3fe6f-270d-40f8-b843-d927a58ca6e9.png)


<h1 align="center"> Taiko Alpha-2 Node </h1>
<h1 align="center"> Panduan instalasi Node Alpha-2 <br> 
</h1>



### Taiko Bridge:

 * [Bridge](https://bridge.a2.taiko.xyz/#/)
 * [swap](https://swap.a2.taiko.xyz/#/swap)
 * [Adding Chain](https://chainid.network/)
 * [Explorer](https://explorer.a2.taiko.xyz/)

 
 ### Linkler
 * [Kopi Hitam Telegram](https://t.me/uangdrop)
 * [Hercules Twitter](https://twitter.com/uangdrop)
 * [Taiko Dc](https://discord.gg/taikoxyz)
 
 ## 🟢 Sistem Requirement



Saran:
- CPU - 8 atau 16 cores
- Memory - 32GB RAM
- High-performance SSD with at least 1TB of free space

Selanjutnya Tinggal Copy Paste saja Command di bawah 

## 🟢 Update sistem
```shell
sudo apt update
```

```shell
sudo apt upgrade
```


## 🟢 Pengaturan Docker

```shell
apt install docker-compose
```

```shell

sudo apt-get update && sudo apt install jq && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin && sudo apt-get install docker-compose-plugin

```


## 🟢 1. Download file dari Github Taiko

```
git clone https://github.com/taikoxyz/simple-taiko-node.git
```

Membuat Layar
```
screen -S taiko
```

Buka Folder Taiko
```
cd simple-taiko-node
```

Membuat file ".env" 

```
cp .env.sample .env
```

Buka file ".env", Disini ada beberapa yang perlu dirubah.. <br>

```
nano .env
```

<br><br>

Sekarang kita perlu membuat RPC sepolia.  https://dashboard.blockpi.io/

![image](https://user-images.githubusercontent.com/101635385/226991770-91c96236-88be-45e6-abe1-27d24eacd65f.png)


L1_ENDPOINT_HTTP=Blockpi üzerinden alacağınız https linki<br>
L1_ENDPOINT_WS=Blockpi üzerinden alacağınız wss linki

![image](https://user-images.githubusercontent.com/101635385/226990799-a596650f-1978-4d0a-8fb2-021d07672d62.png)

<br>

![image](https://user-images.githubusercontent.com/101635385/226991109-bc633b4b-d30a-405a-90ad-667f99d48684.png)


<br><br>

ENABLE_PROVER=true yapın<br>
L1_PROVER_PRIVATE_KEY=Matemask adresinizin private keyini yazın

![image](https://user-images.githubusercontent.com/101635385/226991245-2543ea5d-5371-4fa1-be81-243dfb68413a.png)


*ctrl + x Yes diyerek kaydediyoruz. <br>

<br>




<br>

Private Key nasıl alınır sağdaki 3 noktaya tıklayın --- >> ardından hesap bilgileri --- >> Özel anahtarı dışa aktar

![image](https://user-images.githubusercontent.com/101635385/210151390-4342cbb3-5c1c-4e35-96ff-fde422ac08bb.png)

<br>

![image](https://user-images.githubusercontent.com/101635385/210151407-a7b0aa7e-ae39-47cc-b1ab-2697e0d25edf.png)





## 🟢 Çalıştırma

Bu işlem sonrası kurulum yapacak ve senkronize olmaya başlayacaktır.

```
docker compose up
```

![image](https://user-images.githubusercontent.com/101635385/226992188-1f9174f9-9b8c-4593-bbe8-ece1086d56e4.png)


## 🟢 Explorer üzerinden block görüntüleme 


 * [Explorer](https://explorer.a2.taiko.xyz//)



## 🟢 Log Görme

Eğer başta screen oluşturmadıysanız bir screen oıluşturup logları görebilirsiniz.

```
cd simple-taiko-node
docker compose logs -f
```


## 🟢 Durdurma

Bu işlem sonrası bloklar silinmez sadece node durur.

```
docker compose down
```

## 🟢 Nodeyi silme


```
docker compose down -v
cd
rm -fr simple-taiko-node
```


## 🟢 Port çakışması yaşayanlar

.env dosyasındaki portları resimdeki gibi yapın

![image](https://user-images.githubusercontent.com/101635385/226996911-78dd39d2-d08c-4630-9ae6-e7e0cae90842.png)




Artık sorunsuz çalıştırabilirsiniz. 



## 🟢 Sözleşme Oluşturma ( Bunu yapmak şart değil isterseniz yapın )

Bu işlem sonrası kurulum yapacak ve senkronize olmaya başlayacaktır.

```
curl -L https://foundry.paradigm.xyz | bash
```

![image](https://user-images.githubusercontent.com/101635385/210168053-69d942f9-65b9-44cc-a42f-32f6d086b537.png)


```
source /root/.bashrc
```

```
foundryup
```

![image](https://user-images.githubusercontent.com/101635385/210168068-bf4d800a-84e2-4c66-a65a-9f831307a6b5.png)


```
forge init hello_foundry && cd hello_foundry
```

Nodeyi kurduğunuz cüzdanın private keyini yazın 

```
forge create --legacy --rpc-url https://rpc.a2.taiko.xyz --private-key CÜZDAN-PRİVATE-KEY src/Counter.sol:Counter
```

![image](https://user-images.githubusercontent.com/101635385/210168108-94cac132-d52e-4c0f-9d90-43043e5d1a7a.png)


Sözleşme aşağıdaki gibi oluştu. Kod bölümüne gelin ve doğrulayı tıklayın bir sayfa açılacak en altta doğrula butonuna basın

![image](https://user-images.githubusercontent.com/101635385/210168140-b4b0413e-3020-46d1-8e6a-58468094abdb.png)

![image](https://user-images.githubusercontent.com/101635385/210168227-efba71d6-7e5e-40aa-91a6-b846dcdb4903.png)



Forklamayı ve beğenmeyi unutmayınız :)
