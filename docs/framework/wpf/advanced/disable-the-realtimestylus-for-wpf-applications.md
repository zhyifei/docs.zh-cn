---
title: 禁用实时样式
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186082"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="a3e67-102">禁用用于 WPF 应用程序的 RealTimeStylus </span><span class="sxs-lookup"><span data-stu-id="a3e67-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="a3e67-103">Windows 演示基础 （WPF） 已内置了用于处理 Windows 7 触摸输入的支持。</span><span class="sxs-lookup"><span data-stu-id="a3e67-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="a3e67-104">支持来自平板电脑平台的实时手写笔输入，如<xref:System.Windows.UIElement.OnStylusDown%2A>、<xref:System.Windows.UIElement.OnStylusUp%2A>和<xref:System.Windows.UIElement.OnStylusMove%2A>事件。</span><span class="sxs-lookup"><span data-stu-id="a3e67-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="a3e67-105">Windows 7 还提供多点触控输入，作为 Win32 WM_TOUCH窗口消息。</span><span class="sxs-lookup"><span data-stu-id="a3e67-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="a3e67-106">这两个 API 在同一 HWND 上是互斥的。</span><span class="sxs-lookup"><span data-stu-id="a3e67-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="a3e67-107">通过平板电脑平台启用触摸输入（WPF 应用程序的默认值）可禁用WM_TOUCH消息。</span><span class="sxs-lookup"><span data-stu-id="a3e67-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="a3e67-108">因此，要使用WM_TOUCH接收来自 WPF 窗口的触摸消息，必须禁用 WPF 中的内置手写笔支持。</span><span class="sxs-lookup"><span data-stu-id="a3e67-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="a3e67-109">这适用于使用WM_TOUCH的组件的 WPF 窗口等方案。</span><span class="sxs-lookup"><span data-stu-id="a3e67-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="a3e67-110">要禁用 WPF 侦听手写笔输入，请删除 WPF 窗口添加的任何平板电脑支持。</span><span class="sxs-lookup"><span data-stu-id="a3e67-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3e67-111">示例</span><span class="sxs-lookup"><span data-stu-id="a3e67-111">Example</span></span>  
 <span data-ttu-id="a3e67-112">以下示例代码演示如何使用反射删除默认的平板电脑平台支持。</span><span class="sxs-lookup"><span data-stu-id="a3e67-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```csharp  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3e67-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3e67-113">See also</span></span>

- [<span data-ttu-id="a3e67-114">截获触笔输入</span><span class="sxs-lookup"><span data-stu-id="a3e67-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
