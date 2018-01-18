---
title: "如何：将信息作为只读信息检索"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e7144863e43ec816ad2359c6c48f6d38babb3b46
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-retrieve-information-as-read-only"></a>如何：将信息作为只读信息检索
当您不打算更改数据时，您可以通过设法产生只读结果来提高查询性能。  
  
 通过将 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> 设置为 `false` 可实现只读处理。  
  
> [!NOTE]
>  当 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> 设置为 `false` 时，<xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> 将隐式设置为 `false`。  
  
## <a name="example"></a>示例  
 下面的代码检索雇员雇佣日期的只读集合。  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [查询概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [查询数据库](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [推迟加载与即时加载](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
