---
title: "64 位应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [C++], 64-bit
- 64-bit applications [C++]
- 64-bit programming [C++]
ms.assetid: fd4026bc-2c3d-4b27-86dc-ec5e96018181
caps.latest.revision: "53"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ee85512cde0ce50e6a5c34cc5f6acc531c24bc0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="64-bit-applications"></a><span data-ttu-id="430ea-102">64 位应用程序</span><span class="sxs-lookup"><span data-stu-id="430ea-102">64-bit Applications</span></span>
<span data-ttu-id="430ea-103">编译应用程序时，您可以将其指定为在 Windows 64 位操作系统上作为本机应用程序或在 WOW64（Windows 64 位下的 Windows 32 位）下运行。</span><span class="sxs-lookup"><span data-stu-id="430ea-103">When you compile an application, you can specify that it should run on a Windows 64-bit operating system either as a native application or under WOW64 (Windows 32-bit on Windows 64-bit).</span></span> <span data-ttu-id="430ea-104">WOW64 是一种兼容性环境，它使 32 位应用能够在 64 位系统上运行。</span><span class="sxs-lookup"><span data-stu-id="430ea-104">WOW64 is a compatibility environment that enables a 32-bit application to run on a 64-bit system.</span></span> <span data-ttu-id="430ea-105">WOW64 包括在所有 64 位版本的 Windows 操作系统中。</span><span class="sxs-lookup"><span data-stu-id="430ea-105">WOW64 is included in all 64-bit versions of the Windows operating system.</span></span>  
  
## <a name="running-32-bit-vs-64-bit-applications-on-windows"></a><span data-ttu-id="430ea-106">在 Windows 上运行 32 位与64 位应用程序</span><span class="sxs-lookup"><span data-stu-id="430ea-106">Running 32-bit vs. 64-bit Applications on Windows</span></span>  
 <span data-ttu-id="430ea-107">在 64 位操作系统上，所有基于 .NET Framework 1.0 或 1.1 生成的应用程序都会被视为 32 位应用程序，并始终在 WOW64 和 32 位公共语言运行时 (CLR) 下执行。</span><span class="sxs-lookup"><span data-stu-id="430ea-107">All applications that are built on the .NET Framework 1.0 or 1.1 are treated as 32-bit applications on a 64-bit operating system and are always executed under WOW64 and the 32-bit common language runtime (CLR).</span></span> <span data-ttu-id="430ea-108">基于 [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)] 或更晚版本生成的 32 位应用程序在 64 位系统上也会的 WOW64 下运行。</span><span class="sxs-lookup"><span data-stu-id="430ea-108">32-bit applications that are built on the [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)] or later versions also run under WOW64 on 64-bit systems.</span></span>  
  
 <span data-ttu-id="430ea-109">在 x86 计算机上，Visual Studio 会安装 32 位版本的 CLR，而在 64 位 Windows 计算机上会同时安装 32 位版本和适当的 64 位版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="430ea-109">Visual Studio installs the 32-bit version of the CLR on an x86 computer, and both the 32-bit version and the appropriate 64-bit version of the CLR on a 64-bit Windows computer.</span></span> <span data-ttu-id="430ea-110">（因为 Visual Studio 是一个 32 位应用程序，所以当安装到 64 位系统上时，它会在 WOW64 下运行。）</span><span class="sxs-lookup"><span data-stu-id="430ea-110">(Because Visual Studio is a 32-bit application, when it is installed on a 64-bit system, it runs under WOW64.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="430ea-111">由于 Itanium 处理器系列的 x86 仿真和 WOW64 子系统设计，仅限在一个处理器上执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="430ea-111">Because of the design of x86 emulation and the WOW64 subsystem for the Itanium processor family, applications are restricted to execution on one processor.</span></span> <span data-ttu-id="430ea-112">这些因素会降低在基于 Itanium 的系统上运行的 32 位 .NET Framework 应用程序的性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="430ea-112">These factors reduce the performance and scalability of 32-bit .NET Framework applications that run on Itanium-based systems.</span></span> <span data-ttu-id="430ea-113">我们建议您使用 [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)]，它包括对基于 Itanium 系统的本机 64 位支持，以提升性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="430ea-113">We recommend that you use the [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)], which includes native 64-bit support for Itanium-based systems, for increased performance and scalability.</span></span>  
  
 <span data-ttu-id="430ea-114">默认情况下，在 64 位 Windows 操作系统上运行 64 位托管应用程序时，您可以创建一个不超过 2 GB 的对象。</span><span class="sxs-lookup"><span data-stu-id="430ea-114">By default, when you run a 64-bit managed application on a 64-bit Windows operating system, you can create an object of no more than 2 gigabytes (GB).</span></span> <span data-ttu-id="430ea-115">然而，在 [!INCLUDE[net_v45](../../includes/net-v45-md.md)] 中，您可以增加该限制。</span><span class="sxs-lookup"><span data-stu-id="430ea-115">However, in the [!INCLUDE[net_v45](../../includes/net-v45-md.md)], you can increase this limit.</span></span>  <span data-ttu-id="430ea-116">有关详细信息，请参阅 [\<gcAllowVeryLargeObjects> 元素](../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)。</span><span class="sxs-lookup"><span data-stu-id="430ea-116">For more information, see the [\<gcAllowVeryLargeObjects> element](../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md).</span></span>  
  
 <span data-ttu-id="430ea-117">很多程序集可在 32 位 CLR 和 64 位 CLR 上同样运行。</span><span class="sxs-lookup"><span data-stu-id="430ea-117">Many assemblies run identically on both the 32-bit CLR and the 64-bit CLR.</span></span> <span data-ttu-id="430ea-118">然而，因为包含下列一个或多个原因，对于不同的 CLR，有些程序可能会有不同表现：</span><span class="sxs-lookup"><span data-stu-id="430ea-118">However, some programs may behave differently, depending on the CLR, if they contain one or more of the following:</span></span>  
  
