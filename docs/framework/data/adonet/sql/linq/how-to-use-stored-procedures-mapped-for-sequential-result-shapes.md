---
title: "如何：使用针对顺序结果形状映射的存储过程"
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
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 227fe2c777d23172caba5f290d9626552af4747a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="79ef6-102">如何：使用针对顺序结果形状映射的存储过程</span><span class="sxs-lookup"><span data-stu-id="79ef6-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="79ef6-103">这种存储过程可以生成多个结果形状，但您知道结果的返回顺序。</span><span class="sxs-lookup"><span data-stu-id="79ef6-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="79ef6-104">请将此方案与您不知道返回顺序的方案作一个对比。</span><span class="sxs-lookup"><span data-stu-id="79ef6-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="79ef6-105">有关详细信息，请参阅[如何： 使用存储过程为多个结果形状映射](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="79ef6-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ef6-106">示例</span><span class="sxs-lookup"><span data-stu-id="79ef6-106">Example</span></span>  
 <span data-ttu-id="79ef6-107">下面是一个按顺序返回多个结果形状的存储过程的 T-SQL。</span><span class="sxs-lookup"><span data-stu-id="79ef6-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="79ef6-108">示例</span><span class="sxs-lookup"><span data-stu-id="79ef6-108">Example</span></span>  
 <span data-ttu-id="79ef6-109">你将使用类似于以下内容的代码来执行此存储过程。</span><span class="sxs-lookup"><span data-stu-id="79ef6-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="79ef6-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="79ef6-110">See Also</span></span>  
 [<span data-ttu-id="79ef6-111">存储过程</span><span class="sxs-lookup"><span data-stu-id="79ef6-111">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
