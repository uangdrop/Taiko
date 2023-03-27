

![photo_2023-03-27_08-11-38](https://user-images.githubusercontent.com/128940865/227817810-a87af886-3bb5-4371-8824-06776472fba0.jpg)



<h1 align="center"> Instal Node Taiko Alpha-2 <br> </h1>


### Taiko Bridge:

 * [Bridge](https://bridge.a2.taiko.xyz/#/)
 * [Swap](https://swap.a2.taiko.xyz/#/swap)
 * [Adding Chain](https://chainid.network/)
 * [Explorer](https://explorer.a2.taiko.xyz/)

 
 ### Link
 * [Kopi Hitam Telegram](https://t.me/uangdrop)
 * [Kopi Hitam Twitter](https://twitter.com/uangdrop)
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
![Screenshot_9](https://user-images.githubusercontent.com/128940865/227815178-3b17c5f4-d1da-41dd-a571-23b2f7aed50b.png)

<br><br>

Sekarang kita membutuhkan endpoint Sepolia L1 dan Websockets, untuk itu… <br>
⏤ Buat Akun di Alchemy : https://alchemy.com/ <br>
⏤ Buka Dasbor Klik di dropdown "Apps" lalu "Create App" <br>
⏤ Pilih Ethereum dan sepolia Testnet dan “Create Apps” <br>

![Screenshot_7](https://user-images.githubusercontent.com/128940865/227814611-329f182d-cbb0-4c55-8e05-71835ceaf2f5.png)

⏤ Buka Apps dan klik "VIEW KEYS" <br>
![Screenshot_8](https://user-images.githubusercontent.com/128940865/227814892-ac26e7d5-42bb-4c3e-ba47-3de3da3c519c.png)
<br>
⏤ Salin HTTPS dan WEBSOCKET Anda dan paste di .env yang telah di buka tadi <br>
L1_ENDPOINT_HTTP=<br>
L1_ENDPOINT_WSS=<br>
<br>
![Screenshot_10](https://user-images.githubusercontent.com/128940865/227815333-fbce24e1-420d-4082-a86a-8d80d938a350.png)

<br>

Ubah Juga yang dibawah ini : <br>

ENABLE_PROVER=true <br>
L1_PROVER_PRIVATE_KEY=isiPrivateKeyMetamask <br>
<br>
Dari False <br>
![Screenshot_12](https://user-images.githubusercontent.com/128940865/227817657-73d1146c-ae27-409b-bbca-ce59af25544e.png)
<br>
Menjadi True <br> Jangan lupa untuk memasukkan Private Key Anda
![Screenshot_11](https://user-images.githubusercontent.com/128940865/227815710-b5651b04-03ad-4225-8981-edde94d1c138.png)

LALU SIMPAN. Dengan cmd
``ctrl + x`` lalu ``Y`` es diyerek kaydediyoruz. <br>

<br>


## 🟢 RUN THE NODE

Setelah proses ini, itu akan menginstal dan mulai menyinkronkan
```
docker compose up
```
<br>
Contoh : <br>


![226992188-1f9174f9-9b8c-4593-bbe8-ece1086d56e4](https://user-images.githubusercontent.com/128940865/227816904-eed0b35b-424a-4e16-9fb9-5d09ff64c979.png)



<br><br>
## 🟢 TAMBAHAN
## 🟢 Melihat Node yang sedang berjalan

```
cd simple-taiko-node
docker compose logs -f
```


## 🟢 Stop Node

Setelah proses ini, blok tidak dihapus, hanya node yang berhenti

```
docker compose down
```

## 🟢 Menghapus node


```
docker compose down -v
cd
rm -fr simple-taiko-node
```


