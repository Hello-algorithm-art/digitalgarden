---
{"dg-publish":true,"permalink":"/Boxes/地址解析协议ARP/","dgPassFrontmatter":true,"created":"2025-05-26T08:16:08.741+08:00","updated":"2025-06-02T14:24:00.650+08:00"}
---

主机和路由器如何确定在IP数据报首部加入的MAC地址，用于局域网内的传输
利用ARP高速缓存表，存放IP与MAC的映射关系

- 本局域网上广播发送ARP 请求分组，包含自身IP，自身MAC，目标IP
- 本局域网上单播发送ARP 响应分组，包含自身硬件地址



