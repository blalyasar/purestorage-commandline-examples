# COMMANDLINE PURESTORAGE 


> BIR VOLUME'IN DATA DEGERLERI ICIN KULLANILABILIR SON 90 GUN ORNEK OLARAK KULLANILDI 
```
purevol list --historical 90d --space < volume name >
```

Output:

Time                     Name             Size  Thin Provisioning  Data Reduction  Total Reduction  Unique   Snapshots  Total

2023-01-21 17:58:03 +03  < volume name >  850G  -                  2.9 to 1          -                241.01G  0.00       241.01G


+---------+------------+-------------------------------+------------+----------------------+---------------++

> ARRAY'IN SON IOPS DEGERLERINE ERISIM ICIN KULLANILABILIR ARALIK OLARAK BU DEGERLER SECILMELI (choose from '1h', '3h', '24h', '7d', '30d', '90d', '1y')
```
purearray monitor --historical 1h
```

Output:

Time                     B/s (read)  B/s (write)  op/s (read)  op/s (write)  us/op (read)  us/op (write)  Queue us/op
2023-01-21 22:20:02 +03  86.04M      568.49M      3.42K        21.42K        688           234            6
2023-01-21 22:20:32 +03  60.06M      568.89M      3.31K        23.29K        654           229            5



+---------+------------+-------------------------------+------------+----------------------+---------------++

> DAHA ONCE OLUSTURULMUS VOLUME'LERIN KOMUT SATIRINDAN NASIL OLUŞTURULACAGINI GORMEK ICIN BU KOMUT KULLANILABILIR
```
purevol list --cli
```


purevol create --size 850G VOL1

purevol create --size 750G VOL2

purevol create --size 700G VOL3


+---------+------------+-------------------------------+------------+----------------------+---------------++


>  NETWORK CONTROLU SIFIR OLMASI PROBLEM OLMADIGI ANLAMINA GELIYOR
```
purenetwork fc monitor --error
```

Name     Interface Type  Time                     CRC Errors/s (rx)  Link Failures/s (rx)  Loss of Signal Errors/s (rx)  Loss of Sync Errors/s (rx)  Invalid Words/s (tx)

CT0.FC0  fc              2023-01-21 23:57:03 +03  0                  0                     0                             0                           0

CT0.FC1  fc              2023-01-21 23:57:03 +03  0                  0                     0                             0                           0




+---------+------------+-------------------------------+------------+----------------------+---------------++

> ARRAY UZERINDE LATENCY - GECIKMELERI GORMEK ICIN

```
purearray monitor --latency
```

Time                     SAN us/op (read)  Queue us/op (read)  QoS Rate Limit us/op (read)  us/op (read)  us/op cache reduction (read)  SAN us/op (write)  Queue us/op (write)  QoS Rate Limit us/op (write)  us/op (write)

2023-01-22 00:08:35 +03  253               13                  0                            897           -                             212                5                    0                             167



+---------+------------+-------------------------------+------------+----------------------+---------------++


> BUTUN VOLUME BILGILERINI CSV CIKTI OLARAK ALMAK ICIN 

```
purevol list --csv --space --sort size
```


Name,Size,Thin Provisioning,Data Reduction,Total Reduction,Unique,Snapshots,Total

VOL0,1073741824,1.0,1.0,1.0,0,0,0

VOL1,1073741824,1.0,1.0,1.0,0,0,0

VOL2,1073741824,1.0,1.0,1.0,0,0,0



+---------+------------+-------------------------------+------------+----------------------+---------------++


> Host'u listelemek ve Hosta bağlı Volume'leri listelemek

```
purehost list volname 
```

Name   WWN  IQN                                       NQN  Host Group
bilal  -    iqn.yyyy-mm-dd.x.com:xx:bilal  -    -



+---------+------------+-------------------------------+------------+----------------------+---------------++


```
purehost list volname --connect
```


Name   LUN  Vol     Host Group
Hostname  1    Vol0  -
Hostname  2    Vol1  -
Hostname  3    Vol2  -
Hostname  4    Vol3  -



