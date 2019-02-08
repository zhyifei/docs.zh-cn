---
title: 如何：执行返回复杂类型的查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 6c063c9ef6bfde868c773d941ba2107dbaa9ee73
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827118"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="1770b-102">如何：执行返回复杂类型的查询</span><span class="sxs-lookup"><span data-stu-id="1770b-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="1770b-103">本主题演示如何执行返回包含复杂类型属性的实体类型对象的 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 查询。</span><span class="sxs-lookup"><span data-stu-id="1770b-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="1770b-104">运行本示例中的代码</span><span class="sxs-lookup"><span data-stu-id="1770b-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="1770b-105">添加[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1770b-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="1770b-106">有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="1770b-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="1770b-107">在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：</span><span class="sxs-lookup"><span data-stu-id="1770b-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="1770b-108">双击要显示在模型的.edmx 文件[模型浏览器窗口](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100))在实体设计器。</span><span class="sxs-lookup"><span data-stu-id="1770b-108">Double click the .edmx file to display the model in the [Model Browser window](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="1770b-109">在实体设计器图面中，选择`Email`并`Phone`的属性`Contact`实体类型，然后右键单击并选择**重构为新的复杂类型**。</span><span class="sxs-lookup"><span data-stu-id="1770b-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4.  <span data-ttu-id="1770b-110">新的复杂类型与所选`Email`并`Phone`属性添加到**模型浏览器**。</span><span class="sxs-lookup"><span data-stu-id="1770b-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="1770b-111">复杂类型具有默认名称： 重命名类型为`EmailPhone`中**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="1770b-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="1770b-112">此外，新的 `ComplexProperty` 属性将添加到 `Contact` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="1770b-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="1770b-113">将该属性重命名为 `EmailPhoneComplexType.`。</span><span class="sxs-lookup"><span data-stu-id="1770b-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="1770b-114">有关创建和修改复杂类型的使用实体数据模型向导的信息，请参阅[如何：现有属性重构为复杂类型属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100))和[如何：创建和修改复杂类型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="1770b-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1770b-115">示例</span><span class="sxs-lookup"><span data-stu-id="1770b-115">Example</span></span>  
 <span data-ttu-id="1770b-116">下面的示例执行返回的集合的查询`Contact`对象，并显示的两个属性`Contact`对象：`ContactID`的值和`EmailPhoneComplexType`复杂类型。</span><span class="sxs-lookup"><span data-stu-id="1770b-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
