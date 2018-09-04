---
title: 具有紧密耦合的客户端-服务器应用程序的 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
ms.openlocfilehash: 9c36fc1f402d3791611af47a3a6d997db4f31167
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521875"
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a>具有紧密耦合的客户端-服务器应用程序的 LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 可以与表示层上紧密耦合智能客户端，在中间层上使用。 在有些情况下，涉及到只读数据访问，没有进行开放式并发检查，或者具有时间戳的开放式并发，这种情况并不比非远程情况复杂很多。 但是，当数据库要求使用原始值进行开放式并发检查时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不提供对数据集中数据往返的支持级别。 但是，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中间层可以在任何平台上与客户端交换数据。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在[!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)]无基础结构提供它们已序列化到客户端后用于跟踪实体状态。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 支持面向服务的结构，其中数据和表示层之间的交互很少，相对原子的但不执行原始值的任何往返。 因此，如果要将 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 与紧密耦合的智能客户端结合使用，并且数据库使用具有原始值的开放式并发，那么您必须实现自己的机制，用于在表示层和中间层之间通告更改。 系统设计器负责决定通过以这部分额外工作来换取 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在中间层上提供的优点是否有意义。 另一方面，如果数据库具有时间戳，那么就无需自定义的更改跟踪逻辑。  
  
## <a name="see-also"></a>请参阅  
 [使用 LINQ to SQL 的 N 层和远程应用程序](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [使用 Web 服务 的 LINQ to SQL N 层](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [在 N 层应用程序中使用数据集](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)
