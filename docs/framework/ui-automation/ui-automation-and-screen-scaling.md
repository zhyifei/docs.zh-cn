---
title: UI 自动化和屏幕缩放
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scaling, screens
- screens, scaling
- UI (user interface), automation
- UI Automation
ms.assetid: 4380cad7-e509-448f-b9a5-6de042605fd4
ms.openlocfilehash: 2a68a74fa6aadcaba21f142d394a1f8a3d8af371
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179970"
---
# <a name="ui-automation-and-screen-scaling"></a><span data-ttu-id="bd90e-102">UI 自动化和屏幕缩放</span><span class="sxs-lookup"><span data-stu-id="bd90e-102">UI Automation and Screen Scaling</span></span>
> [!NOTE]
> <span data-ttu-id="bd90e-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="bd90e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bd90e-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="bd90e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
<span data-ttu-id="bd90e-105">从 Windows Vista 开始，Windows 使用户能够更改每英寸点 （dpi） 设置，以便屏幕上的大多数用户界面 （UI） 元素看起来更大。</span><span class="sxs-lookup"><span data-stu-id="bd90e-105">Starting with Windows Vista, Windows enables users to change the dots per inch (dpi) setting so that most user interface (UI) elements on the screen appear larger.</span></span> <span data-ttu-id="bd90e-106">尽管此功能在 Windows 中早已可用，但在以前的版本中，缩放必须由应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="bd90e-106">Although this feature has long been available in Windows, in previous versions the scaling had to be implemented by applications.</span></span> <span data-ttu-id="bd90e-107">桌面窗口管理器从 Windows Vista 开始，对所有不处理其自身缩放的应用程序执行默认缩放。</span><span class="sxs-lookup"><span data-stu-id="bd90e-107">Starting with Windows Vista, the Desktop Window Manager performs default scaling for all applications that do not handle their own scaling.</span></span> <span data-ttu-id="bd90e-108">UI 自动化客户端应用程序必须考虑到此功能。</span><span class="sxs-lookup"><span data-stu-id="bd90e-108">UI Automation client applications must take this feature into account.</span></span>  
  
