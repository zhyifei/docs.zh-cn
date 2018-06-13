---
title: 如何：筛选相关数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: b40de7201610c58b9b8e86045afe5869d958bdf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360830"
---
# <a name="how-to-filter-related-data"></a>如何：筛选相关数据
使用 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 方法可指定用来限制检索到的数据量的子查询。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 方法将检索到的 `Orders` 限制为今天尚未发货的那些订单。 如果不使用这种方式，则即使只需要一部分订单，也会检索到所有 `Orders`。  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [查询数据库](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
