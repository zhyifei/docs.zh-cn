---
title: '禁用用于 WPF 应用程序的 RealTimeStylus '
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: ddf4a7f4488f957b2f413d61ad02aa59beba30f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545657"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="b9b8e-102">禁用用于 WPF 应用程序的 RealTimeStylus </span><span class="sxs-lookup"><span data-stu-id="b9b8e-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="b9b8e-103">Windows Presentation Foundation (WPF) 提供了内置支持用于处理 Windows 7 触摸屏输入。这种支持是通过平板电脑平台的实时触笔输入<xref:System.Windows.UIElement.OnStylusDown%2A>， <xref:System.Windows.UIElement.OnStylusUp%2A>，和<xref:System.Windows.UIElement.OnStylusMove%2A>事件。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="b9b8e-104">Windows 7 还作为 Win32 WM_TOUCH 窗口消息提供多点触控输入。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="b9b8e-105">这些两个 Api 上相同的 HWND 互斥。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="b9b8e-106">启用触控输入平板电脑平台 （WPF 应用程序的默认值） 通过禁用 WM_TOUCH 消息。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="b9b8e-107">因此，若要使用 WM_TOUCH 接收从 WPF 窗口的触摸屏输入消息，则必须禁用 WPF 中的内置触笔支持。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="b9b8e-108">这是适用于如 WPF 窗口承载使用 WM_TOUCH 的组件的方案。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="b9b8e-109">若要禁用 WPF 侦听到触笔输入，删除作为 WPF 窗口中添加任何平板电脑支持。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9b8e-110">示例</span><span class="sxs-lookup"><span data-stu-id="b9b8e-110">Example</span></span>  
 <span data-ttu-id="b9b8e-111">下面的示例代码演示如何使用反射删除默认平板电脑平台支持。</span><span class="sxs-lookup"><span data-stu-id="b9b8e-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="b9b8e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9b8e-112">See Also</span></span>  
 [<span data-ttu-id="b9b8e-113">截获触笔输入</span><span class="sxs-lookup"><span data-stu-id="b9b8e-113">Intercepting Input from the Stylus</span></span>](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
