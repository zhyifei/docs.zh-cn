---
title: 分析 LINQ to SQL 源代码
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 25c54fa67171b456b2eeb5c30f52d1e654fca995
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353749"
---
# <a name="analyzing-linq-to-sql-source-code"></a>分析 LINQ to SQL 源代码
通过按以下步骤操作，您可以用 Northwind 示例数据库生成 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 源代码。 您可以将对象模型的元素与数据库的元素作一个比较，以便更好地了解不同项的映射方式。  
  
> [!NOTE]
>  使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]来生成此代码。  
  
1.  如果您的开发计算机上还没有 Northwind 示例数据库，您可以免费下载它。 有关详细信息，请参阅[下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)。  
  
2.  使用 SqlMetal 命令行工具生成 Visual Basic 或 C# 源文件。 有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。 通过在命令提示符处键入以下命令，您可以生成包含存储过程和函数的 Visual Basic 和 C# 源文件。  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a>请参阅  
 [参考](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [背景信息](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
