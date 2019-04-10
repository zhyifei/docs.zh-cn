---
title: 如何：设置 Windows 窗体控件显示的文本
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
ms.openlocfilehash: 59570af89e6236e3c13866d45dc5361d52b84274
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308518"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="f704c-102">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="f704c-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="f704c-103">Windows 窗体控件通常会显示一些与控件的主要功能相关的文本。</span><span class="sxs-lookup"><span data-stu-id="f704c-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="f704c-104">例如，<xref:System.Windows.Forms.Button> 控件通常会显示一个题注，用于指示单击按钮时将执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f704c-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="f704c-105">对于所有控件而言，都可通过使用 <xref:System.Windows.Forms.Control.Text%2A> 属性来设置或返回文本。</span><span class="sxs-lookup"><span data-stu-id="f704c-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="f704c-106">可以使用 <xref:System.Windows.Forms.Control.Font%2A> 属性更改字体。</span><span class="sxs-lookup"><span data-stu-id="f704c-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="f704c-107">还可使用设计器来设置文本。</span><span class="sxs-lookup"><span data-stu-id="f704c-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="f704c-108">另请参阅[如何：创建 Windows 窗体控件使用设计器的访问键](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md)，[如何：设置显示的文本的 Windows 窗体控件使用设计器](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md)，[如何：设置所显示的图像的 Windows 窗体控件使用设计器](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="f704c-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="f704c-109">以编程方式设置控件所显示的文本</span><span class="sxs-lookup"><span data-stu-id="f704c-109">To set the text displayed by a control programmatically</span></span>  
  
1. <span data-ttu-id="f704c-110">将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为字符串。</span><span class="sxs-lookup"><span data-stu-id="f704c-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="f704c-111">若要创建带下划线的访问密钥，包含一个 & 号 (&) 将访问密钥的字母前。</span><span class="sxs-lookup"><span data-stu-id="f704c-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2. <span data-ttu-id="f704c-112">将 <xref:System.Windows.Forms.Control.Font%2A> 属性设置为类型 <xref:System.Drawing.Font> 的对象。</span><span class="sxs-lookup"><span data-stu-id="f704c-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
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
    >  <span data-ttu-id="f704c-113">可使用转义符来显示用户界面元素中的特殊字符，通常对这些元素（如菜单项）有着不同的解释。</span><span class="sxs-lookup"><span data-stu-id="f704c-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="f704c-114">例如，以下代码行设置要读取的菜单项的文本"和现在的内容完全不同":</span><span class="sxs-lookup"><span data-stu-id="f704c-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f704c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f704c-115">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f704c-116">如何：创建 Windows 窗体控件的访问键</span><span class="sxs-lookup"><span data-stu-id="f704c-116">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="f704c-117">如何：响应 Windows 窗体按钮的单击</span><span class="sxs-lookup"><span data-stu-id="f704c-117">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
