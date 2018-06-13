---
title: Windows 窗体应用程序中的用户输入
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 4f1b96ab53b30d045a315b43abd0e38157e26c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538358"
---
# <a name="user-input-in-a-windows-forms-application"></a>Windows 窗体应用程序中的用户输入
在 Windows 窗体，用户输入发送到 Windows 消息的窗体中的应用程序。 可重写方法的一系列处理在应用程序窗体中，这些消息，并控制级别。 当这些方法接收鼠标和键盘消息时，因此将引发可以处理以获取信息鼠标或键盘输入的事件。 在许多情况下，Windows 窗体应用程序将能够只需通过处理这些事件处理所有用户输入。 在其他情况下，应用程序可能需要重写处理消息以便由应用程序、 窗体中或控件接收到之前截获某个特定消息的方法之一。  
  
## <a name="mouse-and-keyboard-events"></a>鼠标和键盘事件  
 所有 Windows 窗体控件都继承一的组与鼠标和键盘输入相关的事件。 例如，可以处理控件<xref:System.Windows.Forms.Control.KeyPress>事件可以确定曾按下的键的字符代码或控件可以处理<xref:System.Windows.Forms.Control.MouseClick>事件，以确定的鼠标位置单击。 有关鼠标和键盘事件的详细信息，请参阅[使用键盘事件](../../../docs/framework/winforms/using-keyboard-events.md)和[Windows 窗体中的鼠标事件](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)。  
  
## <a name="methods-that-process-user-input-messages"></a>处理用户输入的消息的方法  
 窗体和控件有权访问<xref:System.Windows.Forms.IMessageFilter>界面和一组处理 Windows 消息的消息队列中的不同点的可重写方法。 这些方法都有<xref:System.Windows.Forms.Message>参数，它封装 Windows 消息的低级别的详细信息。 可以实现，也可以重写这些方法，以检查的消息，然后使用消息或将其传递到消息队列中的下一步使用者。 下表列出了处理 Windows 窗体中的所有 Windows 消息的方法。  
  
|方法|说明|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|此方法会截获排队应用程序级别 （也称为已发布） 的 Windows 消息。|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|已处理之前，此方法会截获窗体和控件级别的 Windows 消息。|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|此方法处理 Windows 消息级别的窗体和控件。|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|此方法执行级别的窗体和控件的 Windows 消息的默认处理。 这提供一个窗口的最小功能。|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|处理完后，此方法将截获消息级别的窗体和控件。 <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage>样式位，必须为要调用此方法设置。|  
  
 通过额外的一组特定于这些类型的消息的可重写方法还处理键盘和鼠标的消息。 有关详细信息，请参阅[键盘输入工作原理](../../../docs/framework/winforms/how-keyboard-input-works.md)和[鼠标输入工作原理 Windows 窗体中](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md)。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体中的用户输入](../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 [Windows 窗体应用程序中的键盘输入](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Windows 窗体应用程序中的鼠标输入](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
