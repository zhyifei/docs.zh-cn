---
title: '禁用用于 WPF 应用程序的 RealTimeStylus '
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: ddf4a7f4488f957b2f413d61ad02aa59beba30f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>禁用用于 WPF 应用程序的 RealTimeStylus 
Windows Presentation Foundation (WPF) 提供了内置支持用于处理 Windows 7 触摸屏输入。这种支持是通过平板电脑平台的实时触笔输入<xref:System.Windows.UIElement.OnStylusDown%2A>， <xref:System.Windows.UIElement.OnStylusUp%2A>，和<xref:System.Windows.UIElement.OnStylusMove%2A>事件。 Windows 7 还作为 Win32 WM_TOUCH 窗口消息提供多点触控输入。 这些两个 Api 上相同的 HWND 互斥。 启用触控输入平板电脑平台 （WPF 应用程序的默认值） 通过禁用 WM_TOUCH 消息。 因此，若要使用 WM_TOUCH 接收从 WPF 窗口的触摸屏输入消息，则必须禁用 WPF 中的内置触笔支持。 这是适用于如 WPF 窗口承载使用 WM_TOUCH 的组件的方案。  
  
 若要禁用 WPF 侦听到触笔输入，删除作为 WPF 窗口中添加任何平板电脑支持。  
  
## <a name="example"></a>示例  
 下面的示例代码演示如何使用反射删除默认平板电脑平台支持。  
  
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
  
## <a name="see-also"></a>请参阅  
 [截获触笔输入](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
