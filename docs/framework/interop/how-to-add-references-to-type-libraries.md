---
title: 如何：添加对类型库的引用
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3fda2af84ff74e129c36dc966bad247bdf9e20
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427131"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="f1287-102">如何：添加对类型库的引用</span><span class="sxs-lookup"><span data-stu-id="f1287-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="f1287-103">当添加对类型库的引用时，Visual Studio 将生成包含元数据的互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="f1287-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="f1287-104">如果主互操作程序集可用，则 Visual Studio 在生成新的互操作程序集之前将使用现有程序集。</span><span class="sxs-lookup"><span data-stu-id="f1287-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="f1287-105">在 Visual Studio 中添加对类型库的引用</span><span class="sxs-lookup"><span data-stu-id="f1287-105">To add a reference to a type library in Visual Studio</span></span>  
  
1. <span data-ttu-id="f1287-106">在计算机上安装 COM DLL 或 EXE 文件，除非 Windows Setup.exe 文件会为你执行此安装。</span><span class="sxs-lookup"><span data-stu-id="f1287-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2. <span data-ttu-id="f1287-107">选择“项目”、“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="f1287-107">Choose **Project**, **Add Reference**.</span></span>  
  
3. <span data-ttu-id="f1287-108">在引用管理器中，选择“COM”。</span><span class="sxs-lookup"><span data-stu-id="f1287-108">In the Reference Manager, choose **COM**.</span></span>  
  
4. <span data-ttu-id="f1287-109">从列表中选择类型库，或通过浏览选择 .tlb 文件。</span><span class="sxs-lookup"><span data-stu-id="f1287-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5. <span data-ttu-id="f1287-110">选择 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f1287-110">Choose **OK**.</span></span>  
  
6. <span data-ttu-id="f1287-111">在解决方案资源管理器中，打开刚刚添加的引用快捷菜单，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="f1287-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7. <span data-ttu-id="f1287-112">在“属性”窗口中，确保将“嵌入互操作类型”属性设置为“True”。</span><span class="sxs-lookup"><span data-stu-id="f1287-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="f1287-113">通过此设置，Visual Studio 将会在可执行文件中嵌入 COM 类型的类型信息，从而不必将主互操作程序集与你的应用一起部署。</span><span class="sxs-lookup"><span data-stu-id="f1287-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1287-114">根据你使用的 Visual Studio 版本，菜单和对话框选项可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="f1287-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="f1287-115">添加对类型库的引用以进行命令行编译</span><span class="sxs-lookup"><span data-stu-id="f1287-115">To add a reference to a type library for command-line compilation</span></span>  
  
1. <span data-ttu-id="f1287-116">按后列文章中所述，生成一个互操作程序集：[如何：从类型库生成互操作程序集](how-to-generate-interop-assemblies-from-type-libraries.md)。</span><span class="sxs-lookup"><span data-stu-id="f1287-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2. <span data-ttu-id="f1287-117">配合使用 [/link（C# 编译器选项）](../../csharp/language-reference/compiler-options/link-compiler-option.md)或 [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) 编译器选项与互操作程序集名称，将 COM 类型的类型信息嵌入到可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="f1287-117">Use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1287-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1287-118">See also</span></span>

- [<span data-ttu-id="f1287-119">将类型库作为程序集导入</span><span class="sxs-lookup"><span data-stu-id="f1287-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="f1287-120">向 .NET Framework 公开 COM 组件</span><span class="sxs-lookup"><span data-stu-id="f1287-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="f1287-121">演练：在 Visual Studio 中嵌入托管程序集中的类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="f1287-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) 
- [<span data-ttu-id="f1287-122">演练：在 Visual Studio 中嵌入托管程序集中的类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1287-122">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="f1287-123">/link（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="f1287-123">/link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="f1287-124">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1287-124">/link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
