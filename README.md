# IS-IS

# Лабораторная работа: IS-IS.
# Задание:
1. Настроить IS-IS в ISP Триада
2. R23 и R25 находятся в зоне 2222
3. R24 находится в зоне 24
4. R26 находится в зоне 26
Настройка осуществляется одновременно для IPv4 и IPv6

# Решение:

# Схема сегмента сети:

![](https://github.com/dmitriyklimenkov/IS-IS/blob/main/IS-IS%20%D1%81%D1%85%D0%B5%D0%BC%D0%B0.png)

# 1. Конфигурация R23, R25.
Настройку IS-IS произведем на примере маршрутизатора R23. В режиме конфигурации запустим процесс IS-IS и внесем номер зоны и Router-id.
```
!
router isis
 net 49.2222.0023.0023.0023.00
 log-adjacency-changes
!
```
И запустим на интерфейсах:
```
!
interface Ethernet0/0
 ip router isis
 ipv6 enable
 ipv6 router isis
!
interface Ethernet0/1
 ip router isis
 ipv6 router isis
!
interface Ethernet0/2
 ip router isis
 ipv6 router isis
!
```
На R25 настройка проводится аналогично.

# 2. Конфигурация R24.
В режиме конфигурации запустим процесс IS-IS и внесем номер зоны и Router-id.
```
router isis
 net 49.0024.0024.0024.0024.00
 log-adjacency-changes
```
И запустим на интерфейсах:
```
!
interface Ethernet0/0
 ip router isis
 ipv6 router isis
!
interface Ethernet0/1
 ip router isis
 ipv6 router isis
!
interface Ethernet0/2
 ip router isis
 ipv6 router isis
!
interface Ethernet0/3
 ip router isis
 ipv6 router isis
!
```

# 3. Конфигурация R26.
В режиме конфигурации запустим процесс IS-IS и внесем номер зоны и Router-id.
```
!
router isis
 net 49.0026.0026.0026.0026.00
 log-adjacency-changes
!
```
И запустим на интерфейсах:
```
!
interface Ethernet0/0
 ip router isis
 ipv6 router isis
!
interface Ethernet0/1
 ip router isis
 ipv6 router isis
!
interface Ethernet0/2
 ip router isis
 ipv6 router isis
!
interface Ethernet0/3
 ip router isis
 ipv6 router isis
!
```
На примере R24 проверим таблицы маршрутизации IPv4 и IPv6.
![](https://github.com/dmitriyklimenkov/IS-IS/blob/main/IS-IS%20routev4.PNG)

![](https://github.com/dmitriyklimenkov/IS-IS/blob/main/IS-IS%20routev6.PNG)
