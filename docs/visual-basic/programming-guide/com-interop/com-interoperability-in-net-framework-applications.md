---
title: .NET Framework 应用程序中的 COM 互操作性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 76c953941d2b8e7af5e4894fd1c521d62e64860f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642116"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="9fc11-102">.NET Framework 应用程序中的 COM 互操作性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fc11-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>

<span data-ttu-id="9fc11-103">当你想要在同一个应用程序中使用 COM 对象和.NET Framework 对象时，您需要解决对象存在于内存中的差异。</span><span class="sxs-lookup"><span data-stu-id="9fc11-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="9fc11-104">.NET Framework 对象位于托管内存中 — 由公共语言运行时控制的内存，并根据需要运行时可能会移动。</span><span class="sxs-lookup"><span data-stu-id="9fc11-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="9fc11-105">COM 对象位于非托管内存中，不应将移动到另一个内存位置。</span><span class="sxs-lookup"><span data-stu-id="9fc11-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="9fc11-106">Visual Studio 和.NET Framework 提供工具来控制这些托管和非托管组件的交互。</span><span class="sxs-lookup"><span data-stu-id="9fc11-106">Visual Studio and the .NET Framework provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="9fc11-107">有关托管代码的详细信息，请参阅[公共语言运行时](../../../standard/clr.md)。</span><span class="sxs-lookup"><span data-stu-id="9fc11-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>

<span data-ttu-id="9fc11-108">除了.NET 应用程序中使用 COM 对象，您可能还想要使用 Visual Basic 开发从 com。 通过非托管代码可访问的对象</span><span class="sxs-lookup"><span data-stu-id="9fc11-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>

<span data-ttu-id="9fc11-109">此页面上的链接提供有关 COM 和.NET Framework 对象之间的交互的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9fc11-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="9fc11-110">相关章节</span><span class="sxs-lookup"><span data-stu-id="9fc11-110">Related sections</span></span>

| | |
|---------|---------|
| [<span data-ttu-id="9fc11-111">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="9fc11-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md) | <span data-ttu-id="9fc11-112">提供指向介绍在 Visual Basic 中，包括 COM 对象、 ActiveX 控件、 Win32 Dll，托管的对象和继承的 COM 对象的 COM 互操作性的主题。</span><span class="sxs-lookup"><span data-stu-id="9fc11-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span> |
| [<span data-ttu-id="9fc11-113">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="9fc11-113">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="9fc11-114">简要介绍了一些托管和非托管代码之间的交互问题并提供进一步研究的链接。</span><span class="sxs-lookup"><span data-stu-id="9fc11-114">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span> |
| [<span data-ttu-id="9fc11-115">COM 包装</span><span class="sxs-lookup"><span data-stu-id="9fc11-115">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md) | <span data-ttu-id="9fc11-116">讨论运行时可调用包装器，它允许托管的代码调用 COM 方法，以及 COM 可调用包装，允许 COM 客户端调用.NET 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="9fc11-116">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span> |
| [<span data-ttu-id="9fc11-117">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="9fc11-117">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="9fc11-118">提供指向介绍 COM 互操作性方面包装、 异常、 继承、 线程、 事件、 转换和封送处理主题。</span><span class="sxs-lookup"><span data-stu-id="9fc11-118">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span> |
| [<span data-ttu-id="9fc11-119">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="9fc11-119">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md) | <span data-ttu-id="9fc11-120">讨论的工具，可用于将转换为公共语言运行时程序集中的等效定义 COM 类型库中找到的类型定义。</span><span class="sxs-lookup"><span data-stu-id="9fc11-120">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span> |