-   <span data-ttu-id="430ea-119">结构中包含大小随平台而改变的成员，例如任何指针类型。</span><span class="sxs-lookup"><span data-stu-id="430ea-119">Structures that contain members that change size depending on the platform (for example, any pointer type).</span></span>  
  
-   <span data-ttu-id="430ea-120">指针算术包含固定大小。</span><span class="sxs-lookup"><span data-stu-id="430ea-120">Pointer arithmetic that includes constant sizes.</span></span>  
  
-   <span data-ttu-id="430ea-121">平台调用错误，或使用句柄的 `Int32` 而非 `IntPtr` 的 COM 声明不正确。</span><span class="sxs-lookup"><span data-stu-id="430ea-121">Incorrect platform invoke or COM declarations that use `Int32` for handles instead of `IntPtr`.</span></span>  
  
-   <span data-ttu-id="430ea-122">将 `IntPtr` 转换到 `Int32` 的代码。</span><span class="sxs-lookup"><span data-stu-id="430ea-122">Code that casts `IntPtr` to `Int32`.</span></span>  
  
 <span data-ttu-id="430ea-123">有关如何移植 32 位应用程序在 64 位 CLR 上运行的详细信息，请参阅[迁移 32 位托管代码迁移至 64 位](https://msdn.microsoft.com/library/ms973190.aspx)。</span><span class="sxs-lookup"><span data-stu-id="430ea-123">For more information about how to port a 32-bit application to run on the 64-bit CLR, see [Migrating 32-bit Managed Code to 64-bit](https://msdn.microsoft.com/library/ms973190.aspx).</span></span>  
  
## <a name="general-64-bit-programming-information"></a><span data-ttu-id="430ea-124">常规 64 位编程信息</span><span class="sxs-lookup"><span data-stu-id="430ea-124">General 64-Bit Programming Information</span></span>  
 <span data-ttu-id="430ea-125">有关 64 位编程的常规信息，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="430ea-125">For general information about 64-bit programming, see the following documents:</span></span>  
  
-   <span data-ttu-id="430ea-126">有关 64 位 Windows 计算机上的 64 位版 CLR 的详细信息，请参阅 MSDN 网站上的 [.NET Framework 开发人员中心](http://go.microsoft.com/fwlink/?LinkId=37079)。</span><span class="sxs-lookup"><span data-stu-id="430ea-126">For more information about the 64-bit version of the CLR on a 64-bit Windows computer, see the [.NET Framework Developer Center](http://go.microsoft.com/fwlink/?LinkId=37079) on the MSDN website.</span></span>  
  
-   <span data-ttu-id="430ea-127">在 [!INCLUDE[winsdkshort](../../includes/winsdkshort-md.md)] 文档中，请参阅 [64 位 Windows 编程指南](http://go.microsoft.com/fwlink/p/?LinkId=253512)。</span><span class="sxs-lookup"><span data-stu-id="430ea-127">In the [!INCLUDE[winsdkshort](../../includes/winsdkshort-md.md)] documentation, see [Programming Guide for 64-bit Windows](http://go.microsoft.com/fwlink/p/?LinkId=253512).</span></span>  
  
-   <span data-ttu-id="430ea-128">有关如何下载 64 位版 CLR 的信息，请参阅 MSDN 网站上的 [.NET Framework 开发人员中心下载](http://go.microsoft.com/fwlink/?LinkId=50953)。</span><span class="sxs-lookup"><span data-stu-id="430ea-128">For information about how to download a 64-bit version of the CLR, see [.NET Framework Developer Center Downloads](http://go.microsoft.com/fwlink/?LinkId=50953) on the MSDN website.</span></span>  
  
-   <span data-ttu-id="430ea-129">有关 Visual Studio 对创建 64 位应用程序提供的支持的信息，请参阅 [Visual Studio IDE 64 位支持](http://msdn.microsoft.com/library/b08ff3ad-c6fd-468f-94d5-01a61aab6833)。</span><span class="sxs-lookup"><span data-stu-id="430ea-129">For information about Visual Studio support for creating 64-bit applications, see [Visual Studio IDE 64-Bit Support](http://msdn.microsoft.com/library/b08ff3ad-c6fd-468f-94d5-01a61aab6833).</span></span>  
  
## <a name="compiler-support-for-creating-64-bit-applications"></a><span data-ttu-id="430ea-130">创建 64 位应用程序的编译器支持</span><span class="sxs-lookup"><span data-stu-id="430ea-130">Compiler Support for Creating 64-Bit Applications</span></span>  
 <span data-ttu-id="430ea-131">默认情况下，如果您使用 .NET Framework 在 32 位或 64 位计算机中生成一个应用程序，该应用程序将会在 64 位计算机中作为本机应用程序运行（即不是在 WOW64 下运行）。</span><span class="sxs-lookup"><span data-stu-id="430ea-131">By default, when you use the .NET Framework to build an application on either a 32-bit or a 64-bit computer, the application will run on a 64-bit computer as a native application (that is, not under WOW64).</span></span> <span data-ttu-id="430ea-132">有关如何使用 Visual Studio 编译器创建 64 位应用程序，并且应用程序会作为本机应用程序运行和/或在 WOW64 下运行的信息，请参阅下表中的文档。</span><span class="sxs-lookup"><span data-stu-id="430ea-132">The following table lists documents that explain how to use Visual Studio compilers to create 64-bit applications that will run as native, under WOW64, or both.</span></span>  
  
|<span data-ttu-id="430ea-133">编译器</span><span class="sxs-lookup"><span data-stu-id="430ea-133">Compiler</span></span>|<span data-ttu-id="430ea-134">编译器选项</span><span class="sxs-lookup"><span data-stu-id="430ea-134">Compiler option</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="430ea-135">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="430ea-135">Visual Basic</span></span>|[<span data-ttu-id="430ea-136">/platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="430ea-136">/platform (Visual Basic)</span></span>](~/docs/visual-basic/reference/command-line-compiler/platform.md)|  
|<span data-ttu-id="430ea-137">Visual C#</span><span class="sxs-lookup"><span data-stu-id="430ea-137">Visual C#</span></span>|[<span data-ttu-id="430ea-138">/platform（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="430ea-138">/platform (C# Compiler Options)</span></span>](~/docs/csharp/language-reference/compiler-options/platform-compiler-option.md)|  
|<span data-ttu-id="430ea-139">Visual C++</span><span class="sxs-lookup"><span data-stu-id="430ea-139">Visual C++</span></span>|<span data-ttu-id="430ea-140">可以通过使用 **/clr:safe** 创建与平台无关的 Microsoft 中间语言 (MSIL) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="430ea-140">You can create platform-agnostic, Microsoft intermediate language (MSIL) applications by using **/clr:safe**.</span></span> <span data-ttu-id="430ea-141">有关详细信息，请参阅 [/clr（公共语言运行时编译）](/cpp/build/reference/clr-common-language-runtime-compilation)。</span><span class="sxs-lookup"><span data-stu-id="430ea-141">For more information, see [/clr (Common Language Runtime Compilation)](/cpp/build/reference/clr-common-language-runtime-compilation).</span></span><br /><br /> <span data-ttu-id="430ea-142">Visual c++ 为每个 64 位操作系统均包括一个单独的编译器。</span><span class="sxs-lookup"><span data-stu-id="430ea-142">Visual C++ includes a separate compiler for each 64-bit operating system.</span></span> <span data-ttu-id="430ea-143">有关如何使用 Visual C++ 创建可在 64 位 Windows 操作系统上运行的本机应用程序的详细信息，请参阅 [64 位编程](http://msdn.microsoft.com/library/h2k70f3s\(v=vs.80\))。</span><span class="sxs-lookup"><span data-stu-id="430ea-143">For more information about how to use Visual C++ to create native applications that run on a 64-bit Windows operating system, see [64-bit Programming](http://msdn.microsoft.com/library/h2k70f3s\(v=vs.80\)).</span></span>|  
  
## <a name="determining-the-status-of-an-exe-file-or-dll-file"></a><span data-ttu-id="430ea-144">确定 .exe 文件或 .dll 文件的状态</span><span class="sxs-lookup"><span data-stu-id="430ea-144">Determining the Status of an .exe File or .dll File</span></span>  
 <span data-ttu-id="430ea-145">若要确定 .exe 文件或 .dll 文件是只能在特定平台上运行还是可在 WOW64 下运行，请使用不带任何选项的 [CorFlags.exe（CorFlags 转换工具）](../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="430ea-145">To determine whether an .exe file or .dll file is meant to run only on a specific platform or under WOW64, use [CorFlags.exe (CorFlags Conversion Tool)](../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md) with no options.</span></span> <span data-ttu-id="430ea-146">您也可以使用 CorFlags.exe 更改 .exe 文件或 .dll 文件的平台状态。</span><span class="sxs-lookup"><span data-stu-id="430ea-146">You can also use CorFlags.exe to change the platform status of an .exe file or .dll file.</span></span> <span data-ttu-id="430ea-147">Visual Studio 程序集的 CLR 头的主运行时版本号设置为 2，次运行时版本号设置为 5。</span><span class="sxs-lookup"><span data-stu-id="430ea-147">The CLR header of a Visual Studio assembly has the major runtime version number set to 2 and the minor runtime version number set to 5.</span></span> <span data-ttu-id="430ea-148">将次运行时版本设置为 0 的应用程序会被视为旧版应用程序，且始终在 WOW64 下执行。</span><span class="sxs-lookup"><span data-stu-id="430ea-148">Applications that have the minor runtime version set to 0 are treated as legacy applications and are always executed under WOW64.</span></span>  
  
 <span data-ttu-id="430ea-149">若要以编程方式查询 .exe 或 .dll，以查看其是只能在特定平台上运行还是在 WOW64 下运行，请使用 <xref:System.Reflection.Module.GetPEKind%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="430ea-149">To programmatically query an .exe or .dll to see whether it is meant to run only on a specific platform or under WOW64, use the <xref:System.Reflection.Module.GetPEKind%2A?displayProperty=nameWithType> method.</span></span>
