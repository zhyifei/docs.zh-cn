---
title: 在 Visual Studio 中创建 LINQ to DataSet 项目
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 8b905c65575c3c567459d843b2a5d1606bc63228
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783773"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>如何：在 Visual Studio 中创建 LINQ to DataSet 项目

不同类型的 LINQ 项目需要特定的程序集引用和导入的命名空间 （Visual Basic）C#或 [using](../../../csharp/language-reference/keywords/using-directive.md) 指令（）。 LINQ 的最低要求是对*system.object*的引用和`using`的指令。 <xref:System.Linq>

默认情况下，如果在 Visual Studio 2017 中创建C#新的控制台应用程序项目，则会提供这些要求。 如果要从早期版本的 Visual Studio 升级项目，可能必须手动提供这些与 LINQ 相关的引用。

LINQ to DataSet 需要对*system.data.datasetextensions.dll*和*的两*个附加引用。

> [!NOTE]
> 如果是从命令提示符生成，则必须在 *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*中手动引用与 LINQ 相关的 dll。

## <a name="to-enable-linq-to-dataset-functionality"></a>启用 LINQ to DataSet 功能

按照以下步骤在现有项目中启用 LINQ to DataSet 功能。

1. 添加对 System.data.datasetextensions.dll **、system.web**和 system.object的引用。

   在**解决方案资源管理器**中，右键单击 "**引用**" 节点，然后选择 "**添加引用**"。 在 "**引用管理器** **" 对话框**中 **，选择 "** **system.data.datasetextensions.dll**"。 选择“确定”。

1. 为**system.web**和**system.object**添加[using](../../../csharp/language-reference/keywords/using-directive.md)指令（或 Visual Basic 中的[Imports 语句](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)）。

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. 根据你连接到`using`数据库的方式`Imports` ，还可以根据需要添加**SqlClient** **的指令**（或语句）。

## <a name="see-also"></a>请参阅

- [LINQ to DataSet 入门](getting-started-linq-to-dataset.md)
