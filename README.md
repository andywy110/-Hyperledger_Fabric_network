# -Hyperledger_Fabric_network
AI resource allocation system Based on blockchain rescue station

Main idea:

An AI Resource allocation system, based on blockchained resuce station.

All resuce stations has a blockchain node ,which it can store all the infomation contains available resources and requirements of all refugees.

Base on that, our AI resource allocation system can calculate all the data in block nodes includes station's weather conditions, geography infomation, and so on.. and thus genering the allocation solution plan. 

## The design flow
![alt text](https://developer.ibm.com/developer/patterns/build-an-asset-leasing-application-using-blockchain-and-iot/images/flow-v4.png)
1. The smart contract is deployed to a local Hyperledger Fabric network via the IBM Blockchain Platform extension for VS Code.
2. As the asset is moved from place to place it is scanned via RFID or barcode by an IoT device. In this pattern, the device is simulated.
3. The IoT device publishes an event notification to the IBM Watson IoT Platform, which then notifies all listening applications that a scan has taken place.
4. An application listening to the IBM Watson IoT Platform for scanning events then invokes a transfer transaction.
5. The location of the asset is updated in the ledger automatically.
## 主题

本次挑战赛内容为，创造解决方案，用于提高对自然灾害的准备，并在灾害来临时加速救援。

今年的挑战是强调个人健康和社区福祉（individual health 和 community well-being），这包括但不限于：

降低疾病风险，
改善数据访问和资源可用性的解决方案，
以及解决灾害发生前，发生期间和发生后受影响者的心理健康需求
