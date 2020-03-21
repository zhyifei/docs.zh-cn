---
title: 不安全的 Intranet 客户端和服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: 2fa13a12a377cc16a95318367605d8b5d92769a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184689"
---
# <a name="intranet-unsecured-client-and-service"></a>不安全的 Intranet 客户端和服务
下图描述了为向 WCF 应用程序提供有关安全专用网络的信息而开发的简单 Windows 通信基础 （WCF） 服务。 不需要安全性，因为数据的重要性较低，网络预期具有固有的安全性，或者安全性由 WCF 基础结构下面的层提供。  
  
 ![内联网不安全的客户端和服务方案。](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|特征|说明|  
|--------------------|-----------------|  
|安全模式|无|  
|传输|TCP|  
|绑定|<xref:System.ServiceModel.NetTcpBinding>|  
|互操作性|仅限 WCF|  
|身份验证|无|  
|完整性|无|  
|机密性|无|  
  
## <a name="service"></a>服务  
 下面的代码和配置应独立运行。 执行下列操作之一：  
  
- 使用代码（而不使用配置）创建独立服务。  
  
- 使用提供的配置创建服务，但不定义任何终结点。  
  
### <a name="code"></a>代码  
 下面的代码演示如何创建不安全的终结点：  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a>配置  
 下面的代码使用配置设置相同的终结点：  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Client  
 下面的代码和配置应独立运行。 执行下列操作之一：  
  
- 使用代码（和客户端代码）创建独立客户端。  
  
- 创建不定义任何终结点地址的客户端。 而使用将配置名称作为自变量的客户端构造函数。 例如：  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>代码  
 以下代码显示使用 TCP 协议访问不安全终结点的基本 WCF 客户端。  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a>配置  
 下面的配置代码应用于客户端：  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ServiceModel.NetTcpBinding>
- [安全概述](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Windows Server App Fabric 的安全模型](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
