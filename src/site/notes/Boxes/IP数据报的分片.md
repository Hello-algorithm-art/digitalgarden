---
{"dg-publish":true,"permalink":"/Boxes/IP数据报的分片/","dgPassFrontmatter":true,"created":"2025-05-27T11:03:18.533+08:00","updated":"2025-05-27T11:40:01.711+08:00"}
---

原数据共4000字节，其中首部20字节，数据部分3800字节
首部固定为20字节，若MTU=1500，
前两个分片，有效数据位1480B，1480B，最后一个分片有效数据位1020

首部片偏移字段以8B为单位，除最后一个分片，其余分片都是8B的整数倍
![file-20250527113622902.png](/img/user/images/IP%E6%95%B0%E6%8D%AE%E6%8A%A5%E7%9A%84%E5%88%86%E7%89%87/file-20250527113622902.png)