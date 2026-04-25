# Enterprise Network & Security Lab

## Giới thiệu

Dự án mô phỏng hệ thống mạng doanh nghiệp sử dụng Cisco Packet Tracer và VMware, với mục tiêu xây dựng một kiến trúc mạng hoàn chỉnh bao gồm phân tách VLAN, định tuyến liên VLAN (Inter-VLAN Routing) và triển khai các chính sách bảo mật bằng firewall và ACL.

Hệ thống được thiết kế theo mô hình thực tế của doanh nghiệp với nhiều phòng ban và kiểm soát truy cập giữa các phòng ban.

---

## Mô hình mạng (Topology)

![Network Diagram](topology/network-diagram.png)

---

## Kiến trúc hệ thống

- Core Layer: Switch Layer 3 (Cisco 3560) thực hiện routing giữa các VLAN
- Access Layer: Các switch Layer 2 (Cisco 2960) cho từng phòng ban
- Firewall: Cisco ASA kiểm soát truy cập giữa mạng nội bộ và router
- Router: Kết nối ra mạng ngoài (WAN)

---

## Phân chia VLAN

| Phòng ban | VLAN | Subnet |
|----------|------|--------|
| IT       | 10   | 192.168.10.0/24 |
| HR       | 20   | 192.168.20.0/24 |
| FINANCE  | 30   | 192.168.30.0/24 |
| SALE     | 40   | 192.168.40.0/24 |

---

## Công nghệ sử dụng

- VLAN & Trunking (802.1Q)
- Inter-VLAN Routing (Layer 3 Switch)
- Static Routing
- Cisco ASA Firewall
- Access Control List (ACL)
- ICMP testing (ping)

---

## Chính sách bảo mật (Security Policy)

Hệ thống được cấu hình với các quy tắc kiểm soát truy cập như sau:

- IT có toàn quyền truy cập đến các phòng ban khác
- HR không được truy cập FINANCE
- SALE không được truy cập HR và FINANCE
- Các truy cập bị chặn được thực hiện thông qua ACL trên thiết bị mạng

---

## Kiểm thử hệ thống (Testing)

### ✔ Truy cập hợp lệ

#### IT → HR
![IT to HR](screenshots/ping-it-hr.png)

#### IT → FINANCE
![IT to FIN](screenshots/ping-it-fin.png)

---

### ❌ Truy cập bị chặn (theo chính sách ACL)

#### HR → FINANCE
![HR to FIN Blocked](screenshots/ping-hr-fin-block.png)

#### SALE → HR
![SALE to HR Blocked](screenshots/ping-sale-hr-block.png)

---

## Định tuyến

- Core Switch thực hiện routing giữa các VLAN
- Firewall định tuyến giữa mạng nội bộ và router
- Router được cấu hình static route để truy cập các mạng nội bộ

---

## Kết quả đạt được

- Thiết kế thành công mô hình mạng doanh nghiệp cơ bản
- Triển khai phân tách VLAN rõ ràng
- Thực hiện routing giữa các mạng nội bộ
- Áp dụng chính sách bảo mật bằng ACL
- Kiểm thử thành công cả trường hợp cho phép và bị chặn truy cập

---

## Ghi chú

Dự án được xây dựng nhằm mục đích học tập và nâng cao kỹ năng về:
- Network Design
- System Administration
- Network Security

---

## Tác giả

- Hoai Le
