# Решение демонстрационного экзамена 2026 года по специальности "Сетевое и системное администрирование" 09.02.06

<br>

<p align="center"><img src="network_topology.png"></p>
<p align="center"><strong>Рис. 1. Топология сети</strong></p>

<br>

## Модуль 1. Настройка сетевой инфраструктуры

### 1. Произведите базовую настройку устройств
- Настройте имена устройств согласно топологии. Используйте полное доменное имя
- На всех устройствах необходимо сконфигурировать IPv4:
  - IP-адрес должен быть из приватного диапазона, в случае, если сеть локальная, согласно RFC1918
  - Локальная сеть в сторону HQ-SRV (VLAN 100) должна вмещать не более 32 адресов
  - Локальная сеть в сторону HQ-CLI (VLAN 200) должна вмещать не менее 16 адресов
  - Локальная сеть для управления (VLAN 999) должна вмещать не более 8 адресов
  - Локальная сеть в сторону BR-SRV должна вмещать не более 16 адресов

<br>

<details>
<summary>Решение</summary>
  
<br>

<table align="center">
  <tr>
    <td align="center">Устройство</td>
    <td align="center">Запись</td>
    <td align="center">Тип</td>
  </tr>
  <tr>
    <td align="center">HQ-RTR</td>
    <td align="center">hq-rtr.au-team.irpo</td>
    <td align="center">A, PTR</td>
  </tr>
  <tr>
    <td align="center">BR-RTR</td>
    <td align="center">br-rtr.au-team.irpo</td>
    <td align="center">A</td>
  </tr>
  <tr>
    <td align="center">HQ-SRV</td>
    <td align="center">hq-srv.au-team.irpo</td>
    <td align="center">A, PTR</td>
  </tr>
  <tr>
    <td align="center">HQ-CLI</td>
    <td align="center">hq-cli.au-team.irpo</td>
    <td align="center">A, PTR</td>
  </tr>
  <tr>
    <td align="center">BR-SRV</td>
    <td align="center">br-srv.au-team.irpo</td>
    <td align="center">A</td>
  </tr>
  <tr>
    <td align="center">ISP (интерфейс направленный в сторону HQ-RTR)</td>
    <td align="center">docker.au-team.irpo</td>
    <td align="center">A</td>
  </tr>
  <tr>
    <td align="center">ISP (интерфейс направленный в сторону BR-RTR)</td>
    <td align="center">web.au-team.irpo</td>
    <td align="center">A</td>
  </tr>
</table>
<p align="center"><strong>Табл. 1. Полное доменное имя</strong></p>

---
  
<br>

<table align="center">
  <tr>
    <td align="center">Название сети</td>
    <td align="center">IP-адрес подсети</td>
    <td align="center">Диапазон IP-адресов</td>
  </tr>
  <tr>
    <td align="center">HQ-SRV (VLAN 100)</td>
    <td align="center">192.168.100.0/27</td>
    <td align="center">192.168.100.0 - 192.168.100.31</td>
  </tr>
  <tr>
    <td align="center">HQ-CLI (VLAN 200)</td>
    <td align="center">192.168.200.0/24</td>
    <td align="center">192.168.200.0 - 192.168.200.255</td>
  </tr>
  <tr>
    <td align="center">MGMT (VLAN 999)</td>
    <td align="center">192.168.99.0/29</td>
    <td align="center">192.168.99.0 - 192.168.99.7</td>
  </tr>
  <tr>
    <td align="center">BR-SRV</td>
    <td align="center">192.168.0.0/28</td>
    <td align="center">192.168.0.0 - 192.168.0.15</td>
  </tr>
</table>
<p align="center"><strong>Табл. 2. Подсеть</strong></p>

---

<br>

#### Настройка имени устройств
</details>
