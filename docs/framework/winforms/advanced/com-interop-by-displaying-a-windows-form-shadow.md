---
title: 如何：通过使用 ShowDialog 方法显示 Windows 窗体来支持 COM 互操作
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: 81220ad4c0bf00a38abfe7257d5fc61e92e8d885
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206442"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="2bae4-102">如何：通过使用 ShowDialog 方法显示 Windows 窗体来支持 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="2bae4-102">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>
<span data-ttu-id="2bae4-103">可通过在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 消息循环上显示 Windows 窗体来解决组件对象模型 (COM) 互操作性问题，可使用 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 方法来创建该消息循环。</span><span class="sxs-lookup"><span data-stu-id="2bae4-103">You can resolve Component Object Model (COM) interoperability problems by displaying your Windows Form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop, which is created by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="2bae4-104">若要使窗体在 COM 客户端应用程序中正确工作，必须在 Windows 窗体消息循环上运行该窗体。</span><span class="sxs-lookup"><span data-stu-id="2bae4-104">To make a form work correctly from a COM client application, you must run it on a Windows Forms message loop.</span></span> <span data-ttu-id="2bae4-105">若要执行此操作，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="2bae4-105">To do this, use one of the following approaches:</span></span>  
  
-   <span data-ttu-id="2bae4-106">使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法显示 Windows 窗体；</span><span class="sxs-lookup"><span data-stu-id="2bae4-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form;</span></span>  
  
-   <span data-ttu-id="2bae4-107">在单独的线程上显示每个 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="2bae4-107">Display each Windows Form on a separate thread.</span></span> <span data-ttu-id="2bae4-108">有关详细信息，请参阅[如何：通过在其自己的线程上显示每个 Windows 窗体来支持 COM 互操作](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)。</span><span class="sxs-lookup"><span data-stu-id="2bae4-108">For more information, see [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="2bae4-109">过程</span><span class="sxs-lookup"><span data-stu-id="2bae4-109">Procedure</span></span>  
 <span data-ttu-id="2bae4-110">使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法可能是在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 消息循环上显示窗体的最简单方法，因为在所有方法中，它只需最少的代码即可实现。</span><span class="sxs-lookup"><span data-stu-id="2bae4-110">Using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method can be the easiest way to display a form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop because, of all the approaches, it requires the least code to implement.</span></span>  
  
 <span data-ttu-id="2bae4-111"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法挂起非托管应用程序的消息循环，并将窗体显示为对话框。</span><span class="sxs-lookup"><span data-stu-id="2bae4-111">The <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method suspends the unmanaged application's message loop and displays the form as a dialog box.</span></span> <span data-ttu-id="2bae4-112">由于宿主应用程序的消息循环已挂起， <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法创建新的 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 消息循环来处理该窗体的消息。</span><span class="sxs-lookup"><span data-stu-id="2bae4-112">Because the host application's message loop has been suspended, the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method creates a new [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop to process the form's messages.</span></span>  
  
 <span data-ttu-id="2bae4-113">使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法的缺点是窗体将作为模式对话框打开。</span><span class="sxs-lookup"><span data-stu-id="2bae4-113">The disadvantage of using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method is that the form will be opened as a modal dialog box.</span></span> <span data-ttu-id="2bae4-114">Windows 窗体打开时，此行为将阻止调用应用程序中的任何用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="2bae4-114">This behavior blocks any user interface (UI) in the calling application while the Windows Form is open.</span></span> <span data-ttu-id="2bae4-115">当用户退出该窗体时， [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 消息循环关闭，先前应用程序的消息循环重新运行。</span><span class="sxs-lookup"><span data-stu-id="2bae4-115">When the user exits the form, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop closes and the earlier application's message loop starts running again.</span></span>  
  
 <span data-ttu-id="2bae4-116">可以在 Windows 窗体中创建具有显示窗体方法的类库，然后为 COM 互操作生成类库。</span><span class="sxs-lookup"><span data-stu-id="2bae4-116">You can create a class library in Windows Forms which has a method to show the form, and then build the class library for COM interop.</span></span> <span data-ttu-id="2bae4-117">可以从 Visual Basic 6.0 或 Microsoft 基础类 (MFC) 中使用此 DLL 文件，在这两种环境中，都可以调用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法来显示窗体。</span><span class="sxs-lookup"><span data-stu-id="2bae4-117">You can use this DLL file from Visual Basic 6.0 or Microsoft Foundation Classes (MFC), and from either of these environments you can call the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the form.</span></span>  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="2bae4-118">通过使用 ShowDialog 方法显示 Windows 窗体来支持 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="2bae4-118">To support COM interop by displaying a windows form with the ShowDialog method</span></span>  
  
-   <span data-ttu-id="2bae4-119">在 <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> 组件中，将所有对 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法的调用替换为对 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="2bae4-119">Replace all calls to the <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> method with calls to the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method in your [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bae4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bae4-120">See also</span></span>

- [<span data-ttu-id="2bae4-121">向 COM 公开 .NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="2bae4-121">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="2bae4-122">如何：通过在其自己的线程上显示每个 Windows 窗体来支持 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="2bae4-122">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [<span data-ttu-id="2bae4-123">Windows Forms and Unmanaged Applications</span><span class="sxs-lookup"><span data-stu-id="2bae4-123">Windows Forms and Unmanaged Applications</span></span>](windows-forms-and-unmanaged-applications.md)
