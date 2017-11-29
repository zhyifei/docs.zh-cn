---
title: "编写事务应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ec8537c4fdf80ffe448bba1376eacf519d67bcbe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="writing-a-transactional-application"></a>编写事务应用程序
作为事务应用程序程序员，您可以利用 <xref:System.Transactions> 命名空间所提供的两种编程模型来创建事务。 则可以通过使用利用的显式编程模型<xref:System.Transactions.Transaction>类或在其中事务自动由管理基础结构中，通过使用隐式编程模型<xref:System.Transactions.TransactionScope>类。 我们建议你使用用于开发的隐式事务模型。 你可以找到有关如何使用事务范围中的详细信息[实现使用事务范围的隐式事务](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)主题。  
  
 这两种模型都支持在程序达到一致状态时提交事务。 如果提交成功，就会永久提交事务。 如果提交失败，事务就会中止。 如果应用程序无法成功完成事务，则会尝试中止并撤消事务的效果。  
  
## <a name="in-this-section"></a>本节内容  
  
### <a name="creating-a-transaction"></a>创建事务  
 <xref:System.Transactions> 命名空间提供了两种用于创建事务的模型。 下列主题对这两种模型进行了介绍。  
  
 [实现使用事务范围的隐式事务](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.TransactionScope> 类创建隐式事务。  
  
 [实现使用 CommittableTransaction 的显式事务](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.CommittableTransaction> 类创建显式事务。  
  
### <a name="escalating-transaction-management"></a>升级事务管理  
 当事务需要访问其他应用程序域中的资源时，或者要登记到其他持久资源管理器时，事务会自动升级为由 MSDTC 管理。 中介绍了事务升级[事务管理升级](../../../../docs/framework/data/transactions/transaction-management-escalation.md)主题。  
  
### <a name="concurrency"></a>并发  
 主题[与 DependentTransaction 管理并发](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md)演示如何通过使用异步任务之间实现并发<xref:System.Transactions.DependentTransaction>类。  
  
### <a name="com-interop"></a>COM+ 互操作  
 主题[与企业服务和 COM + 事务互操作性](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md)阐释了如何建立您与 COM + 事务进行交互的分布式的事务。  
  
### <a name="diagnostics"></a>诊断  
 [诊断跟踪](../../../../docs/framework/data/transactions/diagnostic-traces.md)介绍如何使用由生成的跟踪代码<xref:System.Transactions>基础结构来解决你的应用程序中的错误。  
  
### <a name="working-within-aspnet"></a>使用 ASP.NET  
 [在 ASP.NET 中使用 System.Transactions](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md)主题介绍如何成功地使用<xref:System.Transactions>内部 ASP.NET 应用程序。
