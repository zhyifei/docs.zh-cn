---
title: "如何：使用设计器为 Windows 窗体控件创建访问键"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed3bf2aa1e6081ca018f1b4dec98e6304a1aa95c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="2406f-102">如何：使用设计器为 Windows 窗体控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="2406f-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="2406f-103">*访问密钥*菜单、 菜单项或如按钮控件的标签的文本中带下划线的字符。</span><span class="sxs-lookup"><span data-stu-id="2406f-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="2406f-104">它使用户能够通过同时按下 ALT 键和预定义的访问键"单击"按钮。</span><span class="sxs-lookup"><span data-stu-id="2406f-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="2406f-105">例如，如果某个按钮可运行一个过程来打印窗体，因此其`Text`"P"使得字母"P"以显示为带有下划线的按钮文本中在运行时的字母前到"打印，"添加一个与号 (&) 设置属性。</span><span class="sxs-lookup"><span data-stu-id="2406f-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="2406f-106">用户可以运行该命令通过按 ALT + P 与按钮相关联。</span><span class="sxs-lookup"><span data-stu-id="2406f-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="2406f-107">不能具有不能接收焦点的控件的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="2406f-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2406f-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="2406f-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2406f-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="2406f-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2406f-110">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="2406f-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="2406f-111">若要创建的控件的访问密钥</span><span class="sxs-lookup"><span data-stu-id="2406f-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="2406f-112">在**属性**窗口中，设置`Text`属性将成为访问键的字母前为一个字符串，包含一个 & 号 (&)。</span><span class="sxs-lookup"><span data-stu-id="2406f-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="2406f-113">例如，若要设置为访问键的字母"P"，键入**和打印**到网格。</span><span class="sxs-lookup"><span data-stu-id="2406f-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2406f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2406f-114">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="2406f-115">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="2406f-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="2406f-116">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="2406f-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="2406f-117">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="2406f-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
