---
title: "如何：在 Visual Basic 或 C# 中生成对象模型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f4cf0999366a1a677fa729f2d409bea36821eb3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>如何：在 Visual Basic 或 C# 中生成对象模型 #
在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，采用您自己的编程语言的对象模型映射到关系数据库。 有两种工具可用来利用现有数据库的元数据自动生成 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 或 C# 模型。  
  
-   如果您使用的是 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]，则可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来生成对象模型。 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]提供了一个丰富的用户界面来帮助你生成[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]对象模型。 有关详细信息，请参阅[Linq to SQL Visual Studio 中的工具](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)。
  
-   SQLMetal 命令行工具。 有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。  
  
    > [!NOTE]
    >  如果您没有现有数据库且希望利用对象模型创建一个，则可以使用代码编辑器和 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 来创建对象模型。 有关详细信息，请参阅[如何： 动态创建数据库](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)。  
  
 文档[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]提供了如何生成的示例[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]或通过使用 C# 对象模型[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]。 以下信息提供了有关如何使用 SQLMetal 命令行工具的示例。 有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。  
  
## <a name="example"></a>示例  
 下面的示例中显示的 SQLMetal 命令行会生成 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 代码作为 Northwind 示例数据库的基于属性的对象模型。 还呈现了存储过程和函数。  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>示例  
 下面的示例中显示的 SQLMetal 命令行会生成 C# 代码作为 Northwind 示例数据库的基于属性的对象模型。 还呈现了存储过程和函数，并自动将表名变为复数形式。  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [通过演练学习](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [如何：通过使用代码编辑器自定义实体类](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [基于特性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [外部映射](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [创建对象模型](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
