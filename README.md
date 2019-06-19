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

# Asset Tracking with Blockchain and IoT

In this pattern, we will be creating a local Hyperledger Fabric network using the IBM Blockchain Platform extension for VSCode which makes it easy to start developing smart contracts. 

The solution that we will be creating is an asset lifecycle and tracking solution that keeps a record of the asset from creation to deletion. Also, we will be creating and managing asset leases which keep track of the lease terms in a lease agreement such as end date, price, and deposit amount. 

For the IoT integration, we will be leveraging the IBM Watson IoT Platform to handle device scanning at various locations as the asset is being transferred. Instead of having an actual physical device, we will be creating a web app pretending to be a device which will trigger these scans and notify a locally node.js app to invoke the updateAssetLocation transaction.

After completing this pattern you will understand how to:
- Deploy smart contracts to a local Hyperledger Fabric network
- Create a simulated IoT device using the IBM Watson IoT Platform and Node-Red
- Connect to a Hyperledger Fabric application using the Fabric SDK for Node.js
- Publish IoT events to the ledger on a device event such as a scan

# Flow
1. The smart contract is deployed to a local Hyperledger Fabric network via the IBM Blockchain Platform extension for VS Code.
2. As the asset is moved from place to place it is scanned via RFID or barcode by an IoT device. In this pattern, the device is simulated.
3. The IoT device publishes an event notification to the IBM Watson IoT Platform, which then notifies all listening applications that a scan has taken place.
4. An application listening to the IBM Watson IoT Platform for scanning events then invokes a transfer transaction.
5. The location of the asset is updated in the ledger automatically.



## Scenario
In this demo scenario we have three participants: a manufacturer, a vendor, and a contractor. 
1. The manufacturer creates the asset and sells it to the vendor. 
2. The vendor then creates a lease with the contractor which defines terms including how much deposit is to be paid and how much deposit will be returned based on the amount of damage that the asset has received during the lease duration. For example, if the asset is returned with 21% damage then only 60% of the deposit will be returned. 
3. After the lease duration is over, the asset is returned to the vendor and inspected for damage. The lease is then updated to reflect the amount of damage that the asset received.
4. The asset is sent back to the manufacturer for repairs. If the vendor has a warranty to cover future repairs with the manufacturer, the manufacturer could take a look at the history of the asset and see if any activity such as imporper usage has voided the warranty.
5. The asset is then returned to the vendor to be leased out again.


## Structure of Asset

The asset being stored in the ledger has the following properties:

- manufacturer - creator of the asset
- assetNumber - serial number given to the asset
- assetType - type of asset
- currentOwner - Who currently posesses the asset
- currentState - The current state of the asset
- percentDamage - The amount of damage in percent found during the inspection stage
- location - Where the asset was scanned last

## Structure of the Asset Lease

The asset lease being stored in the ledger has the following properties:

- leaseNumber - Lease agreement number
- lessee - Who is receiving the lease
- lessor - Who is leasing the asset out
- assetKey - The key of the asset being leased
- dateLeased - The date the lease goes into effect
- endOfLease - The end of the lease agreement
- price - The total price of the lease payments
- depositPaid - The deposit paid up front
- dateReturned - The date the asset was returned
- percentDamaged - The condition of the asset on return displayed in percent damaged
- depositReturned - Based on the ammount of damage, the amount of the deposit returned

# Prerequisites
- an IBM Cloud account
- VSCode
- The IBM Blockchain Platform extension for VSCode 
