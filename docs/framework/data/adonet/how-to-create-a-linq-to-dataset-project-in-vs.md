---
title: 创建 LINQ to DataSet 项目在 Visual Studio 中
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980724"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="50d0d-102">如何： 创建 LINQ to DataSet 项目在 Visual Studio 中</span><span class="sxs-lookup"><span data-stu-id="50d0d-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="50d0d-103">不同类型的 LINQ 项目需要某些程序集引用和导入命名空间 (Visual Basic) 或[使用](../../../csharp/language-reference/keywords/using-directive.md)指令 (C#)。</span><span class="sxs-lookup"><span data-stu-id="50d0d-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="50d0d-104">LINQ 的最低要求是对的引用*System.Core.dll*和一个`using`指令<xref:System.Linq>。</span><span class="sxs-lookup"><span data-stu-id="50d0d-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="50d0d-105">这些要求被提供默认情况下，如果在 Visual Studio 2017 中创建新 C# 控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="50d0d-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="50d0d-106">如果您要从 Visual Studio 的早期版本升级项目，您可能必须手动提供这些与 LINQ 相关的引用。</span><span class="sxs-lookup"><span data-stu-id="50d0d-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="50d0d-107">LINQ 到数据集需要两个其他引用*System.Data.dll*并*System.Data.DataSetExtensions.dll*。</span><span class="sxs-lookup"><span data-stu-id="50d0d-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="50d0d-108">如果您正在构建的命令提示符下，则必须手动引用中与 LINQ 相关的 Dll *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*。</span><span class="sxs-lookup"><span data-stu-id="50d0d-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="50d0d-109">启用 LINQ to DataSet 功能</span><span class="sxs-lookup"><span data-stu-id="50d0d-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="50d0d-110">请按照下列步骤以启用 LINQ to DataSet 中的现有项目的功能。</span><span class="sxs-lookup"><span data-stu-id="50d0d-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="50d0d-111">将引用添加到**System.Core**， **System.Data**，并**System.Data.DataSetExtensions**。</span><span class="sxs-lookup"><span data-stu-id="50d0d-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="50d0d-112">在中**解决方案资源管理器**，右键单击**引用**节点，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="50d0d-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="50d0d-113">在中**引用管理器**对话框中，选择**System.Core**， **System.Data**，以及**System.Data.DataSetExtensions**。</span><span class="sxs-lookup"><span data-stu-id="50d0d-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="50d0d-114">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="50d0d-114">Select **OK**.</span></span>

1. <span data-ttu-id="50d0d-115">添加[使用](../../../csharp/language-reference/keywords/using-directive.md)指令 (或[Imports 语句](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)在 Visual Basic 中) 的**System.Data**并**System.Linq**。</span><span class="sxs-lookup"><span data-stu-id="50d0d-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="50d0d-116">（可选） 添加`using`指令 (或`Imports`语句) 的**System.Data.Common**或**System.Data.SqlClient**，取决于如何连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="50d0d-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="50d0d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="50d0d-117">See also</span></span>

- [<span data-ttu-id="50d0d-118">开始使用 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="50d0d-118">Get started with LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
