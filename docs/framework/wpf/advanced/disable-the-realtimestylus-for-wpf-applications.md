---
title: '禁用用于 WPF 应用程序的 RealTimeStylus '
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: e44b71ac5af64ab3a6cb008db71e5a8881592e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962485"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="b6ae8-102">禁用用于 WPF 应用程序的 RealTimeStylus </span><span class="sxs-lookup"><span data-stu-id="b6ae8-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="b6ae8-103">Windows Presentation Foundation (WPF) 提供了内置支持来处理 Windows 7 触控输入。这种支持是通过为 tablet 平台的实时触笔输入<xref:System.Windows.UIElement.OnStylusDown%2A>， <xref:System.Windows.UIElement.OnStylusUp%2A>，和<xref:System.Windows.UIElement.OnStylusMove%2A>事件。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="b6ae8-104">Windows 7 还提供了作为 Win32 WM_TOUCH 窗口消息的多点触控输入。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="b6ae8-105">这两个 Api 上的同一个 HWND 互相排斥。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="b6ae8-106">启用触控输入通过 tablet 平台 （WPF 应用程序的默认值） 禁用 WM_TOUCH 消息。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="b6ae8-107">因此，若要使用 WM_TOUCH 从 WPF 窗口接收触控消息，则必须禁用在 WPF 中的内置触笔支持。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="b6ae8-108">此选项适用于使用 WM_TOUCH 组件宿主的 WPF 窗口类似的情况。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="b6ae8-109">若要禁用 WPF 笔针输入到侦听，删除了由 WPF 窗口添加任何平板电脑支持。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6ae8-110">示例</span><span class="sxs-lookup"><span data-stu-id="b6ae8-110">Example</span></span>  
 <span data-ttu-id="b6ae8-111">下面的示例代码演示如何使用反射删除默认 tablet 平台支持。</span><span class="sxs-lookup"><span data-stu-id="b6ae8-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6ae8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6ae8-112">See also</span></span>

- [<span data-ttu-id="b6ae8-113">截获触笔输入</span><span class="sxs-lookup"><span data-stu-id="b6ae8-113">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
