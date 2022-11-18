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

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432162-68e7828e-e917-4636-83a4-5c7969356313.png">
</p>

### BACA BAIK BAIK Jika Anda Menggunakan Ubuntu 18 - 20.04 (Instal Ini Agar Tidak Error) OPTIONAL

```
wget http://nz2.archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.16_amd64.deb
```
```
sudo dpkg -i libssl1.1_1.1.1f-1ubuntu2.16_amd64.deb
```

## 1. Instal CLI

```
sudo apt-get update
sudo apt install libssl-dev
sudo apt-get install -y tar wget curl
```
```
wget -q https://github.com/dusk-network/wallet-cli/releases/download/v0.12.0/ruskwallet0.12.0-linux-x64.tar.gz
```
```
tar -xf ruskwallet0.12.0-linux-x64.tar.gz
```
```
rm -rf ruskwallet0.12.0-linux-x64.tar.gz
```
```
cd rusk-wallet0.12.0-linux-x64
```
```
./rusk-wallet
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
- Submit Form

## 4. Install Rusk-Node

- Buka Vps kalian
- Untuk Memastikan Apakah Balance Faucet Udah Landing, Jalankan Perintah di Bawah :

```
cd rusk-wallet0.12.0-linux-x64
./rusk-wallet
```

- Arah Bawah Pilih `Replace your wallet with a lost one using the recovery phrase` dan `enter`
- Masukan Pharse Wallet kalian `Enter`
- Masukan Password Anda 2x dan `Enter`
- Balik ke VPS Arah Bawah Pilih `Back` dan `Enter`
- Arah Bawah Lagi Pilih `Exit` dan `Enter`

## 5. Instal Rusk-Node

```
cd
curl --proto '=https' --tlsv1.2 -sSf https://dusk-infra.ams3.digitaloceanspaces.com/rusk/itn-installer.sh | sh
```

## 6. Buka Port (Untuk Pengguna Azure sama DO biasanya Buka Port di Website Dasboard VPS Kalian) kalo Contabo Langsung Paste aja di Vps Kalian

```
sudo ufw allow 22
sudo ufw allow 9000:9005/udp
sudo ufw enable
```

## 7. Set password `consensus.keys` Jalankan

```
cd /root/.dusk/rusk-wallet
mv *.key /opt/dusk/conf/consensus.keys

## 8. Set Password Consensus.keys

```
echo 'DUSK_CONSENSUS_KEYS_PASS=<MASUKAN-PASWWORD-KALIAN>' > /opt/dusk/services/dusk.conf
```
  
`<MASUKAN-PASWWORD-KALIAN>` = Isi Dengan Password Kalian, Samain Aja Kaya Yang Pas Awal Buat Wallet

## Start Node

```
service rusk start
service dusk start
```

Jika Tidak Terjadi Apa Apa Berarti Sudah Benar

## 
