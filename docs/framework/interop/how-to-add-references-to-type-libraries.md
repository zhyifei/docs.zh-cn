---
title: "如何：添加对类型库的引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e80c4bf5142a9bbbd2b7f75d67553db73f0ff22
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="3810a-102">如何：添加对类型库的引用</span><span class="sxs-lookup"><span data-stu-id="3810a-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="3810a-103">当添加对类型库的引用时，Visual Studio 将生成包含元数据的互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="3810a-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="3810a-104">如果主互操作程序集可用，则 Visual Studio 在生成新的互操作程序集之前将使用现有程序集。</span><span class="sxs-lookup"><span data-stu-id="3810a-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="3810a-105">在 Visual Studio 中添加对类型库的引用</span><span class="sxs-lookup"><span data-stu-id="3810a-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="3810a-106">在计算机上安装 COM DLL 或 EXE 文件，除非 Windows Setup.exe 文件会为你执行此安装。</span><span class="sxs-lookup"><span data-stu-id="3810a-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="3810a-107">选择“项目”、“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="3810a-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="3810a-108">在引用管理器中，选择“COM”。</span><span class="sxs-lookup"><span data-stu-id="3810a-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="3810a-109">从列表中选择类型库，或通过浏览选择 .tlb 文件。</span><span class="sxs-lookup"><span data-stu-id="3810a-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="3810a-110">选择 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3810a-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="3810a-111">在解决方案资源管理器中，打开刚刚添加的引用快捷菜单，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="3810a-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="3810a-112">在“属性”窗口中，确保将“嵌入互操作类型”属性设置为“True”。</span><span class="sxs-lookup"><span data-stu-id="3810a-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="3810a-113">通过此设置，Visual Studio 将会在可执行文件中嵌入 COM 类型的类型信息，从而不必将主互操作程序集与你的应用一起部署。</span><span class="sxs-lookup"><span data-stu-id="3810a-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3810a-114">根据你使用的 Visual Studio 版本，菜单和对话框选项可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="3810a-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="3810a-115">添加对类型库的引用以进行命令行编译</span><span class="sxs-lookup"><span data-stu-id="3810a-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="3810a-116">按照[如何从类型库中生成互操作程序集](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)中所述，生成互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="3810a-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="3810a-117">配合使用 [/link（C# 编译器选项）](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)或 [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) 编译器选项与互操作程序集名称，将 COM 类型的类型信息嵌入到可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="3810a-117">Use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3810a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3810a-118">See Also</span></span>  
 [<span data-ttu-id="3810a-119">将类型库作为程序集导入</span><span class="sxs-lookup"><span data-stu-id="3810a-119">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="3810a-120">向 .NET Framework 公开 COM 组件</span><span class="sxs-lookup"><span data-stu-id="3810a-120">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="3810a-121">演练：嵌入 Microsoft Office 程序集中的类型信息</span><span class="sxs-lookup"><span data-stu-id="3810a-121">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="3810a-122">演练：嵌入托管程序集中的类型</span><span class="sxs-lookup"><span data-stu-id="3810a-122">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="3810a-123">/link（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="3810a-123">/link (C# Compiler Options)</span></span>](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)  
 [<span data-ttu-id="3810a-124">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3810a-124">/link (Visual Basic)</span></span>](~/docs/visual-basic/reference/command-line-compiler/link.md)
