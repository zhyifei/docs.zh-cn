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
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="5ac38-102">如何：在 Visual Studio 中创建 LINQ to DataSet 项目</span><span class="sxs-lookup"><span data-stu-id="5ac38-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="5ac38-103">不同类型的 LINQ 项目需要特定的程序集引用和导入的命名空间 （Visual Basic）C#或 [using](../../../csharp/language-reference/keywords/using-directive.md) 指令（）。</span><span class="sxs-lookup"><span data-stu-id="5ac38-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="5ac38-104">LINQ 的最低要求是对*system.object*的引用和`using`的指令。 <xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="5ac38-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="5ac38-105">默认情况下，如果在 Visual Studio 2017 中创建C#新的控制台应用程序项目，则会提供这些要求。</span><span class="sxs-lookup"><span data-stu-id="5ac38-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="5ac38-106">如果要从早期版本的 Visual Studio 升级项目，可能必须手动提供这些与 LINQ 相关的引用。</span><span class="sxs-lookup"><span data-stu-id="5ac38-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="5ac38-107">LINQ to DataSet 需要对*system.data.datasetextensions.dll*和*的两*个附加引用。</span><span class="sxs-lookup"><span data-stu-id="5ac38-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac38-108">如果是从命令提示符生成，则必须在 *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*中手动引用与 LINQ 相关的 dll。</span><span class="sxs-lookup"><span data-stu-id="5ac38-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="5ac38-109">启用 LINQ to DataSet 功能</span><span class="sxs-lookup"><span data-stu-id="5ac38-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="5ac38-110">按照以下步骤在现有项目中启用 LINQ to DataSet 功能。</span><span class="sxs-lookup"><span data-stu-id="5ac38-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="5ac38-111">添加对 System.data.datasetextensions.dll **、system.web**和 system.object的引用。</span><span class="sxs-lookup"><span data-stu-id="5ac38-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="5ac38-112">在**解决方案资源管理器**中，右键单击 "**引用**" 节点，然后选择 "**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="5ac38-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="5ac38-113">在 "**引用管理器** **" 对话框**中 **，选择 "** **system.data.datasetextensions.dll**"。</span><span class="sxs-lookup"><span data-stu-id="5ac38-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="5ac38-114">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="5ac38-114">Select **OK**.</span></span>

1. <span data-ttu-id="5ac38-115">为**system.web**和**system.object**添加[using](../../../csharp/language-reference/keywords/using-directive.md)指令（或 Visual Basic 中的[Imports 语句](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)）。</span><span class="sxs-lookup"><span data-stu-id="5ac38-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="5ac38-116">根据你连接到`using`数据库的方式`Imports` ，还可以根据需要添加**SqlClient** **的指令**（或语句）。</span><span class="sxs-lookup"><span data-stu-id="5ac38-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ac38-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ac38-117">See also</span></span>

- [<span data-ttu-id="5ac38-118">LINQ to DataSet 入门</span><span class="sxs-lookup"><span data-stu-id="5ac38-118">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
