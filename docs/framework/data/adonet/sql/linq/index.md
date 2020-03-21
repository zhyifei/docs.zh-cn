---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: b0660312f540a69911905edd08541ed70cf39bb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174311"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]是 .NET Framework 版本 3.5 的一个组件，它提供了用于将关系数据作为对象管理的运行时基础结构。  
  
> [!NOTE]
> 关系数据显示为由二维表（关系** 或平面文件**）组成的集合，其中公共列将表互相关联起来。 若要有效地使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，您必须略为熟悉关系数据库的基本原理。  
  
 在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，关系数据库的数据模型映射到用开发人员所用的编程语言表示的对象模型。 当应用程序运行时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将对象模型中的语言集成查询转换为 SQL，然后将它们发送到数据库进行执行。 当数据库返回结果时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将它们转换回您可以用您自己的编程语言处理的对象。  
  
 使用 Visual Studio 的开发人员通常使用对象关系设计器，它提供了实现 的许多功能的[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]用户界面。  
  
 此版本的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 附带的文档介绍了生成 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序所需的基本构造块、流程和技术。 您还可以搜索 Microsoft 文档以查找特定问题，还可以参加[LINQ 论坛](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)，与专家详细讨论更复杂的主题。 最后[，LINQ 到 SQL：.NET 语言集成查询关系数据](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10))白皮书详细介绍了[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]技术，并附有可视化基本和 C# 代码示例。  
  
## <a name="in-this-section"></a>本节内容  
 [入门](getting-started.md)  
 提供对 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的简要概述以及有关如何开始使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的信息。  
  
 [编程指南](programming-guide.md)  
 提供映射、查询、更新、调试及类似任务的步骤。  
  
 [参考](reference.md)  
 提供有关 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的多个方面的参考信息。 相关主题包括“SQL-CLR 类型映射”、“标准查询运算符转换”等。  
  
 [示例](samples.md)  
 提供指向可视化基本和 C# 示例的链接。  
  
## <a name="related-sections"></a>相关章节  
 [语言集成查询 （LINQ） - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 在 C# 中提供 LINQ 技术的概述。

 [语言集成查询 (LINQ) - Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 在可视化基础知识中概述 LINQ 技术。
  
 [Linq](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 介绍可视化基本用户的 LINQ 技术。  
  
 [LINQ 和 ADO.NET](../../linq-and-ado-net.md)  
 指向ADO.NET门户的链接。  
  
 [LINQ to SQL 演练](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 列出可用于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的演练。  
  
 [下载示例数据库](downloading-sample-databases.md)  
 介绍如何下载文档中使用的示例数据库。  
  
 [LinqDataSource Web 服务器控制概述](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 描述<xref:System.Web.UI.WebControls.LinqDataSource>控件如何通过ASP.NET数据源控制体系结构向 Web 开发人员公开语言集成查询 （LINQ）。
