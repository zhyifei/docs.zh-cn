---
title: "如何：显示变更集"
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
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 19f0198103999da687e07f472cd5a480406830cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="1bce9-102">如何：显示变更集</span><span class="sxs-lookup"><span data-stu-id="1bce9-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="1bce9-103">可以通过使用 <xref:System.Data.Linq.DataContext> 来查看由 <xref:System.Data.Linq.DataContext.GetChangeSet%2A> 跟踪的更改。</span><span class="sxs-lookup"><span data-stu-id="1bce9-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bce9-104">示例</span><span class="sxs-lookup"><span data-stu-id="1bce9-104">Example</span></span>  
 <span data-ttu-id="1bce9-105">下面的示例检索所在城市为伦敦的客户，将其所在城市更改为巴黎，然后将所做的更改提交回数据库。</span><span class="sxs-lookup"><span data-stu-id="1bce9-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="1bce9-106">执行此代码所得到的输出与如下内容类似。</span><span class="sxs-lookup"><span data-stu-id="1bce9-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="1bce9-107">请注意，结尾处的摘要显示做了八项更改。</span><span class="sxs-lookup"><span data-stu-id="1bce9-107">Note that the summary at the end shows that eight changes were made.</span></span>  
  
 `CustomerID: AROUT`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: BSBEV`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: CONSH`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: EASTC`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: NORTS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: PARIS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SEVES`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SPECD`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 ``  
  
 `Total changes: {Added: 0, Removed: 0, Modified: 8}`  
  
## <a name="see-also"></a><span data-ttu-id="1bce9-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bce9-108">See Also</span></span>  
 [<span data-ttu-id="1bce9-109">调试支持</span><span class="sxs-lookup"><span data-stu-id="1bce9-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
