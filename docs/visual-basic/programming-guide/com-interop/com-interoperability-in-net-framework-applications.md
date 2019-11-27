---
title: .NET Framework 应用程序中的 COM 互操作性
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 1c484ae948c247a97dd57539e3b0be263736aceb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348749"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="95aa5-102">.NET Framework 应用程序中的 COM 互操作性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95aa5-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>

<span data-ttu-id="95aa5-103">如果要在同一个应用程序中使用 COM 对象和 .NET Framework 对象，则需要解决对象在内存中的存在情况之间的差异。</span><span class="sxs-lookup"><span data-stu-id="95aa5-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="95aa5-104">.NET Framework 对象位于托管内存（由公共语言运行时控制的内存）中，可以根据需要在运行时中移动。</span><span class="sxs-lookup"><span data-stu-id="95aa5-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="95aa5-105">COM 对象位于非托管内存中，不应移动到另一个内存位置。</span><span class="sxs-lookup"><span data-stu-id="95aa5-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="95aa5-106">Visual Studio 和 .NET Framework 提供用于控制这些托管和非托管组件的交互的工具。</span><span class="sxs-lookup"><span data-stu-id="95aa5-106">Visual Studio and the .NET Framework provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="95aa5-107">有关托管代码的详细信息，请参阅[公共语言运行时](../../../standard/clr.md)。</span><span class="sxs-lookup"><span data-stu-id="95aa5-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>

<span data-ttu-id="95aa5-108">除了在 .NET 应用程序中使用 COM 对象之外，还可以使用 Visual Basic 开发通过 COM 从非托管代码访问的对象。</span><span class="sxs-lookup"><span data-stu-id="95aa5-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>

<span data-ttu-id="95aa5-109">此页上的链接提供有关 COM 和 .NET Framework 对象之间的交互的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95aa5-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="95aa5-110">相关章节</span><span class="sxs-lookup"><span data-stu-id="95aa5-110">Related sections</span></span>

| | |
|---------|---------|
| [<span data-ttu-id="95aa5-111">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="95aa5-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md) | <span data-ttu-id="95aa5-112">提供与 Visual Basic 中的 COM 互操作性相关的主题的链接，这些主题包括 COM 对象、ActiveX 控件、Win32 Dll、托管对象以及 COM 对象的继承。</span><span class="sxs-lookup"><span data-stu-id="95aa5-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span> |
| [<span data-ttu-id="95aa5-113">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="95aa5-113">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="95aa5-114">简要介绍了托管和非托管代码之间的一些交互问题，并提供了进一步研究的链接。</span><span class="sxs-lookup"><span data-stu-id="95aa5-114">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span> |
| [<span data-ttu-id="95aa5-115">COM 包装</span><span class="sxs-lookup"><span data-stu-id="95aa5-115">COM Wrappers</span></span>](../../../standard/native-interop/com-wrappers.md) | <span data-ttu-id="95aa5-116">讨论允许托管代码调用 COM 方法的运行时可调用包装器，以及允许 COM 客户端调用 .NET 对象方法的 COM 可调用包装器。</span><span class="sxs-lookup"><span data-stu-id="95aa5-116">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span> |
| [<span data-ttu-id="95aa5-117">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="95aa5-117">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="95aa5-118">提供一些链接，这些链接指向涵盖与包装、异常、继承、线程处理、事件、转换和封送处理相关的 COM 互操作性。</span><span class="sxs-lookup"><span data-stu-id="95aa5-118">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span> |
| [<span data-ttu-id="95aa5-119">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="95aa5-119">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md) | <span data-ttu-id="95aa5-120">讨论可用于将 COM 类型库中找到的类型定义转换为公共语言运行时程序集中的等效定义的工具。</span><span class="sxs-lookup"><span data-stu-id="95aa5-120">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span> |
