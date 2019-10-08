---
title: 如何：在 Visual Basic 或 C# 中生成对象模型
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 7d2c0600534c93f5884eec48a4bdaa3ce99945e9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002801"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>如何：在 Visual Basic 或 C @ no__t 中生成对象模型
在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，采用您自己的编程语言的对象模型映射到关系数据库。 有两个工具可用于根据现有数据库的C#元数据自动生成 Visual Basic 或模型。  
  
- 如果使用的是 Visual Studio，则可以使用对象关系设计器来生成对象模型。 O/R 设计器提供了丰富的用户界面，可帮助您生成 @no__t 0 对象模型。 有关详细信息，请参阅[Visual Studio 中的 Linq TO SQL 工具](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)。
  
- SQLMetal 命令行工具。 有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../tools/sqlmetal-exe-code-generation-tool.md)。  
  
    > [!NOTE]
    > 如果您没有现有数据库且希望利用对象模型创建一个，则可以使用代码编辑器和 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 来创建对象模型。 有关详细信息，请参阅[如何：动态创建数据库 @ no__t。  
  
 O/R 设计器的文档提供了有关如何使用 O/R 设计C#器生成 Visual Basic 或对象模型的示例。 以下信息提供了有关如何使用 SQLMetal 命令行工具的示例。 有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../tools/sqlmetal-exe-code-generation-tool.md)。  
  
## <a name="example"></a>示例  
 下面的示例中所示的 SQLMetal 命令行产生 Visual Basic 代码，作为 Northwind 示例数据库的基于属性的对象模型。 还呈现了存储过程和函数。  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>示例  
 下面的示例中显示的 SQLMetal 命令行会生成 C# 代码作为 Northwind 示例数据库的基于属性的对象模型。 还呈现了存储过程和函数，并自动将表名变为复数形式。  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>请参阅

- [编程指南](programming-guide.md)
- [LINQ to SQL 对象模型](the-linq-to-sql-object-model.md)
- [通过演练学习](learning-by-walkthroughs.md)
- [如何：使用代码编辑器自定义实体类 @ no__t-0
- [基于特性的映射](attribute-based-mapping.md)
- [SqlMetal.exe（代码生成工具）](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [外部映射](external-mapping.md)
- [下载示例数据库](downloading-sample-databases.md)
- [创建对象模型](creating-the-object-model.md)
