---
title: 编写事务应用程序
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 048df434ff0ada2ab5f8c7473913f6c34c05d1a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793486"
---
# <a name="writing-a-transactional-application"></a>编写事务应用程序
作为事务应用程序程序员，您可以利用 <xref:System.Transactions> 命名空间所提供的两种编程模型来创建事务。 可以通过使用利用显式编程模型<xref:System.Transactions.Transaction>类或在其中事务自动管理的基础结构，通过使用隐式编程模型<xref:System.Transactions.TransactionScope>类。 我们建议使用隐式事务模型进行开发。 你可以找到有关如何使用事务作用域中的详细信息[实现隐式事务使用事务范围](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)主题。  
  
 这两种模型都支持在程序达到一致状态时提交事务。 如果提交成功，就会永久提交事务。 如果提交失败，事务就会中止。 如果应用程序无法成功完成事务，则会尝试中止并撤消事务的效果。  
  
## <a name="in-this-section"></a>本节内容  
  
### <a name="creating-a-transaction"></a>创建事务  
 <xref:System.Transactions> 命名空间提供了两种用于创建事务的模型。 下列主题对这两种模型进行了介绍。  
  
 [使用事务范围实现隐式事务](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.TransactionScope> 类创建隐式事务。  
  
 [使用 CommittableTransaction 实现显式事务](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.CommittableTransaction> 类创建显式事务。  
  
### <a name="escalating-transaction-management"></a>升级事务管理  
 当事务需要访问其他应用程序域中的资源时，或者要登记到其他持久资源管理器时，事务会自动升级为由 MSDTC 管理。 中介绍事务升级[Transaction Management Escalation](../../../../docs/framework/data/transactions/transaction-management-escalation.md)主题。  
  
### <a name="concurrency"></a>并发  
 本主题[使用 DependentTransaction 管理并发](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md)演示了如何通过使用异步任务之间实现并发<xref:System.Transactions.DependentTransaction>类。  
  
### <a name="com-interop"></a>COM+ 互操作  
 本主题[与企业服务和 COM + 事务的互操作性](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md)阐释如何使分布式的事务与 COM + 事务交互。  
  
### <a name="diagnostics"></a>诊断  
 [诊断跟踪](../../../../docs/framework/data/transactions/diagnostic-traces.md)介绍如何使用由生成的跟踪代码<xref:System.Transactions>基础结构来对你的应用程序中的错误进行故障排除。  
  
### <a name="working-within-aspnet"></a>使用 ASP.NET  
 [在 ASP.NET 中使用 System.Transactions](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md)主题介绍如何成功地使用<xref:System.Transactions>在 ASP.NET 应用程序。
