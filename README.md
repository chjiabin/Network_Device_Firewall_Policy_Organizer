# Network_Device_Firewall_Policy_Organizer
一个用于梳理网络设备防火墙规则的整理器
## 设计思路
- 从配置文件中读取配置，扫描配置中的规则和策略，将扫描结果入库
- 使用数据库管理防火墙规则

## 当前实现
### Vendoor 注册
- 厂商注册器，一般不同厂商配置会有自己的特征，将这些登记到 VendorRegister.py，用于后续识别

### 规则扫描器
#### ACL scaner
- 实现一个ACL scaner引擎，和厂商无关，会判断当前 Vendor，后调用相应注册的 Vendor ACL Formater。
- ACL 规则注册，通常 ACL 形式多种多样，需要根据不同特点写处理策略，后被 Verdor 的 ACL Formatter调用。
#### Object-group scanner
- 实现一个 Object-group scaner引擎，和厂商无关，会判断当前 Vendor，后调用相应注册的 VendorObject-group Formater。
- Object-group 规则注册，通常 Object-group 形式多种多样，需要根据不同特点写处理策略，后被 Verdor 的 Object-group Formatter调用。

