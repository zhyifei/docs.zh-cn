---
title: 事务模型
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9efe8c6994cc80957b707bbae0885a3c5896f70a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499019"
---
# <a name="transaction-models"></a>事务模型
本主题描述 Microsoft 提供的事务编程模型和基础结构组件之间的关系。  
  
 当使用事务 Windows Communication Foundation (WCF) 中，务必了解，你不选择不同的事务模型之间但而在一个集成化且一致的模型的不同层上进行操作。  
  
 以下各部分描述了三个主要事务组件。  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation 事务  
 在 WCF 中的事务支持可以编写事务性服务。 此外，借助于它对 Ws-atomictransaction (WS-AT) 协议的支持，应用程序可以使事务流动到使用 WCF 或第三方技术生成的 Web 服务。  
  
 在 WCF 服务或应用程序中，WCF 事务功能提供属性和配置，用于以声明方式指定基础结构如何以及何时应创建、 流式处理，和同步事务。  
  
## <a name="systemtransactions-transactions"></a>System.Transactions 事务  
 <xref:System.Transactions> 命名空间同时提供了一个基于 <xref:System.Transactions.Transaction> 类的显式编程模型和一个使用 <xref:System.Transactions.TransactionScope> 类的隐式编程模型（在此模型中，基础结构自动管理事务）。  
  
 有关如何创建使用这两种模型的事务应用程序的详细信息，请参阅[编写事务应用程序](http://go.microsoft.com/fwlink/?LinkId=94947)。  
  
 在 WCF 服务或应用程序，<xref:System.Transactions>提供的编程模型，用于创建客户端应用程序中的事务并显式进行交互与事务，在需要时，服务中。  
  
## <a name="msdtc-transactions"></a>MSDTC 事务  
 Microsoft Distributed Transaction Coordinator (MSDTC) 是一个事务管理器，它为分布式事务提供支持。  
  
 有关详细信息，请参阅[DTC 程序员参考](http://go.microsoft.com/fwlink/?LinkId=94948)。  
  
 在 WCF 服务或应用程序中，MSDTC 提供的客户端或服务中创建的事务协调的基础结构。
