---
title: 如何：设置 Windows 窗体控件所显示的文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: d9c9bea26cfc3d5b2cfc4484173a7680ff2fc34d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399321"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="e62e5-102">如何：设置 Windows 窗体控件所显示的文本</span><span class="sxs-lookup"><span data-stu-id="e62e5-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="e62e5-103">Windows 窗体控件通常会显示一些与控件的主要功能相关的文本。</span><span class="sxs-lookup"><span data-stu-id="e62e5-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="e62e5-104">例如，<xref:System.Windows.Forms.Button> 控件通常会显示一个题注，用于指示单击按钮时将执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e62e5-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="e62e5-105">对于所有控件而言，都可通过使用 <xref:System.Windows.Forms.Control.Text%2A> 属性来设置或返回文本。</span><span class="sxs-lookup"><span data-stu-id="e62e5-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="e62e5-106">可以使用 <xref:System.Windows.Forms.Control.Font%2A> 属性更改字体。</span><span class="sxs-lookup"><span data-stu-id="e62e5-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="e62e5-107">还可使用设计器来设置文本。</span><span class="sxs-lookup"><span data-stu-id="e62e5-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="e62e5-108">另请参阅[如何： 创建访问密钥的 Windows 窗体控件使用设计器](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md)，[如何： 通过使用 Windows 窗体控件显示的文本将设计器设置](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md)，[如何： 设置的图像显示 Windows 窗体控件使用设计器](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="e62e5-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="e62e5-109">以编程方式设置控件所显示的文本</span><span class="sxs-lookup"><span data-stu-id="e62e5-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="e62e5-110">将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为字符串。</span><span class="sxs-lookup"><span data-stu-id="e62e5-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="e62e5-111">若要创建一个带下划线的访问键，请使将成为访问键的字母前包含一个 & 号 (&)。</span><span class="sxs-lookup"><span data-stu-id="e62e5-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="e62e5-112">将 <xref:System.Windows.Forms.Control.Font%2A> 属性设置为类型 <xref:System.Drawing.Font> 的对象。</span><span class="sxs-lookup"><span data-stu-id="e62e5-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="e62e5-113">可使用转义符来显示用户界面元素中的特殊字符，通常对这些元素（如菜单项）有着不同的解释。</span><span class="sxs-lookup"><span data-stu-id="e62e5-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="e62e5-114">例如，下面的代码行将菜单项的文本设置为“现读取完全不同的内容”：</span><span class="sxs-lookup"><span data-stu-id="e62e5-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e62e5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e62e5-115">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e62e5-116">如何：创建 Windows 窗体控件的访问键</span><span class="sxs-lookup"><span data-stu-id="e62e5-116">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="e62e5-117">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="e62e5-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
