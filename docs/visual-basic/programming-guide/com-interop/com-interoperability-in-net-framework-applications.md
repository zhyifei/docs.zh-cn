---
title: ".NET Framework 应用程序中的 COM 互操作性 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c84143e22f33f572447c50e33559a52469b181a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="a00a6-102">.NET Framework 应用程序中的 COM 互操作性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a00a6-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="a00a6-103">如果你想要在同一个应用程序中使用 COM 对象和.NET Framework 对象，你需要处理中的对象在内存中的存在的差异。</span><span class="sxs-lookup"><span data-stu-id="a00a6-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="a00a6-104">.NET Framework 对象位于托管内存-由公共语言运行时控制的内存 — 和根据需要可由运行时移动。</span><span class="sxs-lookup"><span data-stu-id="a00a6-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="a00a6-105">COM 对象位于非托管内存中，不应将移至另一个内存位置。</span><span class="sxs-lookup"><span data-stu-id="a00a6-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="a00a6-106">与[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]提供工具以控制这些交互托管和非托管组件。</span><span class="sxs-lookup"><span data-stu-id="a00a6-106"> and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="a00a6-107">有关托管代码的详细信息，请参阅[公共语言运行时](../../../standard/clr.md)。</span><span class="sxs-lookup"><span data-stu-id="a00a6-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="a00a6-108">除了使用.NET 应用程序中的 COM 对象，可能还想要使用[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]开发可从 com。 通过非托管代码访问的对象</span><span class="sxs-lookup"><span data-stu-id="a00a6-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="a00a6-109">此页上的链接提供有关 COM 和.NET Framework 对象之间的交互的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a00a6-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a00a6-110">相关章节</span><span class="sxs-lookup"><span data-stu-id="a00a6-110">Related Sections</span></span>  
 [<span data-ttu-id="a00a6-111">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="a00a6-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="a00a6-112">提供到包含在 Visual Basic 中，包括 COM 对象、 ActiveX 控件，Win32 Dll，托管的对象和 COM 对象的继承的 COM 互操作性的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="a00a6-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="a00a6-113">COM 互操作包装错误</span><span class="sxs-lookup"><span data-stu-id="a00a6-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="a00a6-114">如果项目系统无法创建特定组件的 COM 互操作性包装，描述的结果和选项。</span><span class="sxs-lookup"><span data-stu-id="a00a6-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="a00a6-115">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="a00a6-115">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="a00a6-116">简要介绍了一些托管和非托管代码之间的交互问题并提供进一步学习的链接。</span><span class="sxs-lookup"><span data-stu-id="a00a6-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="a00a6-117">COM 包装</span><span class="sxs-lookup"><span data-stu-id="a00a6-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="a00a6-118">讨论运行时可调用包装器，它允许托管的代码调用 COM 方法调用，以及 COM 可调用包装器，它允许 COM 客户端调用.NET 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="a00a6-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="a00a6-119">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="a00a6-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="a00a6-120">提供到包含 COM 互操作性方面包装、 异常、 继承、 线程、 事件、 转换和封送处理的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="a00a6-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="a00a6-121">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="a00a6-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="a00a6-122">讨论的工具，可用于将转换到公共语言运行时程序集中的等效定义 COM 类型库中找到的类型定义。</span><span class="sxs-lookup"><span data-stu-id="a00a6-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
