# COMMANDLINE PURESTORAGE 


> BIR VOLUME'IN DATA DEGERLERI ICIN KULLANILABILIR SON 90 GUN ORNEK OLARAK KULLANILDI 
```
purevol list --historical 90d --space < volume name >
```

Output:

Time                     Name             Size  Thin Provisioning  Data Reduction  Total Reduction  Unique   Snapshots  Total

2023-01-21 17:58:03 +03  < volume name >  850G  -                  2.9 to 1          -                241.01G  0.00       241.01G


#+---------+------------+-------------------------------+------------+----------------------+---------------++

> ARRAY'IN SON IOPS DEGERLERINE ERISIM ICIN KULLANILABILIR ARALIK OLARAK BU DEGERLER SECILMELI (choose from '1h', '3h', '24h', '7d', '30d', '90d', '1y')
```
purearray monitor --historical 1h
```

Output:

Time                     B/s (read)  B/s (write)  op/s (read)  op/s (write)  us/op (read)  us/op (write)  Queue us/op
2023-01-21 22:20:02 +03  86.04M      568.49M      3.42K        21.42K        688           234            6
2023-01-21 22:20:32 +03  60.06M      568.89M      3.31K        23.29K        654           229            5



#+---------+------------+-------------------------------+------------+----------------------+---------------++

> DAHA ONCE OLUSTURULMUS VOLUME'LERIN KOMUT SATIRINDAN NASIL OLUŞTURULACAGINI GORMEK ICIN BU KOMUT KULLANILABILIR
```
purevol list --cli
```

Output:

purevol create --size 850G VOL1

purevol create --size 750G VOL2

purevol create --size 700G VOL3


