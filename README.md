# Tutorial testnet DUSK Incentivized

<p style="font-size:14px" align="right">
<a href="https://t.me/bangpateng_airdrop" target="_blank">Join Telegram Bang Pateng<img src="https://user-images.githubusercontent.com/50621007/183283867-56b4d69f-bc6e-4939-b00a-72aa019d1aea.png" width="30"/></a>
</p>

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432156-50a53f84-3d5d-40da-950c-0d9e62c2e4b4.jpg">
</p>

## Referensi

[Dokumen resmi](https://dusk.network/pages/incentivized-testnet#Wallet)

[Minta Faucet](https://docs.google.com/forms/d/e/1FAIpQLScxABRnszbBEaTZAIg2TwfJVIq0kRggy8QK2MRBTO7vuyP_Ug/viewform)

[Server discord](https://discord.gg/dusknetwork)

## Spesifikasi

### Persyaratan perangkat keras

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|CPU|Intel Core 2|
|RAM|1 GB DDR4 RAM|
|Penyimpanan|20 GB HDD|

### Persyaratan perangkat lunak

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|Sistem Operasi|Ubuntu 22|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|Sistem Operasi|Ubuntu 22 atau lebih tinggi|

### BACA BAIK BAIK Jika Anda Menggunakan Ubuntu 18 - 20.04 (Instal Ini Agar Tidak Error) OPTIONAL

```
wget http://nz2.archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.16_amd64.deb
```
```
sudo dpkg -i libssl1.1_1.1.1f-1ubuntu2.16_amd64.deb
```

## 1. Instal CLI

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432162-68e7828e-e917-4636-83a4-5c7969356313.png">
</p>

```
sudo apt-get update
sudo apt install libssl-dev
sudo apt-get install -y tar wget curl
```
```
wget https://github.com/dusk-network/wallet-cli/releases/download/v0.13.0/ruskwallet0.13.0-linux-x64-libssl3.tar.gz
tar -xf ruskwallet0.13.0-linux-x64-libssl3.tar.gz
cd rusk-wallet0.13.0-linux-x64-libssl3
./rusk-wallet --state http://127.0.0.1:8585
```

## 2. Create Wallet

- Lalu Jika Muncul Tulisan `Create New Wallet` Klik Enter
- Masukan Password Bebas
- Masukan Password Lagi
- Copy dan Simpan Pharse Kalian
- Lalu Pilih `y` dan `Enter`
- Lalu Enter Lagi Nanti Muncul Address kalian Copy dan Simpan Juga

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432143-2ca75493-230f-441a-9389-7165b80019f0.jpg">
</p>

- Gunakan Arah Bawah Pada Keyboard Pc kalian
- Arahkan kan ke `Export Provisioner Key-Pair` dan `Enter`
- Lalu Isi Dengan Command di Bawah Ini, Tergantung Penempatan Directory anda Sendiri Kalo saya di Sini

```
/root/.dusk/rusk-wallet/
```
- Lalu `Enter` Anda Akan Melihat Gambar di Bawah Ini dan Jangan Lupa di Backup Juga Yang Ane Garis Kuning ngin

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432152-3e5578a6-9b21-4cd2-adab-8b132fd111d4.PNG">
</p>

**Noted :** Seharusnya ada dua file sekarang, file .key dan file .cpk . Jaga kerahasiaan file .key , jangan bagikan dengan siapa pun. Kami akan membutuhkan file ini nanti untuk node kami. Anggap saja seperti kunci konsensus Anda, yang Anda gunakan untuk menandatangani transaksi.

.cpk adalah kunci publik. Kami membutuhkan yang ini untuk memberi Anda akses ke testnet.


- Balik ke VPS Arah Bawah Pilih `Back` dan `Enter`
- Arah Bawah Lagi Pilih `Exit` dan `Enter`

## 3. Minta Faucet

- Isi Form Faucet : https://docs.google.com/forms/d/e/1FAIpQLScxABRnszbBEaTZAIg2TwfJVIq0kRggy8QK2MRBTO7vuyP_Ug/viewform
- Paste Address Dusk kalian
- Upload File.cpk kalian 
- Alamat Hadiah, Isi Address ETH Metamask (Ini Untuk Menerima Reward Hadiah Testnet nya Nanti)
- Submit Form dan Tunggu Keesokan Harinya

## 4. Memastikan Faucet Sudah Landing

- Buka Vps kalian
- Untuk Memastikan Apakah Balance Faucet Udah Landing, Jalankan Perintah di Bawah :

```
cd rusk-wallet0.13.0-linux-x64-libssl3
./rusk-wallet --state http://127.0.0.1:8585
```

- Arah Bawah Pilih `Replace your wallet with a lost one using the recovery phrase` dan `enter`
- Masukan Pharse Wallet kalian `Enter`
- Masukan Password Anda 2x dan `Enter`
- Balik ke VPS Arah Bawah Pilih `Back` dan `Enter`
- Arah Bawah Lagi Pilih `Exit` dan `Enter`

## 5. Instal Rusk-Node

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716202-a9687681-6daa-4a5f-b1d7-299f0d72e2f7.JPG">
</p>

```
cd
curl --proto '=https' --tlsv1.2 -sSf https://dusk-infra.ams3.digitaloceanspaces.com/rusk/itn-installer.sh | sh
```

## 6. Buka Port (Untuk Pengguna Azure sama DO biasanya Buka Port di Website Dasboard VPS Kalian) kalo Contabo Langsung Paste aja di Vps Kalian

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716199-ff3752f6-76a4-4cab-965b-3a13b7f12623.jpg">
</p>

```
sudo ufw allow 22
sudo ufw allow 8585
sudo ufw allow 9000:9005/udp
sudo ufw enable
```

## 7. Set password `consensus.keys` Jalankan

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716195-647652a1-e758-477a-850e-7c002a0102f9.jpg">
</p>

```
cd /root/.dusk/rusk-wallet
mv *.key /opt/dusk/conf/consensus.keys
```
```
echo 'DUSK_CONSENSUS_KEYS_PASS=<MASUKAN-PASWWORD-KALIAN>' > /opt/dusk/services/dusk.conf
```
  
`<MASUKAN-PASWWORD-KALIAN>` = Isi Dengan Password Kalian, Samain Aja Kaya Yang Pas Awal Buat Wallet

## 8. Start Node

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716190-b364ac77-2424-4693-b7af-37157cc9a2e9.jpg">
</p>

```
service rusk start
service dusk start
```

Jika Tidak Terjadi Apa Apa Berarti Sudah Benar

## 9. Check Log Rusk dan Dusk (Untuk Memastikan Jalan Dengan Baik)


### Cek log rusk

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716183-094af1f4-eab6-4f95-a021-45ed26c4406d.jpg">
</p>

```
tail -f /var/log/rusk.log
```

### Cek log dusk

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716177-8a814b33-8205-40ef-a4be-0fe6ee9d997c.jpg">
</p>

```
tail -f /var/log/dusk.log
```


## 10. Stake Token

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202719383-9e0c6c50-157a-4cdb-a2ee-6b55cc9c26f5.JPG">
</p>

```
cd
cd rusk-wallet0.13.0-linux-x64-libssl3
./rusk-wallet --state http://127.0.0.1:8585
```

- Pilih `Acces Wallet` dan `Enter`
- Masukan Password Kalian dan `Enter`
- Lalu `Enter` lagi
- Arah Bawah Pilih `Stake Dusk` 
- Introduce the amount of DUSK to stake: isi `25000` dan `Enter`
- Introduce the gas limit for this transaction: isi `2000000000 dan `Enter`
- Introduce the gas price for this transaction: Biarkan Bawaan Langsung `Enter` Aja
- Ketik `y` dan `Enter`
- Done

## 11. Check Staking Udah Apa Belum

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202719371-a190234a-6fa5-4174-b8c9-1918c0ebbd3a.JPG">
</p>

```
./rusk-wallet --state http://127.0.0.1:8585
```

- Pilih `Acces Wallet` dan `Enter`
- Masukan Password Kalian dan `Enter`
- Lalu `Enter` lagi
- Arah Bawah Pilih `Check existing stake` dan `Enter`
- Done

## 12. Perintah Berguna Lainnya

## Menjalankan service

### Menjalankan service rusk

```
service rusk start
```

### Menjalankan service dusk

```
service dusk start
```

## Menghentikan service

### Menghentikan service rusk

```
service rusk stop
```

### Menghentikan service dusk

```
service dusk stop
```

### Hapus Node 

```
sudo service rusk stop
sudo systemctl disable rusk
sudo service dusk stop
sudo systemctl disbale dusk
sudo rm /etc/systemd/system/rusk* -rf
sudo rm /etc/systemd/system/dusk* -rf
sudo rm -rf /opt/dusk/
rm -rf /var/log/dusk.log
rm -rf /var/log/rusk.log
rm -rf rusk-wallet0.13.0-linux-x64-libssl3
```
