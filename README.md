# Soal test maggang Backend engineer dengan Springboot

Berikut adalah soal/pertanyaan yang perlu dijawab oleh peserta maggang

## knowledge base

1. Apa yang anda ketahui tentang Bare Metal?
   - Bare Metal adalah server layanan bentuk awan yang konsumen dapat sewa dari penyedia. Server ini yang tidak dapat digunakan bersama dengan konsumen lain.   Berbasis   mesin virtual, server tidak disertai hypervisor yang sudah terinstal dan memberikan kontrol penuh atas infrastruktur server mereka. Selain itu memiliki fleksibilitas     untuk memilih sistem operasinya, menghindari tantangan pengguna lain yang bising akibat infrastruktur bersama, dan menyempurnakan perangkat keras dan perangkat lunak    untuk beban kerja spesifik yang seringkali membutuhkan banyak data. Bersamaan dengan mesin virtual, jaringan,  dan penyimpanan , server bare metal merupakan komponen mendasar dari tumpukan infrastruktur-sebagai-layanan (IaaS) dalam komputasi awan.
   
2. Apa yang anda ketahui tentang konsep jaringan VLAN?
   - VLAN (Virtual Local Area Network) merupakan metode pemisahan atau segmentasi jaringan fisik menjadi beberapa jaringan logis. Sehingga memudahkan administrator jaringan untuk melakukan perawatan, fleksibilitas, dan skalabilitas jaringan. Sehingga menghasikan jaringan yang optimal dan lalu lintas jaringan terjaga dengan baik.
   - Jenis -jenis VLAN :
     1. Default VLAN 
     2. Data VLAN
     3. Native Vlan
     4. Management VLAN
     5. Voice VLAN
   
3. Apa yang anda ketahui tentang IPMI / Ip Management pada server?
   - IP Managemnet pada server adalah tools atau metode yang digunakan administrator jaringan untuk mengelola, melacak, dan merancang IP sehingga dapat mengetahui alamat IP pengguna. Jenisnya ada subnetting, routing, dinamic routing, static routing, dan penerapan VLSM. 
   
4. Pernahkah anda mendesign suatu jaringan pada suatu kantor/perusahaan/campus sebutkan dan jelaskan?
   Sudah pernah.
   Skenario : Sebuah perusahaan memumpunyai 3 gedung A,B, dan C yang harus terhubung  jaringan agar memudahkan dalam melakukan koordinasi.
   Solusi : Menggunakan IP management routing lalu pada gedung B menggunakan OSPF istilahnya sebagai jembatan penghubung gedung A dan C.  

## Design modules

Dalam suatu kantor terdapat 3 lantai yang di isi beberapa divisi seperti:

Lantai 3: 

1. IT Networking (5 orang)
   - VLAN 10
   - Gateway : 192.168.10.1
   - DHCP IP Range : 192.168.10.2 - 192.168.10.6
     
3. Server Aplikasi (10 server)
   - VLAN 20
   - Gateway : 192.168.20.1
   - DHCP IP Range : 192.168.20.2 - 192.168.20.11
     
5. Server Database (5 server)
   - VLAN 30
   - Gateway : 192.168.30.1
   - DHCP IP Range : 192.168.30.2 - 192.168.30.6

Lantai 2:
2. Developer/programmer (200 orang)
   - VLAN 40
   - Gateway : 192.168.40.1
   - DHCP IP Range : 192.168.40.2 - 192.168.40.201
     
3. Database engineer (50 orang)
   - VLAN 50
   - Gateway : 192.168.50.1
   - DHCP IP Range : 192.168.50.2 - 192.168.50.51
     
5. QA/QC engineer (50 orang)
    - VLAN 60
   - Gateway : 192.168.60.1
   - DHCP IP Range : 192.168.60.2 - 192.168.60.51

Lantai 1:
5. Manager (10 orang)
   - VLAN 70
   - Gateway : 192.168.70.1
   - DHCP IP Range : 192.168.70.2 - 192.168.70.11
     
6. Front office (8 orang)
   - VLAN 80
   - Gateway : 192.168.80.1
   - DHCP IP Range : 192.168.80.2 - 192.168.80.9

Ketentuan ACL list :
1. VLAN 20
   - Allow access dari VLAN 40, VLAN 70, VLAN 80, VLAN 10
   - Deny selain VLAN diatas.
2. VLAN 30
   - Allow access dari VLAN 10, VLAN 40, VLAN 50
   - Deny selain VLAN diatas
3. VLAN 70 dan VLAN 80
   - Allow access VLAN 20
   - Deny access VLAN lainnya
4. VLAN 10
   - Allow access ke semua VLAN. 


