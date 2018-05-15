---
title: 如何：在 Visual Studio 中创建 LINQ to DataSet 项目
ms.date: 03/30/2017
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 094d766146fe55a865713a4672a2bee6a838ff55
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="bf304-102">如何：在 Visual Studio 中创建 LINQ to DataSet 项目</span><span class="sxs-lookup"><span data-stu-id="bf304-102">How to: Create a LINQ to DataSet Project In Visual Studio</span></span>
<span data-ttu-id="bf304-103">不同类型的 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 项目需要某些导入的命名空间 (Visual Basic) 或 `using` 指令 (C#) 和引用。</span><span class="sxs-lookup"><span data-stu-id="bf304-103">The different types of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] projects require certain imported namespaces (Visual Basic) or `using` directives (C#) and references.</span></span> <span data-ttu-id="bf304-104">最低要求是对 System.Core.dll 的引用和针对 `using` 的 <xref:System.Linq> 指令。</span><span class="sxs-lookup"><span data-stu-id="bf304-104">The minimum requirement is a reference to System.Core.dll and a `using` directive for <xref:System.Linq>.</span></span> <span data-ttu-id="bf304-105">默认情况下，如果创建一个新的 [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] 项目，这些都可以自动提供。</span><span class="sxs-lookup"><span data-stu-id="bf304-105">By default, these are supplied if you create a new [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] project.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="bf304-106"> 还需要对 System.Data.dll 和 System.Data.DataSetExtensions.dll 的引用以及 `Imports` (Visual Basic) 或 `using` (C#) 指令。</span><span class="sxs-lookup"><span data-stu-id="bf304-106"> also requires a reference to System.Data.dll and System.Data.DataSetExtensions.dll and an `Imports` (Visual Basic) or `using` (C#) directive.</span></span>  
  
 <span data-ttu-id="bf304-107">如果您要从早期版本的 Visual Studio 升级某个项目，则可能必须手动提供这些与 LINQ 相关的引用。</span><span class="sxs-lookup"><span data-stu-id="bf304-107">If you are upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span> <span data-ttu-id="bf304-108">您可能还必须将项目手动设置为面向 .NET Framework 3.5 版。</span><span class="sxs-lookup"><span data-stu-id="bf304-108">You might also have to manually set the project to target the .NET Framework version 3.5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf304-109">如果你要在命令提示符下生成的则必须手动引用中与 LINQ 相关的 Dll `drive` **:** \Program Files\Reference Assemblies\Microsoft\Framework\v3.5。</span><span class="sxs-lookup"><span data-stu-id="bf304-109">If you are building from a command prompt, you must manually reference the LINQ-related DLLs in `drive`**:** \Program Files\Reference Assemblies\Microsoft\Framework\v3.5.</span></span>  
  
### <a name="to-target-the-net-framework-35"></a><span data-ttu-id="bf304-110">面向 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="bf304-110">To target the .NET Framework 3.5</span></span>  
  
1.  <span data-ttu-id="bf304-111">在 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] 中，创建一个新的 Visual Basic 或 C# 项目。</span><span class="sxs-lookup"><span data-stu-id="bf304-111">In [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], create a new Visual Basic or C# project.</span></span> <span data-ttu-id="bf304-112">或者，您可以打开一个在 Visual Studio 2005 中创建的 Visual Basic 或 C# 项目，并按照提示将其转换为 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="bf304-112">Alternatively, you can open a Visual Basic or C# project that was created in Visual Studio 2005 and follow the prompts to convert it to a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="bf304-113">对于 C# 项目，单击**项目**菜单，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="bf304-113">For a C# project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="bf304-114">在**应用程序**属性页中，选择中的.NET Framework 3.5**目标框架**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="bf304-114">In the **Application** property page, select .NET Framework 3.5 in the **Target Framework** drop-down list.</span></span>  
  
3.  <span data-ttu-id="bf304-115">对于 Visual Basic 项目中，单击**项目**菜单，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="bf304-115">For a Visual Basic project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="bf304-116">在**编译**属性页中，单击**高级编译选项**，然后选择中的.NET Framework 3.5**目标 Framework （所有配置）** 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="bf304-116">In the **Compile** property page, click **Advanced Compile Options** and then select .NET Framework 3.5 in the **Target Framework (all configurations)** drop-down list.</span></span>  
  
