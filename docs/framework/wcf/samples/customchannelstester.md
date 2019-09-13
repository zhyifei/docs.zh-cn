---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 0d77af319e18868ce7d600269cd9afaa0c4ce2c6
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928648"
---
# <a name="customchannelstester"></a>CustomChannelsTester
`CustomChannelsTester` 是一个可用于依据一组预定义的服务协定测试自定义通道实现的工具。 可以通过使用 XML 文件选择这组服务协定并将其传递给该工具。 然后，该工具将生成服务和客户端，该客户端会在消息交换过程中测试您的自定义通道实现。  
  
### <a name="to-build-the-tool"></a>生成工具  
  
1. 若要生成解决方案，请按照[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
2. 生成解决方案将生成三个文件：Customchannelstester.exe、Testspec.xml 和 Samplerun.cmd。 文件 samplerun.cmd 提供了一个示例命令行，说明如何使用此工具来测试[传输：UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。  
  
### <a name="to-run-the-tool"></a>运行此工具  
  
- 在命令提示符处，键入下列命令：  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     需要使用 `/binding` 选项。  
  
     `/dll`如果 "绑定" 不是由 Windows Communication Foundation （WCF）提供的系统提供的绑定，则是必需的。  
  
     `/testspec` 是可选的。  
  
     这将根据测试规范和绑定创建服务器和客户端。  
  
     执行该客户端和服务器并返回结果。  
  
     下面是用于描述测试规范的示例 XML (testspec.xml)：  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
