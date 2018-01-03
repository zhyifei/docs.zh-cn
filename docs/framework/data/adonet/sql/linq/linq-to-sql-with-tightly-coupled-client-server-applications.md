---
title: "具有紧密耦合的客户端-服务器应用程序的 LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a2fa902cfbea3c6eb15e1832231bb3ed83de5497
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a>具有紧密耦合的客户端-服务器应用程序的 LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]可在中间层上与表示层上的紧密耦合智能客户端。 在有些情况下，涉及到只读数据访问，没有进行开放式并发检查，或者具有时间戳的开放式并发，这种情况并不比非远程情况复杂很多。 但是，当数据库要求使用原始值进行开放式并发检查时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不提供对数据集中数据往返的支持级别。 但是，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中间层可以在任何平台上与客户端交换数据。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]在[!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)]提供无基础结构，以便跟踪实体状态后具有到客户端已序列化。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]支持面向服务的结构，其中数据和表示层之间的交互很小，相对原子的但不执行任何往返原始值。 因此，如果要将 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 与紧密耦合的智能客户端结合使用，并且数据库使用具有原始值的开放式并发，那么您必须实现自己的机制，用于在表示层和中间层之间通告更改。 系统设计器负责决定通过以这部分额外工作来换取 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在中间层上提供的优点是否有意义。 另一方面，如果数据库具有时间戳，那么就无需自定义的更改跟踪逻辑。  
  
## <a name="see-also"></a>请参阅  
 [使用 LINQ to SQL 的 N 层和远程应用程序](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [使用 Web 服务 的 LINQ to SQL N 层](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [在 N 层应用程序中使用数据集](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)