<a name="Scaling_in_Windows_Vista"></a>
## <a name="scaling-in-windows-vista"></a><span data-ttu-id="bd90e-109">Windows Vista 中的缩放</span><span class="sxs-lookup"><span data-stu-id="bd90e-109">Scaling in Windows Vista</span></span>  
 <span data-ttu-id="bd90e-110">默认 dpi 设置为 96，这意味着 96 像素占用一个名义英寸的宽度或高度。</span><span class="sxs-lookup"><span data-stu-id="bd90e-110">The default dpi setting is 96, which means that 96 pixels occupy a width or height of one notional inch.</span></span> <span data-ttu-id="bd90e-111">“一英寸”的确切度量取决于监视器的大小和物理分辨率。</span><span class="sxs-lookup"><span data-stu-id="bd90e-111">The exact measure of an "inch" depends on the size and physical resolution of the monitor.</span></span> <span data-ttu-id="bd90e-112">例如，在 12 英寸宽、水平分辨率为 1280 像素的监视器上，96 像素的水平线将扩展大约 9/10 英寸。</span><span class="sxs-lookup"><span data-stu-id="bd90e-112">For example, on a monitor 12 inches wide, at a horizontal resolution of 1280 pixels, a horizontal line of 96 pixels extends about 9/10 of an inch.</span></span>  
  
 <span data-ttu-id="bd90e-113">更改 dpi 设置与更改屏幕分辨率不同。</span><span class="sxs-lookup"><span data-stu-id="bd90e-113">Changing the dpi setting is not the same as changing the screen resolution.</span></span> <span data-ttu-id="bd90e-114">使用 dpi 缩放时，屏幕上的物理像素数保持不变。</span><span class="sxs-lookup"><span data-stu-id="bd90e-114">With dpi scaling, the number of physical pixels on the screen remains the same.</span></span> <span data-ttu-id="bd90e-115">但是，缩放将应用于 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 元素的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="bd90e-115">However, scaling is applied to the size and location of [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="bd90e-116">桌面窗口管理器 (DWM) 可以自动对桌面和未显式要求缩放的应用程序执行这种扩展。</span><span class="sxs-lookup"><span data-stu-id="bd90e-116">This scaling can be performed automatically by the Desktop Window Manager (DWM) for the desktop and for applications that do not explicitly ask not to be scaled.</span></span>  
  
 <span data-ttu-id="bd90e-117">实际上，当用户将比例因子设置为 120 dpi 时，屏幕上的垂直或水平英寸会变大 25%。</span><span class="sxs-lookup"><span data-stu-id="bd90e-117">In effect, when the user sets the scale factor to 120 dpi, a vertical or horizontal inch on the screen becomes bigger by 25 percent.</span></span> <span data-ttu-id="bd90e-118">所有尺寸会相应缩放。</span><span class="sxs-lookup"><span data-stu-id="bd90e-118">All dimensions are scaled accordingly.</span></span> <span data-ttu-id="bd90e-119">应用程序窗口距屏幕顶端和左边缘的偏移量将增大 25%。</span><span class="sxs-lookup"><span data-stu-id="bd90e-119">The offset of an application window from the top and left edges of the screen increases by 25 percent.</span></span> <span data-ttu-id="bd90e-120">如果启用了应用程序缩放，并且应用程序不具有 dpi 感知功能，则窗口的大小将随其比例的增加，以及它包含的所有[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]元素的偏移量和大小。</span><span class="sxs-lookup"><span data-stu-id="bd90e-120">If application scaling is enabled and the application is not dpi-aware, the size of the window increases in the same proportion, along with the offsets and sizes of all [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements it contains.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd90e-121">默认情况下，当用户将 dpi 设置为 120 时，DWM 不会对非 dpi 感知应用程序执行缩放，但在 dpi 设置为 144 或更高的自定义值时确实执行缩放。</span><span class="sxs-lookup"><span data-stu-id="bd90e-121">By default, the DWM does not perform scaling for non-dpi-aware applications when the user sets the dpi to 120, but does perform it when the dpi is set to a custom value of 144 or higher.</span></span> <span data-ttu-id="bd90e-122">但是，用户可以重写默认行为。</span><span class="sxs-lookup"><span data-stu-id="bd90e-122">However, the user can override the default behavior.</span></span>  
  
 <span data-ttu-id="bd90e-123">屏幕缩放为以任何方式与屏幕坐标有关的应用程序带来了新的挑战。</span><span class="sxs-lookup"><span data-stu-id="bd90e-123">Screen scaling creates new challenges for applications that are concerned in any way with screen coordinates.</span></span> <span data-ttu-id="bd90e-124">屏幕现在包含两个坐标系：物理和逻辑。</span><span class="sxs-lookup"><span data-stu-id="bd90e-124">The screen now contains two coordinate systems: physical and logical.</span></span> <span data-ttu-id="bd90e-125">点的物理坐标是距原点左上部的实际偏移量（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="bd90e-125">The physical coordinates of a point are the actual offset in pixels from the top left of the origin.</span></span> <span data-ttu-id="bd90e-126">如果像素本身进行了缩放，则逻辑坐标为缩放后的偏移量。</span><span class="sxs-lookup"><span data-stu-id="bd90e-126">The logical coordinates are the offsets as they would be if the pixels themselves were scaled.</span></span>  
  
 <span data-ttu-id="bd90e-127">假定你设计了一个对话框，其按钮位于坐标 (100, 48) 处。</span><span class="sxs-lookup"><span data-stu-id="bd90e-127">Suppose you design a dialog box with a button at coordinates (100, 48).</span></span> <span data-ttu-id="bd90e-128">当此对话框显示在默认的 96 dpi 时，该按钮位于物理坐标 （100， 48）。</span><span class="sxs-lookup"><span data-stu-id="bd90e-128">When this dialog box is displayed at the default 96 dpi, the button is located at physical coordinates of (100, 48).</span></span> <span data-ttu-id="bd90e-129">在 120 dpi 处，它位于物理坐标 （125， 60）。</span><span class="sxs-lookup"><span data-stu-id="bd90e-129">At 120 dpi, it is located at physical coordinates of (125, 60).</span></span> <span data-ttu-id="bd90e-130">但是逻辑坐标在任何 dpi 设置中都是相同的：（100，48）。</span><span class="sxs-lookup"><span data-stu-id="bd90e-130">But the logical coordinates are the same at any dpi setting: (100, 48).</span></span>  
  
 <span data-ttu-id="bd90e-131">逻辑坐标很重要，因为它们使操作系统和应用程序的行为一致，而不管 dpi 设置如何。</span><span class="sxs-lookup"><span data-stu-id="bd90e-131">Logical coordinates are important, because they make the behavior of the operating system and applications consistent regardless of the dpi setting.</span></span> <span data-ttu-id="bd90e-132">例如，正常情况下， <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> 将返回逻辑坐标。</span><span class="sxs-lookup"><span data-stu-id="bd90e-132">For example, <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> normally returns the logical coordinates.</span></span> <span data-ttu-id="bd90e-133">如果将光标移到对话框中的元素上，则无论 dpi 设置如何，都会返回相同的坐标。</span><span class="sxs-lookup"><span data-stu-id="bd90e-133">If you move the cursor over an element in a dialog box, the same coordinates are returned regardless of the dpi setting.</span></span> <span data-ttu-id="bd90e-134">如果绘制控件（100，100），则该控件将绘制到这些逻辑坐标，并将在任何 dpi 设置中占据相同的相对位置。</span><span class="sxs-lookup"><span data-stu-id="bd90e-134">If you draw a control at (100, 100), it is drawn to those logical coordinates, and will occupy the same relative position at any dpi setting.</span></span>  
  
<a name="Scaling_in_UI_Automation_Clients"></a>
## <a name="scaling-in-ui-automation-clients"></a><span data-ttu-id="bd90e-135">UI 自动化客户端中的缩放</span><span class="sxs-lookup"><span data-stu-id="bd90e-135">Scaling in UI Automation Clients</span></span>  
 <span data-ttu-id="bd90e-136">API[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不使用逻辑坐标。</span><span class="sxs-lookup"><span data-stu-id="bd90e-136">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API does not use logical coordinates.</span></span> <span data-ttu-id="bd90e-137">下面的方法和属性将返回物理坐标或将其用作参数。</span><span class="sxs-lookup"><span data-stu-id="bd90e-137">The following methods and properties either return physical coordinates or take them as parameters.</span></span>  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 <span data-ttu-id="bd90e-138">默认情况下，在非 96-dpi 环境中运行的 UI 自动化客户端应用程序将无法从这些方法和属性中获得正确的结果。</span><span class="sxs-lookup"><span data-stu-id="bd90e-138">By default, a UI Automation client application running in a non-96- dpi environment will not be able to obtain correct results from these methods and properties.</span></span> <span data-ttu-id="bd90e-139">例如，由于光标的位置是逻辑坐标，客户端不能仅将这些坐标传递到 <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> 以获取光标下的元素。</span><span class="sxs-lookup"><span data-stu-id="bd90e-139">For example, because the cursor position is in logical coordinates, the client cannot simply pass these coordinates to <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> to obtain the element that is under the cursor.</span></span> <span data-ttu-id="bd90e-140">此外，该应用程序不能正确将 Windows 放置在其客户端区域之外。</span><span class="sxs-lookup"><span data-stu-id="bd90e-140">In addition, the application will not be able to correctly place windows outside its client area.</span></span>  
  
 <span data-ttu-id="bd90e-141">解决方法分两个部分。</span><span class="sxs-lookup"><span data-stu-id="bd90e-141">The solution is in two parts.</span></span>  
  
1. <span data-ttu-id="bd90e-142">首先，使客户端应用程序 dpi 感知。</span><span class="sxs-lookup"><span data-stu-id="bd90e-142">First, make the client application dpi-aware.</span></span> <span data-ttu-id="bd90e-143">为此，在启动时调用 Win32`SetProcessDPIAware`函数。</span><span class="sxs-lookup"><span data-stu-id="bd90e-143">To do this, call the Win32 function `SetProcessDPIAware` at startup.</span></span> <span data-ttu-id="bd90e-144">在托管代码中，以下声明使得此函数可用。</span><span class="sxs-lookup"><span data-stu-id="bd90e-144">In managed code, the following declaration makes this function available.</span></span>  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     <span data-ttu-id="bd90e-145">此函数使整个进程具有 dpi 感知功能，这意味着属于该进程的所有窗口都未缩放。</span><span class="sxs-lookup"><span data-stu-id="bd90e-145">This function makes the entire process dpi-aware, meaning that all windows that belong to the process are unscaled.</span></span> <span data-ttu-id="bd90e-146">例如，在[荧光笔示例中](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)，构成高光矩形的四个窗口位于从 UI 自动化获得的物理坐标，而不是逻辑坐标。</span><span class="sxs-lookup"><span data-stu-id="bd90e-146">In the [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), for instance, the four windows that make up the highlight rectangle are located at the physical coordinates obtained from UI Automation, not the logical coordinates.</span></span> <span data-ttu-id="bd90e-147">如果示例不具有 dpi 感知，则高光将在桌面上的逻辑坐标处绘制，这将导致在非 96-dpi 环境中放置不正确。</span><span class="sxs-lookup"><span data-stu-id="bd90e-147">If the sample were not dpi-aware, the highlight would be drawn at the logical coordinates on the desktop, which would result in incorrect placement in a non-96- dpi environment.</span></span>  
  
2. <span data-ttu-id="bd90e-148">要获取光标坐标，请调用 Win32`GetPhysicalCursorPos`函数 。</span><span class="sxs-lookup"><span data-stu-id="bd90e-148">To get cursor coordinates, call the Win32 function `GetPhysicalCursorPos`.</span></span> <span data-ttu-id="bd90e-149">下面的示例演示如何声明和使用此函数。</span><span class="sxs-lookup"><span data-stu-id="bd90e-149">The following example shows how to declare and use this function.</span></span>  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> <span data-ttu-id="bd90e-150">请勿使用 <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="bd90e-150">Do not use <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bd90e-151">未定义此属性在扩展环境下客户端窗口以外的行为。</span><span class="sxs-lookup"><span data-stu-id="bd90e-151">The behavior of this property outside client windows in a scaled environment is undefined.</span></span>  
  
 <span data-ttu-id="bd90e-152">如果应用程序与非 dpi 感知应用程序执行直接跨进程通信，则可能使用 Win32 函数`PhysicalToLogicalPoint`和`LogicalToPhysicalPoint`在逻辑坐标和物理坐标之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="bd90e-152">If your application performs direct cross-process communication with non- dpi-aware applications, you may have convert between logical and physical coordinates by using the Win32 functions `PhysicalToLogicalPoint` and `LogicalToPhysicalPoint`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd90e-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd90e-153">See also</span></span>

- [<span data-ttu-id="bd90e-154">Highlighter Sample</span><span class="sxs-lookup"><span data-stu-id="bd90e-154">Highlighter Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
