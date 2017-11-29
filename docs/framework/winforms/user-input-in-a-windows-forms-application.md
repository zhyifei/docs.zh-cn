---
title: "Windows 窗体应用程序中的用户输入"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb6f832b77404b57ab22e4ac472e7707f0e10dd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="user-input-in-a-windows-forms-application"></a><span data-ttu-id="a1069-102">Windows 窗体应用程序中的用户输入</span><span class="sxs-lookup"><span data-stu-id="a1069-102">User Input in a Windows Forms Application</span></span>
<span data-ttu-id="a1069-103">在 Windows 窗体，用户输入发送到 Windows 消息的窗体中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1069-103">In Windows Forms, user input is sent to applications in the form of Windows messages.</span></span> <span data-ttu-id="a1069-104">可重写方法的一系列处理在应用程序窗体中，这些消息，并控制级别。</span><span class="sxs-lookup"><span data-stu-id="a1069-104">A series of overridable methods process these messages at the application, form, and control level.</span></span> <span data-ttu-id="a1069-105">当这些方法接收鼠标和键盘消息时，因此将引发可以处理以获取信息鼠标或键盘输入的事件。</span><span class="sxs-lookup"><span data-stu-id="a1069-105">When these methods receive mouse and keyboard messages, they raise events that can be handled to get information about the mouse or keyboard input.</span></span> <span data-ttu-id="a1069-106">在许多情况下，Windows 窗体应用程序将能够只需通过处理这些事件处理所有用户输入。</span><span class="sxs-lookup"><span data-stu-id="a1069-106">In many cases, Windows Forms applications will be able to process all user input simply by handling these events.</span></span> <span data-ttu-id="a1069-107">在其他情况下，应用程序可能需要重写处理消息以便由应用程序、 窗体中或控件接收到之前截获某个特定消息的方法之一。</span><span class="sxs-lookup"><span data-stu-id="a1069-107">In other cases, an application may need to override one of the methods that process messages in order to intercept a particular message before it is received by the application, form, or control.</span></span>  
  
