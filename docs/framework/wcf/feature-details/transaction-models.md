---
title: 事务模型
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab3baf8cc0bb6af951f6f3e6396b7545d0c6b301
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="transaction-models"></a>事务模型
本主题描述 Microsoft 提供的事务编程模型和基础结构组件之间的关系。  
  
 在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中使用事务时，需要了解的一点是，您并不是在不同事务模型之间进行选择，而是在一个集成化且一致的模型的不同层上进行操作。  
  
 以下各部分描述了三个主要事务组件。  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation 事务  
 使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的事务支持可以编写事务性服务。 此外，借助于它对 WS-AtomicTransaction (WS-AT) 协议的支持，应用程序可以将事务流式传输到使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 或第三方技术生成的 Web 服务。  
  
 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务或应用程序中，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 事务功能提供了一些属性和配置，用于以声明方式指定基础结构应当创建、流式传输和同步事务的方式和时间。  
  
## <a name="systemtransactions-transactions"></a>System.Transactions 事务  
 <xref:System.Transactions> 命名空间同时提供了一个基于 <xref:System.Transactions.Transaction> 类的显式编程模型和一个使用 <xref:System.Transactions.TransactionScope> 类的隐式编程模型（在此模型中，基础结构自动管理事务）。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 如何创建使用这两种模型的事务应用程序，请参阅[编写事务应用程序](http://go.microsoft.com/fwlink/?LinkId=94947)。  
  
 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务或应用程序中，可使用 <xref:System.Transactions> 提供的编程模型在客户端应用程序中创建事务，以及在需要时与服务内的事务显式进行交互。  
  
## <a name="msdtc-transactions"></a>MSDTC 事务  
 Microsoft Distributed Transaction Coordinator (MSDTC) 是一个事务管理器，它为分布式事务提供支持。  
  
 有关详细信息，请参阅[DTC 程序员参考](http://go.microsoft.com/fwlink/?LinkId=94948)。  
  
 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务或应用程序中，MSDTC 提供了用于对客户端或服务中创建的事务进行协调的基础结构。
