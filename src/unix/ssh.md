---
name: SSH
menu: ssh
---

## open access 

Yêu cầu đầu tiên là server phải được setup để truy cập được từ bên ngoài (giả sử có domain là kipalol.com) và phải hỗ trợ SSH.

Truy cập vào server và thêm dòng cấu hình GatewayPorts vào file /etc/ssh/sshd_config như sau:

GatewayPorts yes