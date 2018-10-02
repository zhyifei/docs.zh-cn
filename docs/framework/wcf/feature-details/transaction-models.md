---
title: 事务模型
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517778"
---
# <a name="transaction-models"></a>事务模型
本主题描述 Microsoft 提供的事务编程模型和基础结构组件之间的关系。  
  
 使用事务时 Windows Communication Foundation (WCF) 中，务必了解不选择不同的事务模型之间但不同层的集成和一致的模型而不操作。  
  
 以下各部分描述了三个主要事务组件。  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation 事务  
 WCF 中的事务支持允许您编写事务性服务。 此外，它对 WS-AtomicTransaction (WS-AT) 协议的支持，与应用程序可以使事务流动到使用 WCF 或第三方技术生成的 Web 服务。  
  
 在 WCF 服务或应用程序中，WCF 事务功能提供属性和配置用于以声明方式指定基础结构如何以及何时应创建、 流、 和同步事务。  
  
## <a name="systemtransactions-transactions"></a>System.Transactions 事务  
 <xref:System.Transactions> 命名空间同时提供了一个基于 <xref:System.Transactions.Transaction> 类的显式编程模型和一个使用 <xref:System.Transactions.TransactionScope> 类的隐式编程模型（在此模型中，基础结构自动管理事务）。  
  
 有关如何创建事务应用程序使用这两种模型的详细信息，请参阅[编写事务应用程序](https://go.microsoft.com/fwlink/?LinkId=94947)。  
  
 中的 WCF 服务或应用程序，<xref:System.Transactions>提供编程模型，用于创建客户端应用程序中的事务和显式进行交互与事务，在需要时，在服务中。  
  
## <a name="msdtc-transactions"></a>MSDTC 事务  
 Microsoft Distributed Transaction Coordinator (MSDTC) 是一个事务管理器，它为分布式事务提供支持。  
  
 有关详细信息，请参阅[DTC 程序员参考](https://go.microsoft.com/fwlink/?LinkId=94948)。  
  
 在 WCF 服务或应用程序中，MSDTC 提供客户端或服务中创建的事务协调的基础结构。
