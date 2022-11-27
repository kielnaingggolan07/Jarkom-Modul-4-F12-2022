# Jarkom-Modul-4-F12-2022

Nama Anggota | NRP
------------------- | --------------
Hesekiel Nainggolan | 5025201054
Khuria Khusna | 5025201053
Afiq Akram | 5025201270


# Soal

![soal shift 4 1](https://user-images.githubusercontent.com/103357229/203995895-d9ce437d-91ad-48c3-8c6a-47ab90fbf29b.png)

> Keterangan:

- Prefix kelompok: 192.205
- Pada Cisco menggunakan metode classless VLSM
- Pada GNS3 menggunakan metode classless CIDR

# VLSM dengan Cisco


## Pembuatan Topologi 

> Pembuatan topologi dibuat sesuai dengan arahan modul, perbedaan hanya ada pada port tambahan pada beberapa router. sebagai contoh, router `the Resonance` memerlukan 3 port tambahan. Hanya ada pilihan 1, 2, 4, dst port, maka kita tambahkan 4 port dengan `NM-4E`. Sesuai dengan gambar berikut:

<img width="628" alt="img1" src="https://user-images.githubusercontent.com/94334247/204120039-ff81210b-daa2-4858-936a-3a007526627d.PNG">

> Hasil topologi sebagai berikut:

<img width="628" alt="img1" src="https://user-images.githubusercontent.com/94334247/204120032-dce9e224-7f7c-47c4-8f7c-2511a19f32be.PNG">


## Subnetting

### Pembagian IP

![Diagram Tanpa Judul drawio](https://user-images.githubusercontent.com/94334247/204125617-aca39cee-5a68-4fa9-ae0e-4c6d7d29c817.png)

> Dari pembagian IP tersebut bisa didapati tabel sebagai berikut:
			
![image](https://user-images.githubusercontent.com/94334247/204120055-456c6c3a-b1d7-46cf-bf51-f2aa8d112036.png)

### Konfigurasi

> dari tabel di atas, maka bisa kita implementasikan pada router, PC, dan server yang ada. Kemudian lakukan konfigurasi berdasarkan ip dari tabel tersebut.

## Routing

> Routing dilakukan dengan menambahkan static routing pada setiap router yang ada

### the Refonance

```
192.205.6.0/23 via 192.205.0.18
192.205.0.64/26 via 192.205.0.13
192.205.8.0/24 via 192.205.0.13
192.205.2.0/24 via 192.205.0.13
192.205.0.24/30 via 192.205.0.13
192.205.0.128/25 via 192.205.0.22
192.205.0.28/30 via 192.205.0.22
192.205.1.0/25 via 192.205.0.22
192.205.1.128/25 via 192.205.0.22
192.205.0.32/30 via 192.205.0.22
192.205.3.0/24 via 192.205.0.22
192.205.4.0/24 via 192.205.0.22
192.205.0.4/30 via 192.205.0.22

```

### the Magical

```
0.0.0.0/0 via 192.205.0.17
```

### the Order

```
0.0.0.0/0 via 192.205.0.14
192.205.8.0/30 via 192.205.0.9
192.205.0.24/30 via 192.205.0.9
192.205.2.0/24 via 192.205.0.9

```

### the Minister

```
0.0.0.0/0 via 192.205.0.10
192.205.2.0/24 via 192.205.0.26
```

### the Dauntless

```
0.0.0.0/0 via 192.205.0.25
```

### the Instrument

```
0.0.0.0/0 via 192.205.0.21
192.205.1.0/25 via 192.205.0.30
192.205.1.128/25 via 192.205.0.30
192.205.3.0/24 via 192.205.0.34
192.205.4.0/24 via 192.205.0.34
192.205.0.4/30 via 192.205.0.34
```

### the Profound

```
0.0.0.0/0 via 192.205.0.129
```

### the FireFist

```
0.0.0.0/0 via 192.205.0.33
192.205.0.4/30 via 192.205.3.3
```

### the Queen

```
0.0.0.0/0 via 192.205.3.1
```

## Testing

> Testing dapat dilakukan dengan melakukan message dari node satu ke node lainnya. Berikut hasil tangkap dari beberapa percobaan yang dilakukan. (Apabila pada file PKT yang tertaut masih menghasilkan failed, maka harap tunggu dan bisa dicoba lagi)
![image](https://user-images.githubusercontent.com/94334247/204120349-5669be32-a023-4497-a0a4-a4cd571f7ba3.png)

