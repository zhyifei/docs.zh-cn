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
ms.openlocfilehash: a1317f34b39c5689e285f8822fff9bfcc42db1d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680312"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="04185-102">如何：使用 Windows 窗体 Label 控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="04185-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="04185-103">Windows 窗体<xref:System.Windows.Forms.Label>控件可用于定义其他控件的访问键。</span><span class="sxs-lookup"><span data-stu-id="04185-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="04185-104">在标签控件中定义访问键时，用户可以同时按 ALT 键和指定的字符，以便将焦点移到 Tab 键顺序中排在其后面的控件。</span><span class="sxs-lookup"><span data-stu-id="04185-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="04185-105">由于标签不能接收焦点，因此焦点会自动移到 Tab 键顺序中的下一个控件。</span><span class="sxs-lookup"><span data-stu-id="04185-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="04185-106">使用此方法可将访问键分配给文本框、组合框、列表框和数据网格。</span><span class="sxs-lookup"><span data-stu-id="04185-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="04185-107">若要向使用标签控件分配访问键</span><span class="sxs-lookup"><span data-stu-id="04185-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="04185-108">首先，绘制标签并画出另一个控件。</span><span class="sxs-lookup"><span data-stu-id="04185-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="04185-109">或</span><span class="sxs-lookup"><span data-stu-id="04185-109">-or-</span></span>  
  
     <span data-ttu-id="04185-110">按任意顺序绘制控件，并设置<xref:System.Windows.Forms.Control.TabIndex%2A>标签为一个小于另一个控件的属性。</span><span class="sxs-lookup"><span data-stu-id="04185-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="04185-111">设置的标签<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="04185-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="04185-112">使用与号 (&) 中标签的<xref:System.Windows.Forms.Label.Text%2A>要分配为标签的访问密钥属性。</span><span class="sxs-lookup"><span data-stu-id="04185-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="04185-113">有关详细信息，请参阅[的 Windows 窗体控件创建访问密钥](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="04185-113">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04185-114">您可能想要显示与号中的标签控件，而不使用它们来创建访问键。</span><span class="sxs-lookup"><span data-stu-id="04185-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="04185-115">如果将标签控件绑定到其中的数据包括与号在记录集中的字段，这可能会出现。</span><span class="sxs-lookup"><span data-stu-id="04185-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="04185-116">若要在标签控件中显示与号，请设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="04185-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="04185-117">如果你想要显示与号，并且还具有访问密钥，设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性设置为`true`并指示访问密钥与一个 & 号 (&) 和与符号以显示两个 & 号。</span><span class="sxs-lookup"><span data-stu-id="04185-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04185-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="04185-118">See also</span></span>
- [<span data-ttu-id="04185-119">如何：调整 Windows 窗体标签控件以适应其内容的大小</span><span class="sxs-lookup"><span data-stu-id="04185-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="04185-120">Label 控件概述</span><span class="sxs-lookup"><span data-stu-id="04185-120">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [<span data-ttu-id="04185-121">Label 控件</span><span class="sxs-lookup"><span data-stu-id="04185-121">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