4.  <span data-ttu-id="bf304-117">上**项目**菜单上，单击**添加引用**，单击 **.NET**选项卡上，向下滚动到**System.Core**，请单击它，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bf304-117">On the **Project** menu, click **Add Reference**, click the **.NET** tab, scroll down to **System.Core**, click it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="bf304-118">向源代码文件或项目中添加用于 `using` 的 <xref:System.Linq> 指令或导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bf304-118">Add a `using` directive or imported namespace for <xref:System.Linq> to your source code file or project.</span></span>  
  
     <span data-ttu-id="bf304-119">有关详细信息，请参阅[using 指令](~/docs/csharp/language-reference/keywords/using-directive.md)或[如何： 添加或删除已导入命名空间 (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="bf304-119">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
### <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="bf304-120">启用 LINQ to DataSet 功能</span><span class="sxs-lookup"><span data-stu-id="bf304-120">To enable LINQ to DataSet functionality</span></span>  
  
1.  <span data-ttu-id="bf304-121">必要时，按照本主题前面的步骤添加对 System.Core.dll 的引用和用于 System.Linq 的 `using` 指令或导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bf304-121">If necessary, follow the steps earlier in this topic to add a reference to System.Core.dll and a `using` directive or imported namespace for System.Linq.</span></span>  
  
2.  <span data-ttu-id="bf304-122">在 C# 或 Visual Basic 中，单击**项目**菜单，，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="bf304-122">In C# or Visual Basic, click the **Project** menu, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="bf304-123">在**添加引用**对话框中，单击 **.NET**选项卡上，如果不在最前面。</span><span class="sxs-lookup"><span data-stu-id="bf304-123">In the **Add Reference** dialog box, click the **.NET** tab if it is not on top.</span></span> <span data-ttu-id="bf304-124">向下滚动到**System.Data**和**System.Data.DataSetExtensions**并单击它们。</span><span class="sxs-lookup"><span data-stu-id="bf304-124">Scroll down to **System.Data** and **System.Data.DataSetExtensions** and click on them.</span></span> <span data-ttu-id="bf304-125">单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="bf304-125">Click the **OK** button.</span></span>  
  
4.  <span data-ttu-id="bf304-126">向源代码文件或项目中添加用于 `using` 的 <xref:System.Data> 指令或导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bf304-126">Add a `using` directive or imported namespace for <xref:System.Data> to your source code file or project.</span></span> <span data-ttu-id="bf304-127">有关详细信息，请参阅[using 指令](~/docs/csharp/language-reference/keywords/using-directive.md)或[如何： 添加或删除已导入命名空间 (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="bf304-127">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
5.  <span data-ttu-id="bf304-128">添加对 System.Data.DataSetExtensions.dll 的引用以便可以使用 LINQ to Dataset 的功能。</span><span class="sxs-lookup"><span data-stu-id="bf304-128">Add a reference to System.Data.DataSetExtensions.dll for LINQ to Dataset functionality.</span></span> <span data-ttu-id="bf304-129">添加对 System.Data.dll 的引用（如果尚不存在）。</span><span class="sxs-lookup"><span data-stu-id="bf304-129">Add a reference to System.Data.dll if it does not already exist.</span></span>  
  
6.  <span data-ttu-id="bf304-130">或者，添加用于 `using` 或 `System.Data.Common` 的 `System.Data.SqlClient` 指令或导入的命名空间，具体取决于如何连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="bf304-130">Optionally, add a `using` directive or imported namespace for `System.Data.Common` or `System.Data.SqlClient`, depending on how you connect to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf304-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf304-131">See Also</span></span>  
 [<span data-ttu-id="bf304-132">入门</span><span class="sxs-lookup"><span data-stu-id="bf304-132">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [<span data-ttu-id="bf304-133">LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="bf304-133">Getting Started with LINQ</span></span>](http://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
