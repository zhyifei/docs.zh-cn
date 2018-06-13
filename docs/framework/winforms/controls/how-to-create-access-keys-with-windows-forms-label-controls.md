---
title: 如何：使用 Windows 窗体 Label 控件创建访问键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: fc9592981f3d926b2b5b85b6869da13dc644e7a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530798"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="490d7-102">如何：使用 Windows 窗体 Label 控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="490d7-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="490d7-103">Windows 窗体<xref:System.Windows.Forms.Label>控件可以用于定义其他控件的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="490d7-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="490d7-104">当标签控件中定义的访问密钥时，用户可以按 ALT 键加你指定要将焦点移到控件的 tab 键顺序将它后面的字符。</span><span class="sxs-lookup"><span data-stu-id="490d7-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="490d7-105">因为标签不能接收焦点，焦点将自动移动到下一个控件的 tab 键顺序。</span><span class="sxs-lookup"><span data-stu-id="490d7-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="490d7-106">使用此方法将访问密钥分配到文本框、 组合框、 列表框和数据网格。</span><span class="sxs-lookup"><span data-stu-id="490d7-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="490d7-107">要分配给了标签控件的访问密钥</span><span class="sxs-lookup"><span data-stu-id="490d7-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="490d7-108">首先，绘制标签，然后绘制另一个控件。</span><span class="sxs-lookup"><span data-stu-id="490d7-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="490d7-109">-或-</span><span class="sxs-lookup"><span data-stu-id="490d7-109">-or-</span></span>  
  
     <span data-ttu-id="490d7-110">按任意顺序绘制控件，并设置<xref:System.Windows.Forms.Control.TabIndex%2A>属性为一个小于另一个控件的标签。</span><span class="sxs-lookup"><span data-stu-id="490d7-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="490d7-111">设置标签的<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="490d7-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="490d7-112">使用与号 (&) 中的标签<xref:System.Windows.Forms.Label.Text%2A>要分配标签的访问密钥属性。</span><span class="sxs-lookup"><span data-stu-id="490d7-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="490d7-113">有关详细信息，请参阅[为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="490d7-113">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="490d7-114">你可能想要显示的标签控件，在与符号，而不是使用它们来创建访问键。</span><span class="sxs-lookup"><span data-stu-id="490d7-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="490d7-115">这可能是如果你将一个标签控件绑定到其中的数据包括 & 在记录集中的字段。</span><span class="sxs-lookup"><span data-stu-id="490d7-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="490d7-116">若要显示的标签控件中的 &，请设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性`false`。</span><span class="sxs-lookup"><span data-stu-id="490d7-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="490d7-117">如果你想要显示与符号，并且还具有的访问密钥，设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性`true`并指示访问密钥与一个 & 号 (&) 和连字符来显示两个 & 号。</span><span class="sxs-lookup"><span data-stu-id="490d7-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="490d7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="490d7-118">See Also</span></span>  
 [<span data-ttu-id="490d7-119">如何：重设 Windows 窗体 Label 控件大小以适应其内容</span><span class="sxs-lookup"><span data-stu-id="490d7-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="490d7-120">Label 控件概述</span><span class="sxs-lookup"><span data-stu-id="490d7-120">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="490d7-121">Label 控件</span><span class="sxs-lookup"><span data-stu-id="490d7-121">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
