---
title: 如何：响应 Windows 窗体按钮的单击
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: a10eaa3ea62df9301a53f5609b503bfabcb50a46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110066"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="1a206-102">如何：响应 Windows 窗体按钮的单击</span><span class="sxs-lookup"><span data-stu-id="1a206-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="1a206-103">Windows 窗体的最基本用法<xref:System.Windows.Forms.Button>控件将在单击按钮时运行某些代码。</span><span class="sxs-lookup"><span data-stu-id="1a206-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="1a206-104">单击<xref:System.Windows.Forms.Button>控件还会生成大量的其他事件，如<xref:System.Windows.Forms.Control.MouseEnter>， <xref:System.Windows.Forms.Control.MouseDown>，和<xref:System.Windows.Forms.Control.MouseUp>事件。</span><span class="sxs-lookup"><span data-stu-id="1a206-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="1a206-105">如果你想要附加这些相关事件的事件处理程序，请确保它们的操作不会冲突。</span><span class="sxs-lookup"><span data-stu-id="1a206-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="1a206-106">例如，如果单击该按钮将清除用户已在文本框中键入的信息，将鼠标指针暂停到按钮上方时就不应显示工具提示信息的已不存在。</span><span class="sxs-lookup"><span data-stu-id="1a206-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="1a206-107">如果用户尝试双击<xref:System.Windows.Forms.Button>控件，每次单击将单独处理; 即，该控件不支持双击事件。</span><span class="sxs-lookup"><span data-stu-id="1a206-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="1a206-108">若要响应按钮单击</span><span class="sxs-lookup"><span data-stu-id="1a206-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="1a206-109">在按钮的`Click`<xref:System.EventHandler>编写代码来运行。</span><span class="sxs-lookup"><span data-stu-id="1a206-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> `Button1_Click` <span data-ttu-id="1a206-110">必须绑定到控件。</span><span class="sxs-lookup"><span data-stu-id="1a206-110">must be bound to the control.</span></span> <span data-ttu-id="1a206-111">有关详细信息，请参阅[如何：在运行时为 Windows 窗体创建事件处理程序](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="1a206-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1a206-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a206-112">See also</span></span>

- [<span data-ttu-id="1a206-113">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="1a206-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="1a206-114">选择 Windows 窗体 Button 控件的方法</span><span class="sxs-lookup"><span data-stu-id="1a206-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="1a206-115">Button 控件</span><span class="sxs-lookup"><span data-stu-id="1a206-115">Button Control</span></span>](button-control-windows-forms.md)
