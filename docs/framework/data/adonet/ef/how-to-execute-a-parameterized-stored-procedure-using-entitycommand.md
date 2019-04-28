---
title: 如何：使用 EntityCommand 执行参数化存储过程
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: deb1877397053ceab8c284a537a861ba56ffb729
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606151"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="d4e38-102">如何：使用 EntityCommand 执行参数化存储过程</span><span class="sxs-lookup"><span data-stu-id="d4e38-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="d4e38-103">本主题说明如何使用 <xref:System.Data.EntityClient.EntityCommand> 类执行参数化存储过程。</span><span class="sxs-lookup"><span data-stu-id="d4e38-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="d4e38-104">运行本示例中的代码</span><span class="sxs-lookup"><span data-stu-id="d4e38-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="d4e38-105">添加[School 模型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4e38-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="d4e38-106">有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="d4e38-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="d4e38-107">在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：</span><span class="sxs-lookup"><span data-stu-id="d4e38-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="d4e38-108">导入 `GetStudentGrades` 存储过程并将 `CourseGrade` 实体指定为返回类型。</span><span class="sxs-lookup"><span data-stu-id="d4e38-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="d4e38-109">有关如何导入存储的过程的信息，请参阅[如何：存储的过程导入](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="d4e38-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e38-110">示例</span><span class="sxs-lookup"><span data-stu-id="d4e38-110">Example</span></span>  
 <span data-ttu-id="d4e38-111">下面的代码执行 `GetStudentGrades` 存储过程，其中，`StudentId` 为必需的参数。</span><span class="sxs-lookup"><span data-stu-id="d4e38-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="d4e38-112">然后由 <xref:System.Data.EntityClient.EntityDataReader> 读取结果。</span><span class="sxs-lookup"><span data-stu-id="d4e38-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="d4e38-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4e38-113">See also</span></span>

- [<span data-ttu-id="d4e38-114">用于实体框架的 EntityClient 提供程序</span><span class="sxs-lookup"><span data-stu-id="d4e38-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
