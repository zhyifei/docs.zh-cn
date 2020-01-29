---
title: 禁用 RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 74145c32af7e9ebbc774a0301e205aa1eb1539b3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737935"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>WPF 애플리케이션에 대해 RealTimeStylus를 사용하지 않도록 설정

Windows Presentation Foundation （WPF）内置支持处理 Windows 7 触控输入。 此支持通过 tablet 平台的实时触笔输入来完成 <xref:System.Windows.UIElement.OnStylusDown%2A>、<xref:System.Windows.UIElement.OnStylusUp%2A>和 <xref:System.Windows.UIElement.OnStylusMove%2A> 事件。 Windows 7 还提供多点触控输入作为 Win32 WM_TOUCH 窗口消息。 这两个 Api 在同一 HWND 上相互排斥。 通过 tablet 平台（WPF 应用程序的默认设置）启用触控输入会禁用 WM_TOUCH 消息。 因此，若要使用 WM_TOUCH 从 WPF 窗口接收触摸消息，您必须禁用 WPF 中的内置触笔支持。 这适用于一个方案，例如 WPF 窗口，该窗口承载使用 WM_TOUCH 的组件。  
  
 若要禁用 WPF 侦听触笔输入，请移除由 WPF 窗口添加的任何 tablet 支持。  
  
## <a name="example"></a>示例  
 下面的示例代码演示如何通过使用反射删除默认 tablet 平台支持。  
  
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
  
## <a name="see-also"></a>另请参阅

- [스타일러스에서 입력 가로채기](intercepting-input-from-the-stylus.md)
