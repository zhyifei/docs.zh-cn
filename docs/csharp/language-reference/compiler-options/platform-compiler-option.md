---
title: "-platform（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: "46"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5d35a91805f6189f60803056c541ce8344c024f0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="platform-c-compiler-options"></a><span data-ttu-id="20b49-102">/platform（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="20b49-102">/platform (C# Compiler Options)</span></span>
<span data-ttu-id="20b49-103">指定公共语言运行时 (CLR) 的哪个版本可以运行程序集。</span><span class="sxs-lookup"><span data-stu-id="20b49-103">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b49-104">语法</span><span class="sxs-lookup"><span data-stu-id="20b49-104">Syntax</span></span>  
  
```console  
/platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20b49-105">参数</span><span class="sxs-lookup"><span data-stu-id="20b49-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="20b49-106">anycpu（默认值）、anycpu32bitpreferred、ARM、x64、x86 或 Itanium。</span><span class="sxs-lookup"><span data-stu-id="20b49-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20b49-107">备注</span><span class="sxs-lookup"><span data-stu-id="20b49-107">Remarks</span></span>  
  
-   <span data-ttu-id="20b49-108">anycpu（默认值）将程序集编译成可在任意平台上运行。</span><span class="sxs-lookup"><span data-stu-id="20b49-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="20b49-109">您的应用程序将尽可能作为 64 位进程运行；当只有 32 位模式可用时，才会回退到 32 位。</span><span class="sxs-lookup"><span data-stu-id="20b49-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="20b49-110">anycpu32bitpreferred 将程序集编译成可在任意平台上运行。</span><span class="sxs-lookup"><span data-stu-id="20b49-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="20b49-111">在同时支持 64 位和 32 位应用程序的系统上，您的应用程序将以32 位模式运行。</span><span class="sxs-lookup"><span data-stu-id="20b49-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="20b49-112">可以仅为针对 .NET Framework 4.5 的项目指定此选项。</span><span class="sxs-lookup"><span data-stu-id="20b49-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="20b49-113">ARM 将程序集编译成可以在具有高级 RISC 计算机 (ARM) 处理器的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="20b49-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="20b49-114">x64 将程序集编译成可由支持 AMD64 或 EM64T 指令集的计算机上的 64 位 CLR 运行。</span><span class="sxs-lookup"><span data-stu-id="20b49-114">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="20b49-115">x86 将程序集编译成可由 32 位、x86 可兼容 CLR 运行。</span><span class="sxs-lookup"><span data-stu-id="20b49-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>  
  
-   <span data-ttu-id="20b49-116">Itanium 将程序集编译成可由配有 Itanium 处理器的计算机上的 64 位 CLR 运行。</span><span class="sxs-lookup"><span data-stu-id="20b49-116">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="20b49-117">在 64 位 Windows 操作系统上：</span><span class="sxs-lookup"><span data-stu-id="20b49-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="20b49-118">用 /platform:x86 编译的程序集将在 WOW64 下运行的 32 位 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="20b49-118">Assemblies compiled with **/platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="20b49-119">用 /platform:anycpu 编译的 DLL 将在加载它的进程所在的同一 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="20b49-119">A DLL compiled with the **/platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="20b49-120">用 /platform:anycpu 编译的可执行文件将在 64 位 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="20b49-120">Executables that are compiled with the **/platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="20b49-121">用 /platform:anycpu32bitpreferred 编译的可执行文件将在 32 位 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="20b49-121">Executables compiled with **/platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="20b49-122">anycpu32bitpreferred 设置只对可执行 (.exe) 文件有效，并且需要 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="20b49-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="20b49-123">有关开发 Windows 64 位操作系统上运行的应用程序的详细信息，请参阅 [64 位应用程序](../../../framework/64-bit-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="20b49-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="20b49-124">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="20b49-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="20b49-125">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="20b49-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="20b49-126">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="20b49-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="20b49-127">修改“目标平台”属性，对于针对 .NET Framework 4.5 的项目，选择或清除“首选 32 位”复选框。</span><span class="sxs-lookup"><span data-stu-id="20b49-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="20b49-128">请注意，/platform 在 Visual C# Express 的开发环境中不可用。</span><span class="sxs-lookup"><span data-stu-id="20b49-128">**Note /platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="20b49-129">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>。</span><span class="sxs-lookup"><span data-stu-id="20b49-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20b49-130">示例</span><span class="sxs-lookup"><span data-stu-id="20b49-130">Example</span></span>  
 <span data-ttu-id="20b49-131">下面的示例演示如何使用 /platform 选项来指定只有 64 位 Windows 操作系统上的 64 位 CLR 才能运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="20b49-131">The following example shows how to use the **/platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc /platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="20b49-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="20b49-132">See Also</span></span>  
 [<span data-ttu-id="20b49-133">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="20b49-133">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="20b49-134">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="20b49-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
