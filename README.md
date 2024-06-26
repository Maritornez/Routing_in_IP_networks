# Routing_in_IP_networks
Cisco Packet Tracer project

# Цель работы
Познакомиться с основами конфигурирования статической маршрутизации.

# Ход работы
![изображение](https://github.com/Maritornez/Routing_in_IP_networks/assets/62441435/1f11d155-f29a-4760-9e6a-d5e9c0e26106)

Рисунок 1 — Схема сети

## 1.	Составим таблицы маршрутизации для каждого из маршрутизаторов.
### Таблица маршрутизации маршрутизатора R1:
|     Сеть    |     Адрес сети       |     Маска                      |     Шлюз                        |     Интерфейс                   |     Метрика    |
|-------------|----------------------|--------------------------------|---------------------------------|---------------------------------|----------------|
|     1       |     159.14.18.128    |     /28     255.255.255.240    |     R1 (1)     159.14.18.129    |     R1 (1)     159.14.18.129    |     0          |
|     2       |     159.14.18.0      |     /26     255.255.255.192    |     R2 (1)     159.14.18.130    |     R1 (1)     159.14.18.129    |     1          |
|     3       |     159.14.18.144    |     /28     255.255.255.240    |     R1 (2)     159.14.18.145    |     R1 (2)     159.14.18.145    |     0          |
|     4       |     159.14.18.64     |     /26     255.255.255.192    |     R3 (1)     159.14.18.146    |     R1 (2)     159.14.18.145    |     1          |
|     5       |     159.14.18.160    |     /27     255.255.255.224    |     R2 (1)     159.14.18.130    |     R1 (1)     159.14.18.129    |     2          |
|     6       |     159.14.19.0      |     /27     255.255.255.224    |     R3 (1)     159.14.18.146    |     R1 (2)     159.14.18.145    |     1          |
|     7       |     159.14.19.32     |     /28     255.255.255.240    |     R3 (1)     159.14.18.146    |     R1 (2)     159.14.18.145    |     2          |

### Таблица маршрутизации маршрутизатора R2:
|     Сеть    |     Адрес сети       |     Маска                      |     Шлюз                        |     Интерфейс                   |     Метрика    |
|-------------|----------------------|--------------------------------|---------------------------------|---------------------------------|----------------|
|     1       |     159.14.18.128    |     /28     255.255.255.240    |     R2 (1)     159.14.18.130    |     R2 (1)     159.14.18.130    |     0          |
|     2       |     159.14.18.0      |     /26     255.255.255.192    |     R2 (2)     159.14.18.1      |     R2 (2)     159.14.18.1      |     0          |
|     3       |     159.14.18.144    |     /28     255.255.255.240    |     R1 (1)     159.14.18.129    |     R2 (1)     159.14.18.130    |     1          |
|     4       |     159.14.18.64     |     /26     255.255.255.192    |     R4 (1)     159.14.18.2      |     R2 (2)     159.14.18.1      |     1          |
|     5       |     159.14.18.160    |     /27     255.255.255.224    |     R4 (1)     159.14.18.2      |     R2 (2)     159.14.18.1      |     1          |
|     6       |     159.14.19.0      |     /27     255.255.255.224    |     R1 (1)     159.14.18.129    |     R2 (1)     159.14.18.130    |     2          |
|     7       |     159.14.19.32     |     /28     255.255.255.240    |     R4 (1)     159.14.18.2      |     R2 (2)     159.14.18.1      |     1          |

### Таблица маршрутизации маршрутизатора R3:
|     Сеть    |     Адрес сети       |     Маска                      |     Шлюз                        |     Интерфейс                   |     Метрика    |
|-------------|----------------------|--------------------------------|---------------------------------|---------------------------------|----------------|
|     1       |     159.14.18.128    |     /28     255.255.255.240    |     R1 (2)     159.14.18.145    |     R3 (1)     159.14.18.146    |     1          |
|     2       |     159.14.18.0      |     /26     255.255.255.192    |     R4 (4)     159.14.18.66     |     R3 (2)     159.14.18.65     |     1          |
|     3       |     159.14.18.144    |     /28     255.255.255.240    |     R3 (1)     159.14.18.146    |     R3 (1)     159.14.18.146    |     0          |
|     4       |     159.14.18.64     |     /26     255.255.255.192    |     R3 (2)     159.14.18.65     |     R3 (2)     159.14.18.65     |     0          |
|     5       |     159.14.18.160    |     /27     255.255.255.224    |     R4 (4)     159.14.18.66     |     R3 (2)     159.14.18.65     |     1          |
|     6       |     159.14.19.0      |     /27     255.255.255.224    |     R3 (3)     159.14.19.1      |     R3 (3)     159.14.19.1      |     0          |
|     7       |     159.14.19.32     |     /28     255.255.255.240    |     R4 (4)     159.14.18.66     |     R3 (2)     159.14.18.65     |     1          |

### Таблица маршрутизации маршрутизатора R4:
|     Сеть    |     Адрес сети       |     Маска                      |     Шлюз                        |     Интерфейс                   |     Метрика    |
|-------------|----------------------|--------------------------------|---------------------------------|---------------------------------|----------------|
|     1       |     159.14.18.128    |     /28     255.255.255.240    |     R2 (2)     159.14.18.1      |     R4 (1)     159.14.18.2      |     1          |
|     2       |     159.14.18.0      |     /26     255.255.255.192    |     R4 (1)     159.14.18.2      |     R4 (1)     159.14.18.2      |     0          |
|     3       |     159.14.18.144    |     /28     255.255.255.240    |     R3 (2)     159.14.18.65     |     R4 (4)     159.14.18.66     |     1          |
|     4       |     159.14.18.64     |     /26     255.255.255.192    |     R4 (4)     159.14.18.66     |     R4 (4)     159.14.18.66     |     0          |
|     5       |     159.14.18.160    |     /27     255.255.255.224    |     R4 (2)     159.14.18.161    |     R4 (2)     159.14.18.161    |     0          |
|     6       |     159.14.19.0      |     /27     255.255.255.224    |     R3 (2)     159.14.18.65     |     R4 (4)     159.14.18.66     |     1          |
|     7       |     159.14.19.32     |     /28     255.255.255.240    |     R4 (3)     159.14.19.33     |     R4 (3)     159.14.19.33     |     0          |

### Таблица маршрутизации маршрутизатора R5:
|     Сеть    |     Адрес сети       |     Маска                      |     Шлюз                       |     Интерфейс                  |     Метрика    |
|-------------|----------------------|--------------------------------|--------------------------------|--------------------------------|----------------|
|     1       |     159.14.18.128    |     /28     255.255.255.240    |     R3 (3)     159.14.19.1     |     R5 (1)     159.14.19.2     |     2          |
|     2       |     159.14.18.0      |     /26     255.255.255.192    |     R4 (3)     159.14.19.33    |     R5 (2)     159.14.19.34    |     1          |
|     3       |     159.14.18.144    |     /28     255.255.255.240    |     R3 (3)     159.14.19.1     |     R5 (1)     159.14.19.2     |     1          |
|     4       |     159.14.18.64     |     /26     255.255.255.192    |     R3 (3)     159.14.19.1     |     R5 (1)     159.14.19.2     |     1          |
|     5       |     159.14.18.160    |     /27     255.255.255.224    |     R4 (3)     159.14.19.33    |     R5 (2)     159.14.19.34    |     1          |
|     6       |     159.14.19.0      |     /27     255.255.255.224    |     R5 (1)     159.14.19.2     |     R5 (1)     159.14.19.2     |     0          |
|     7       |     159.14.19.32     |     /28     255.255.255.240    |     R5 (2)     159.14.19.34    |     R5 (2)     159.14.19.34    |     0          |

## 2.	Присвоим каждому компьютеру IP-адрес, маску сети (в соответствии с подсетью) и шлюз на любой маршрутизатор, к которому подключен коммутатор, соединенный с данным компьютером (рисунок 2).
## 3.	Установим портам маршрутизаторов IP-адреса и маски.

# Топология сети из Cisco Packet Tracer 
![319300059-ee9be984-f510-44ce-9168-548a17e8bc0a_Nero AI_Business_x4](https://github.com/Maritornez/Routing_in_IP_networks/assets/62441435/37aad2b2-59bd-4709-96b4-ef9b94f1bc43)


# Таблицы маршрутизации со всех маршрутизаторов
Узнаем таблицы маршрутизации с помощью команды show ip route.


R1
```
159.14.0.0/16 is variably subnetted, 9 subnets, 4 masks
S 159.14.18.0/26 [1/0] via 159.14.18.130
S 159.14.18.64/26 [1/0] via 159.14.18.146
C 159.14.18.128/28 is directly connected, FastEthernet0/0
L 159.14.18.129/32 is directly connected, FastEthernet0/0
C 159.14.18.144/28 is directly connected, FastEthernet0/1
L 159.14.18.145/32 is directly connected, FastEthernet0/1
S 159.14.18.160/27 [1/0] via 159.14.18.130
S 159.14.19.0/27 [1/0] via 159.14.18.146
S 159.14.19.32/28 [1/0] via 159.14.18.146
```


R2
```
159.14.0.0/16 is variably subnetted, 9 subnets, 4 masks
C 159.14.18.0/26 is directly connected, FastEthernet0/1
L 159.14.18.1/32 is directly connected, FastEthernet0/1
S 159.14.18.64/26 [1/0] via 159.14.18.2
C 159.14.18.128/28 is directly connected, FastEthernet0/0
L 159.14.18.130/32 is directly connected, FastEthernet0/0
S 159.14.18.144/28 [1/0] via 159.14.18.129
S 159.14.18.160/27 [1/0] via 159.14.18.2
S 159.14.19.0/27 [1/0] via 159.14.18.129
S 159.14.19.32/28 [1/0] via 159.14.18.2
```

R3
```
159.14.0.0/16 is variably subnetted, 10 subnets, 4 masks
S 159.14.18.0/26 [1/0] via 159.14.18.66
C 159.14.18.64/26 is directly connected, FastEthernet0/1
L 159.14.18.65/32 is directly connected, FastEthernet0/1
S 159.14.18.128/28 [1/0] via 159.14.18.145
C 159.14.18.144/28 is directly connected, FastEthernet0/0
L 159.14.18.146/32 is directly connected, FastEthernet0/0
S 159.14.18.160/27 [1/0] via 159.14.18.66
C 159.14.19.0/27 is directly connected, FastEthernet1/0
L 159.14.19.1/32 is directly connected, FastEthernet1/0
S 159.14.19.32/28 [1/0] via 159.14.18.66
```

R4
```
159.14.0.0/16 is variably subnetted, 11 subnets, 4 masks
C 159.14.18.0/26 is directly connected, FastEthernet0/0
L 159.14.18.2/32 is directly connected, FastEthernet0/0
C 159.14.18.64/26 is directly connected, FastEthernet1/1
L 159.14.18.66/32 is directly connected, FastEthernet1/1
S 159.14.18.128/28 [1/0] via 159.14.18.1
S 159.14.18.144/28 [1/0] via 159.14.18.65
C 159.14.18.160/27 is directly connected, FastEthernet0/1
L 159.14.18.161/32 is directly connected, FastEthernet0/1
S 159.14.19.0/27 [1/0] via 159.14.18.65
C 159.14.19.32/28 is directly connected, FastEthernet1/0
L 159.14.19.33/32 is directly connected, FastEthernet1/0
```

R5
```
159.14.0.0/16 is variably subnetted, 9 subnets, 4 masks
S 159.14.18.0/26 [1/0] via 159.14.19.33
S 159.14.18.64/26 [1/0] via 159.14.19.1
S 159.14.18.128/28 [1/0] via 159.14.19.1
S 159.14.18.144/28 [1/0] via 159.14.19.1
S 159.14.18.160/27 [1/0] via 159.14.19.33
C 159.14.19.0/27 is directly connected, FastEthernet0/0
L 159.14.19.2/32 is directly connected, FastEthernet0/0
C 159.14.19.32/28 is directly connected, FastEthernet0/1
L 159.14.19.34/32 is directly connected, FastEthernet0/1
```
