---
title: "如何：检测到并解决冲突的提交"
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
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2abd54a7ce2500a1fda39dc781052b9d7656afee
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>如何：检测到并解决冲突的提交
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 提供了许多资源，用于检测和解决因多个用户更改数据库而产生的冲突。 有关详细信息，请参阅[如何： 管理更改冲突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示`try` / `catch`捕获的块<xref:System.Data.Linq.ChangeConflictException>异常。 每个冲突的实体和成员信息会显示在控制台窗口中。  
  
> [!NOTE]
>  您必须将 `using System.Reflection` 指令（在 Visual Basic 中为 `Imports System.Reflection`）包含在内，以支持信息检索。 有关详细信息，请参阅<xref:System.Reflection>。  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [进行和提交数据更改](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [如何：管理更改冲突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
