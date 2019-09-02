---
title: 编写事务应用程序
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 318771c83a5b7ebc0f3fb2bb8c59240269a2dea9
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205824"
---
# <a name="writing-a-transactional-application"></a>编写事务应用程序
作为事务应用程序程序员，您可以利用 <xref:System.Transactions> 命名空间所提供的两种编程模型来创建事务。 通过使用类, 可以使用显式编程模型<xref:System.Transactions.Transaction> , 或者通过<xref:System.Transactions.TransactionScope>使用类, 通过基础结构自动管理事务。 建议使用隐式事务模型进行开发。 可以在[使用事务范围实现隐式事务](implementing-an-implicit-transaction-using-transaction-scope.md)主题中找到有关如何使用事务范围的详细信息。  
  
 这两种模型都支持在程序达到一致状态时提交事务。 如果提交成功，就会永久提交事务。 如果提交失败，事务就会中止。 如果应用程序无法成功完成事务，则会尝试中止并撤消事务的效果。  
  
## <a name="in-this-section"></a>本节内容  
  
### <a name="creating-a-transaction"></a>创建事务  
 <xref:System.Transactions> 命名空间提供了两种用于创建事务的模型。 下列主题对这两种模型进行了介绍。  
  
 [使用事务范围实现隐式事务](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.TransactionScope> 类创建隐式事务。  
  
 [使用 CommittableTransaction 实现显式事务](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 描述 <xref:System.Transactions> 命名空间如何支持使用 <xref:System.Transactions.CommittableTransaction> 类创建显式事务。  
  
### <a name="escalating-transaction-management"></a>升级事务管理  
 当事务需要访问其他应用程序域中的资源时，或者要登记到其他持久资源管理器时，事务会自动升级为由 MSDTC 管理。 事务升级在[事务管理升级](transaction-management-escalation.md)主题中介绍。  
  
### <a name="concurrency"></a>并发  
 使用[DependentTransaction 管理并发](managing-concurrency-with-dependenttransaction.md)的主题演示了如何使用<xref:System.Transactions.DependentTransaction>类在异步任务之间实现并发。  
  
### <a name="com-interop"></a>COM+ 互操作  
 主题[与企业服务和 COM + 事务的互操作性](interoperability-with-enterprise-services-and-com-transactions.md)说明了如何使分布式事务与 com + 事务交互。  
  
### <a name="diagnostics"></a>诊断  
 [诊断跟踪](diagnostic-traces.md)介绍了如何使用<xref:System.Transactions>基础结构所生成的跟踪代码对应用程序中的错误进行故障排除。  
  
### <a name="working-within-aspnet"></a>使用 ASP.NET  
 [ASP.NET 主题中的 Using system.object](using-system-transactions-in-aspnet.md)介绍了如何在 ASP.NET 应用程序中<xref:System.Transactions>成功使用。
