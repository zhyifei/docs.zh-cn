---
title: "如何：使用 EntityCommand 执行参数化存储过程"
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
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 767108465247e44a2b9713133a4211f14dc832fe
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="fd9d2-102">如何：使用 EntityCommand 执行参数化存储过程</span><span class="sxs-lookup"><span data-stu-id="fd9d2-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="fd9d2-103">本主题说明如何使用 <xref:System.Data.EntityClient.EntityCommand> 类执行参数化存储过程。</span><span class="sxs-lookup"><span data-stu-id="fd9d2-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="fd9d2-104">运行本示例中的代码</span><span class="sxs-lookup"><span data-stu-id="fd9d2-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="fd9d2-105">添加[School 模型](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd9d2-105">Add the [School Model](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="fd9d2-106">有关详细信息，请参阅[如何： 使用实体数据模型向导](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)。</span><span class="sxs-lookup"><span data-stu-id="fd9d2-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="fd9d2-107">在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：</span><span class="sxs-lookup"><span data-stu-id="fd9d2-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="fd9d2-108">导入 `GetStudentGrades` 存储过程并将 `CourseGrade` 实体指定为返回类型。</span><span class="sxs-lookup"><span data-stu-id="fd9d2-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="fd9d2-109">有关如何导入存储的过程的信息，请参阅[如何： 导入存储过程](http://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d)。</span><span class="sxs-lookup"><span data-stu-id="fd9d2-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](http://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd9d2-110">示例</span><span class="sxs-lookup"><span data-stu-id="fd9d2-110">Example</span></span>  
 <span data-ttu-id="fd9d2-111">下面的代码执行 `GetStudentGrades` 存储过程，其中，`StudentId` 为必需的参数。</span><span class="sxs-lookup"><span data-stu-id="fd9d2-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="fd9d2-112">然后由 <xref:System.Data.EntityClient.EntityDataReader> 读取结果。</span><span class="sxs-lookup"><span data-stu-id="fd9d2-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="fd9d2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9d2-113">See Also</span></span>  
 [<span data-ttu-id="fd9d2-114">用于实体框架的 EntityClient 提供程序</span><span class="sxs-lookup"><span data-stu-id="fd9d2-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
