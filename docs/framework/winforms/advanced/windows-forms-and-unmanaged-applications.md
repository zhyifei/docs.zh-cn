---
title: Windows 窗体和非托管应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 65465f22b1806d385523c894cce2103afe33c2f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746689"
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="541e6-102">Windows 窗体和非托管应用程序</span><span class="sxs-lookup"><span data-stu-id="541e6-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="541e6-103">Windows 窗体应用程序和控件可以与非托管应用程序进行互操作，但有一些需要注意的问题。</span><span class="sxs-lookup"><span data-stu-id="541e6-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="541e6-104">以下各节将介绍 Windows 窗体应用程序和控件支持和不支持的方案和配置。</span><span class="sxs-lookup"><span data-stu-id="541e6-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="541e6-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="541e6-105">In This Section</span></span>  
 [<span data-ttu-id="541e6-106">Windows 窗体和非托管应用程序概述</span><span class="sxs-lookup"><span data-stu-id="541e6-106">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="541e6-107">提供有关如何使用和实现运用非托管应用程序的 Windows 窗体控件的常规信息。</span><span class="sxs-lookup"><span data-stu-id="541e6-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="541e6-108">如何：通过显示 Windows 窗体使用 ShowDialog 方法来支持 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="541e6-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="541e6-109">提供显示如何使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法在非托管应用程序中运行 Windows 窗体的代码示例。</span><span class="sxs-lookup"><span data-stu-id="541e6-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="541e6-110">如何：通过在其自己的线程上显示每个 Windows 窗体来支持 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="541e6-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="541e6-111">提供显示如何在各自的线程上运行 Windows 窗体的代码示例。</span><span class="sxs-lookup"><span data-stu-id="541e6-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="541e6-112">另请参阅[演练：通过在其自己的线程上显示每个 Windows 窗体支持 COM 互操作](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="541e6-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="541e6-113">参考</span><span class="sxs-lookup"><span data-stu-id="541e6-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="541e6-114">用于为 Windows 窗体中创建单独线程。</span><span class="sxs-lookup"><span data-stu-id="541e6-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="541e6-115">启动线程的消息循环。</span><span class="sxs-lookup"><span data-stu-id="541e6-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="541e6-116">将来自非托管应用程序的调用封送到窗体。</span><span class="sxs-lookup"><span data-stu-id="541e6-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="541e6-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="541e6-117">Related Sections</span></span>  
 [<span data-ttu-id="541e6-118">向 COM 公开 .NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="541e6-118">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="541e6-119">提供有关如何在非托管应用程序中使用 .NET Framework 类型的常规信息。</span><span class="sxs-lookup"><span data-stu-id="541e6-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
