---
title: 如何：创建 Windows 窗体控件的访问键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 53ffd3632ff3e1179a72f1e2bfe4ea366e28b0f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530944"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="56f18-102">如何：创建 Windows 窗体控件的访问键</span><span class="sxs-lookup"><span data-stu-id="56f18-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="56f18-103">*访问密钥*菜单、 菜单项或如按钮控件的标签的文本中带下划线的字符。</span><span class="sxs-lookup"><span data-stu-id="56f18-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="56f18-104">具有访问密钥，用户可以"单击"按钮通过同时按下 ALT 键和预定义的访问键。</span><span class="sxs-lookup"><span data-stu-id="56f18-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="56f18-105">例如，如果某个按钮可运行一个过程来打印窗体，因此其`Text`属性设置为"打印"之前的字母"P"使得字母"P"以在运行时中会带有下划线的按钮文本中添加一个与号。</span><span class="sxs-lookup"><span data-stu-id="56f18-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="56f18-106">用户可以运行该命令通过按 ALT + P 与按钮相关联。</span><span class="sxs-lookup"><span data-stu-id="56f18-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="56f18-107">不能具有不能接收焦点的控件的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="56f18-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="56f18-108">若要创建的控件的访问密钥</span><span class="sxs-lookup"><span data-stu-id="56f18-108">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="56f18-109">设置`Text`属性将设成快捷键的字母前为一个字符串，包含一个 & 号 (&)。</span><span class="sxs-lookup"><span data-stu-id="56f18-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="56f18-110">若要而无需创建访问键，在标题中包含 & 符，包括两个 & 号 (& &)。</span><span class="sxs-lookup"><span data-stu-id="56f18-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="56f18-111">一个与号显示的标题中，带下划线的任何字符。</span><span class="sxs-lookup"><span data-stu-id="56f18-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f18-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="56f18-112">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="56f18-113">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="56f18-113">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="56f18-114">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="56f18-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="56f18-115">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="56f18-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