## <a name="mouse-and-keyboard-events"></a><span data-ttu-id="a1069-108">鼠标和键盘事件</span><span class="sxs-lookup"><span data-stu-id="a1069-108">Mouse and Keyboard Events</span></span>  
 <span data-ttu-id="a1069-109">所有 Windows 窗体控件都继承一的组与鼠标和键盘输入相关的事件。</span><span class="sxs-lookup"><span data-stu-id="a1069-109">All Windows Forms controls inherit a set of events related to mouse and keyboard input.</span></span> <span data-ttu-id="a1069-110">例如，可以处理控件<xref:System.Windows.Forms.Control.KeyPress>事件可以确定曾按下的键的字符代码或控件可以处理<xref:System.Windows.Forms.Control.MouseClick>事件，以确定的鼠标位置单击。</span><span class="sxs-lookup"><span data-stu-id="a1069-110">For example, a control can handle the <xref:System.Windows.Forms.Control.KeyPress> event to determine the character code of a key that was pressed, or a control can handle the <xref:System.Windows.Forms.Control.MouseClick> event to determine the location of a mouse click.</span></span> <span data-ttu-id="a1069-111">有关鼠标和键盘事件的详细信息，请参阅[使用键盘事件](../../../docs/framework/winforms/using-keyboard-events.md)和[Windows 窗体中的鼠标事件](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="a1069-111">For more information on the mouse and keyboard events, see [Using Keyboard Events](../../../docs/framework/winforms/using-keyboard-events.md) and [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).</span></span>  
  
## <a name="methods-that-process-user-input-messages"></a><span data-ttu-id="a1069-112">处理用户输入的消息的方法</span><span class="sxs-lookup"><span data-stu-id="a1069-112">Methods that Process User Input Messages</span></span>  
 <span data-ttu-id="a1069-113">窗体和控件有权访问<xref:System.Windows.Forms.IMessageFilter>界面和一组处理 Windows 消息的消息队列中的不同点的可重写方法。</span><span class="sxs-lookup"><span data-stu-id="a1069-113">Forms and controls have access to the <xref:System.Windows.Forms.IMessageFilter> interface and a set of overridable methods that process Windows messages at different points in the message queue.</span></span> <span data-ttu-id="a1069-114">这些方法都有<xref:System.Windows.Forms.Message>参数，它封装 Windows 消息的低级别的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a1069-114">These methods all have a <xref:System.Windows.Forms.Message> parameter, which encapsulates the low-level details of Windows messages.</span></span> <span data-ttu-id="a1069-115">可以实现，也可以重写这些方法，以检查的消息，然后使用消息或将其传递到消息队列中的下一步使用者。</span><span class="sxs-lookup"><span data-stu-id="a1069-115">You can implement or override these methods to examine the message and then either consume the message or pass it on to the next consumer in the message queue.</span></span> <span data-ttu-id="a1069-116">下表列出了处理 Windows 窗体中的所有 Windows 消息的方法。</span><span class="sxs-lookup"><span data-stu-id="a1069-116">The following table presents the methods that process all Windows messages in Windows Forms.</span></span>  
  
|<span data-ttu-id="a1069-117">方法</span><span class="sxs-lookup"><span data-stu-id="a1069-117">Method</span></span>|<span data-ttu-id="a1069-118">说明</span><span class="sxs-lookup"><span data-stu-id="a1069-118">Notes</span></span>|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|<span data-ttu-id="a1069-119">此方法会截获排队应用程序级别 （也称为已发布） 的 Windows 消息。</span><span class="sxs-lookup"><span data-stu-id="a1069-119">This method intercepts queued (also known as posted) Windows messages at the application level.</span></span>|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|<span data-ttu-id="a1069-120">已处理之前，此方法会截获窗体和控件级别的 Windows 消息。</span><span class="sxs-lookup"><span data-stu-id="a1069-120">This method intercepts Windows messages at the form and control level before they have been processed.</span></span>|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|<span data-ttu-id="a1069-121">此方法处理 Windows 消息级别的窗体和控件。</span><span class="sxs-lookup"><span data-stu-id="a1069-121">This method processes Windows messages at the form and control level.</span></span>|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|<span data-ttu-id="a1069-122">此方法执行级别的窗体和控件的 Windows 消息的默认处理。</span><span class="sxs-lookup"><span data-stu-id="a1069-122">This method performs the default processing of Windows messages at the form and control level.</span></span> <span data-ttu-id="a1069-123">这提供一个窗口的最小功能。</span><span class="sxs-lookup"><span data-stu-id="a1069-123">This provides the minimal functionality of a window.</span></span>|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|<span data-ttu-id="a1069-124">处理完后，此方法将截获消息级别的窗体和控件。</span><span class="sxs-lookup"><span data-stu-id="a1069-124">This method intercepts messages at the form and control level, after they have been processed.</span></span> <span data-ttu-id="a1069-125"><xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage>样式位，必须为要调用此方法设置。</span><span class="sxs-lookup"><span data-stu-id="a1069-125">The <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> style bit must be set for this method to be called.</span></span>|  
  
 <span data-ttu-id="a1069-126">通过额外的一组特定于这些类型的消息的可重写方法还处理键盘和鼠标的消息。</span><span class="sxs-lookup"><span data-stu-id="a1069-126">Keyboard and mouse messages are also processed by an additional set of overridable methods that are specific to those types of messages.</span></span> <span data-ttu-id="a1069-127">有关详细信息，请参阅[键盘输入工作原理](../../../docs/framework/winforms/how-keyboard-input-works.md)和[鼠标输入工作原理 Windows 窗体中](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="a1069-127">For more information, see [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md) and [How Mouse Input Works in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1069-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1069-128">See Also</span></span>  
 [<span data-ttu-id="a1069-129">Windows 窗体中的用户输入</span><span class="sxs-lookup"><span data-stu-id="a1069-129">User Input in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 [<span data-ttu-id="a1069-130">Windows 窗体应用程序中的键盘输入</span><span class="sxs-lookup"><span data-stu-id="a1069-130">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="a1069-131">Windows 窗体应用程序中的鼠标输入</span><span class="sxs-lookup"><span data-stu-id="a1069-131">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
