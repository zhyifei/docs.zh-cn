---
title: "ServiceModel 事务配置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ef1d8a9e749c06701aa0a187f81b5b345518c07b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="servicemodel-transaction-configuration"></a>ServiceModel 事务配置
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 提供了以下三个用于为服务配置事务的属性：`transactionFlow`、`transactionProtocol` 和 `transactionTimeout`。  
  
## <a name="configuring-transactionflow"></a>配置 transactionFlow  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的大多数预定义绑定都包含 `transactionFlow` 和 `transactionProtocol` 属性，以便您可以使用特定的事务流协议为特定终结点配置用于接受传入事务的绑定。 此外，您可以使用 `transactionFlow` 元素及其 `transactionProtocol` 特性生成您自己的自定义绑定。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]设置的配置元素，请参阅[\<绑定 >](../../../../docs/framework/misc/binding.md)和[WCF 配置架构](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)。  
  
 `transactionFlow` 属性指定是否为使用绑定的服务终结点启用事务流。  
  
## <a name="configuring-transactionprotocol"></a>配置 transactionProtocol  
 `transactionProtocol` 属性指定要应用于使用绑定的服务终结点的事务协议。  
  
 下面是一个配置节示例，该配置节将指定的绑定配置为支持事务流并且使用 WS-AtomicTransaction 协议。  
  
```xml  
<netNamedPipeBinding>  
   <binding name="test"  
      closeTimeout="00:00:10"  
      openTimeout="00:00:20"   
      receiveTimeout="00:00:30"  
      sendTimeout="00:00:40"  
      transactionFlow="true"  
      transactionProtocol="WSAtomicTransactionOctober2004"  
      hostNameComparisonMode="WeakWildcard"  
      maxBufferSize="1001"  
      maxConnections="123"   
      maxReceivedMessageSize="1000">  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="configuring-transactiontimeout"></a>配置 transactionTimeout  
 可以在配置文件的 `transactionTimeout` 元素中配置 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的 `behavior` 属性。 下面的代码演示如何执行此操作。  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 `transactionTimeout` 属性指定了在该服务中创建的新事务必须在此期间完成的时间段。 它被用作任何建立新事务的操作的 <xref:System.Transactions.TransactionScope> 超时，而且，如果应用了 <xref:System.ServiceModel.OperationBehaviorAttribute>，则 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 属性将设置为 `true`。  
  
 超时指定了从创建事务到完成两阶段提交协议的第 1 阶段之间的持续时间。  
  
 如果在 `service` 配置节内设置了此属性，则应该通过 <xref:System.ServiceModel.OperationBehaviorAttribute> 应用相应服务的至少一个方法，其中 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 属性设置为 `true`。  
  
 请注意，所使用的超时值是此 `transactionTimeout` 配置设置和任何 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> 属性之间的较小值。  
  
## <a name="see-also"></a>另请参阅  
 [\<绑定 >](../../../../docs/framework/misc/binding.md)  
 [WCF 配置架构](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)
