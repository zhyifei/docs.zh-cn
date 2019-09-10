---
title: 如何：执行返回复杂类型的查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: b08b220e969ad1c400413978c85b2f107d64a688
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854637"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>如何：执行返回复杂类型的查询
本主题演示如何执行返回包含复杂类型属性的实体类型对象的 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 查询。  
  
### <a name="to-run-the-code-in-this-example"></a>运行本示例中的代码  
  
1. 将[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)添加到项目中，并将项目配置为使用实体框架。 有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。  
  
2. 在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. 双击 .edmx 文件可在 Entity Designer 的 "[模型浏览器" 窗口](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100))中显示该模型。 在 Entity Designer 图面上，选择`Email`实体`Phone`类型的和`Contact`属性，然后右键单击并选择 "**重构为新的复杂类型**"。  
  
4. 具有选定`Email`和`Phone`属性的新复杂类型将添加到**模型浏览器**。 为复杂类型提供了一个默认名称：在 "**属性**" `EmailPhone`窗口中将该类型重命名为。 此外，新的 `ComplexProperty` 属性将添加到 `Contact` 实体类型。 将该属性重命名为 `EmailPhoneComplexType.`。  
  
     有关使用实体数据模型向导创建和修改复杂类型的信息，请参阅[如何：将现有属性重构为复杂类型属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) ， [以及如何：创建和修改复杂类型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))。  
  
## <a name="example"></a>示例  
 下面的示例执行一个查询， `Contact`该查询返回对象的集合并显示`Contact`对象的两个属性`ContactID` ：和`EmailPhoneComplexType`复杂类型的值。  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
