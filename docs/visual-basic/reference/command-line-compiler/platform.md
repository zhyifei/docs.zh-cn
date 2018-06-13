---
title: -平台 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec3a7e01e62b60688080fee95cf70e0ed38917f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656173"
---
# <a name="-platform-visual-basic"></a><span data-ttu-id="3f938-102">-平台 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f938-102">-platform (Visual Basic)</span></span>
<span data-ttu-id="3f938-103">指定公共语言运行时 (CLR) 的哪个平台版本可以运行输出文件。</span><span class="sxs-lookup"><span data-stu-id="3f938-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f938-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f938-104">Syntax</span></span>  
  
```  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f938-105">自变量</span><span class="sxs-lookup"><span data-stu-id="3f938-105">Arguments</span></span>  
  
|<span data-ttu-id="3f938-106">术语</span><span class="sxs-lookup"><span data-stu-id="3f938-106">Term</span></span>|<span data-ttu-id="3f938-107">定义</span><span class="sxs-lookup"><span data-stu-id="3f938-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="3f938-108">将程序集编译成可由 32 位、x86 可兼容 CLR 运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="3f938-109">将程序集编译成可由支持 AMD64 或 EM64T 指令集的计算机上的 64 位 CLR 运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="3f938-110">将程序集编译成可由配有 Itanium 处理器的计算机上的 64 位 CLR 运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="3f938-111">将程序集编译成可在配有高级 RISC 计算机 (ARM) 处理器的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="3f938-112">将程序集编译成可在任意平台上运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="3f938-113">应用程序将作为 32 位应用程序在 Windows 的 32 位版本上运行，作为 64 位应用程序在 Windows 的 64 位版本上运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="3f938-114">此标志为默认值。</span><span class="sxs-lookup"><span data-stu-id="3f938-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="3f938-115">将程序集编译成可在任意平台上运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="3f938-116">应用程序将作为 32 位 应用程序在 Windows 的 32 位版本和 64 位版本上运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="3f938-117">此标志仅对可执行文件 (.EXE) 有效且需要 [!INCLUDE[net_v45](~/includes/net-v45-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3f938-117">This flag is valid only for executables (.EXE) and requires [!INCLUDE[net_v45](~/includes/net-v45-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f938-118">备注</span><span class="sxs-lookup"><span data-stu-id="3f938-118">Remarks</span></span>  
 <span data-ttu-id="3f938-119">使用 `-platform` 选项来指定输出文件所面向的处理器类型。</span><span class="sxs-lookup"><span data-stu-id="3f938-119">Use the `-platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="3f938-120">通常，无论平台如何，Visual Basic 内编写的 .NET Framework 程序集将运行相同内容。</span><span class="sxs-lookup"><span data-stu-id="3f938-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="3f938-121">但是，存在一些不同平台行为不同的情况。</span><span class="sxs-lookup"><span data-stu-id="3f938-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="3f938-122">这些常见的情况是：</span><span class="sxs-lookup"><span data-stu-id="3f938-122">These common cases are:</span></span>  
  
-   <span data-ttu-id="3f938-123">结构中包含大小随平台而改变的成员，如任何指针类型。</span><span class="sxs-lookup"><span data-stu-id="3f938-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
-   <span data-ttu-id="3f938-124">指针算术包含固定大小。</span><span class="sxs-lookup"><span data-stu-id="3f938-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
-   <span data-ttu-id="3f938-125">平台调用错误，或使用句柄的 `Integer` 而非 <xref:System.IntPtr> 的 COM 声明不正确。</span><span class="sxs-lookup"><span data-stu-id="3f938-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
-   <span data-ttu-id="3f938-126">将 <xref:System.IntPtr> 强制转换为 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="3f938-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
-   <span data-ttu-id="3f938-127">将平台调用或 COM 互操作与不存在于任何平台的组件一起使用。</span><span class="sxs-lookup"><span data-stu-id="3f938-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="3f938-128">**-平台**选项将减少一些问题，如果你知道你的代码将在运行的体系结构进行的假设。</span><span class="sxs-lookup"><span data-stu-id="3f938-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="3f938-129">尤其是在下列情况下：</span><span class="sxs-lookup"><span data-stu-id="3f938-129">Specifically:</span></span>  
  
-   <span data-ttu-id="3f938-130">如果你针对 64 位平台且应用程序在 32 位计算机上运行，则相对于不使用此开关而出现的错误，此错误消息更早出现且更加针对问题。</span><span class="sxs-lookup"><span data-stu-id="3f938-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
-   <span data-ttu-id="3f938-131">如果你在选项上设置 `x86` 标志且之后应用程序在 64 位计算机上运行，则应用程序将在 WOW 子系统中运行而不是在本机上运行。</span><span class="sxs-lookup"><span data-stu-id="3f938-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="3f938-132">在 64 位 Windows 操作系统上：</span><span class="sxs-lookup"><span data-stu-id="3f938-132">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="3f938-133">用 `-platform:x86` 编译的程序集将在 WOW64 下运行的 32 位 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="3f938-133">Assemblies compiled with `-platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="3f938-134">用 `-platform:anycpu` 编译的可执行文件将在 64 位 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="3f938-134">Executables compiled with the `-platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="3f938-135">用 `-platform:anycpu` 编译的 DLL 将在加载它的进程所在的同一 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="3f938-135">A DLL compiled with the `-platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
-   <span data-ttu-id="3f938-136">用 `-platform:anycpu32bitpreferred` 编译的可执行文件将在 32 位 CLR 上执行。</span><span class="sxs-lookup"><span data-stu-id="3f938-136">Executables that are compiled with `-platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="3f938-137">了解如何开发 64 位版本的 Windows 上运行的应用程序的详细信息，请参阅[64 位应用程序](../../../framework/64-bit-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="3f938-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a><span data-ttu-id="3f938-138">若要设置的 Visual Studio IDE 中的平台</span><span class="sxs-lookup"><span data-stu-id="3f938-138">To set -platform in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="3f938-139">在**解决方案资源管理器**，选择项目，打开**项目**菜单，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3f938-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3f938-140">上**编译**选项卡上，选中或清除**首选 32 位**复选框，或者，在**目标 CPU**列表中，选择一个值。</span><span class="sxs-lookup"><span data-stu-id="3f938-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="3f938-141">有关详细信息，请参阅[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="3f938-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f938-142">示例</span><span class="sxs-lookup"><span data-stu-id="3f938-142">Example</span></span>  
 <span data-ttu-id="3f938-143">下例阐释使用 `-platform` 编译器选项的方式。</span><span class="sxs-lookup"><span data-stu-id="3f938-143">The following example illustrates how to use the `-platform` compiler option.</span></span>  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f938-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f938-144">See Also</span></span>  
 [<span data-ttu-id="3f938-145">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f938-145">/target (Visual Basic)</span></span>](target.md)  
 [<span data-ttu-id="3f938-146">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="3f938-146">Visual Basic Command-Line Compiler</span></span>](index.md)  
 [<span data-ttu-id="3f938-147">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="3f938-147">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
