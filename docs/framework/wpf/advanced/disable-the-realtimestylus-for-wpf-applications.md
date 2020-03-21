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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>禁用用于 WPF 应用程序的 RealTimeStylus 

Windows 演示基础 （WPF） 已内置了用于处理 Windows 7 触摸输入的支持。 支持来自平板电脑平台的实时手写笔输入，如<xref:System.Windows.UIElement.OnStylusDown%2A>、<xref:System.Windows.UIElement.OnStylusUp%2A>和<xref:System.Windows.UIElement.OnStylusMove%2A>事件。 Windows 7 还提供多点触控输入，作为 Win32 WM_TOUCH窗口消息。 这两个 API 在同一 HWND 上是互斥的。 通过平板电脑平台启用触摸输入（WPF 应用程序的默认值）可禁用WM_TOUCH消息。 因此，要使用WM_TOUCH接收来自 WPF 窗口的触摸消息，必须禁用 WPF 中的内置手写笔支持。 这适用于使用WM_TOUCH的组件的 WPF 窗口等方案。  
  
 要禁用 WPF 侦听手写笔输入，请删除 WPF 窗口添加的任何平板电脑支持。  
  
## <a name="example"></a>示例  
 以下示例代码演示如何使用反射删除默认的平板电脑平台支持。  
  
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

- [截获触笔输入](intercepting-input-from-the-stylus.md)
