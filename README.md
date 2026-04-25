# Enterprise Network & Security Lab

## Giới thiệu

Dự án mô phỏng hệ thống mạng doanh nghiệp với nhiều phòng ban (IT, HR, FINANCE, SALE), sử dụng VLAN, routing và firewall để kiểm soát truy cập giữa các phòng ban.

---

## Topology

![Network Diagram](network-diagram.png hoặc network-diagram.jpg ✔.jpg)

---

## Phân chia mạng

| Phòng ban | VLAN | IP |
|----------|------|------|
| IT       | 10   | 192.168.10.0/24 |
| HR       | 20   | 192.168.20.0/24 |
| FINANCE  | 30   | 192.168.30.0/24 |
| SALE     | 40   | 192.168.40.0/24 |

---

## Công nghệ sử dụng

- VLAN, Trunking
- Inter-VLAN Routing (Layer 3 Switch)
- Static Routing
- Cisco ASA Firewall
- ACL (Access Control List)

---

## Chính sách bảo mật

- IT truy cập được tất cả
- HR bị chặn truy cập FINANCE
- SALE bị chặn truy cập HR và FINANCE

---

## Kiểm thử hệ thống

### ✔ Ping thành công

#### IT → HR
![IT-HR](screenshots/Ping IT-HR.png)

#### IT → FINANCE
![IT-FIN](screenshots/Ping IT-FIN .png)

#### IT → SALE
![IT-SALE](screenshots/Ping IT-SALE.png)

---

### ❌ Ping bị chặn (ACL)

#### HR → FINANCE
![HR-FIN](screenshots/Ping HR-FIN = false (chặn bởi ACL).png)

#### SALE → FINANCE
![SALE-FIN](screenshots/Ping SALE - FIN = false(chặn bởi ACL).png)

#### SALE → HR
![SALE-HR](screenshots/Ping SALE - HR = false(chặn bởi ACL).png)

---

## Kết luận

- Hệ thống hoạt động đúng theo thiết kế
- VLAN và routing hoạt động ổn định
- ACL đã chặn đúng các truy cập không hợp lệ
