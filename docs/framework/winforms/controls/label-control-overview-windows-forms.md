---
title: Label 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: 282f7fe8117b2c1b0fc23cb97bad7a34f6d106be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619469"
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="7a98d-102">Label 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="7a98d-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="7a98d-103">Windows 窗体<xref:System.Windows.Forms.Label>控件用于显示文本或图像，用户不能编辑。</span><span class="sxs-lookup"><span data-stu-id="7a98d-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="7a98d-104">它们用于确定在窗体上的对象，哪些特定控件的说明进行的操作如果单击，例如，或以响应运行时事件或在应用程序中的过程中显示信息。</span><span class="sxs-lookup"><span data-stu-id="7a98d-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="7a98d-105">例如，可以使用标签将描述性的隐藏式字幕添加到文本框、 列表框、 组合框等。</span><span class="sxs-lookup"><span data-stu-id="7a98d-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="7a98d-106">此外可以编写在运行时通过响应事件中的标签显示的文本更改的代码。</span><span class="sxs-lookup"><span data-stu-id="7a98d-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="7a98d-107">例如，如果你的应用程序需要几分钟来处理更改，您可以在标签中显示的处理状态消息。</span><span class="sxs-lookup"><span data-stu-id="7a98d-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="7a98d-108">使用标签控件</span><span class="sxs-lookup"><span data-stu-id="7a98d-108">Working with the Label Control</span></span>  
 <span data-ttu-id="7a98d-109">因为<xref:System.Windows.Forms.Label>控件不能接收焦点，也可用于为其他控件创建访问键。</span><span class="sxs-lookup"><span data-stu-id="7a98d-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="7a98d-110">访问键允许用户通过按 ALT 键的访问密钥和选择另一个控件。</span><span class="sxs-lookup"><span data-stu-id="7a98d-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="7a98d-111">有关详细信息，请参阅[的 Windows 窗体控件创建访问密钥](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)和[如何：使用 Windows 窗体 Label 控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="7a98d-111">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="7a98d-112">在该标签中显示的标题中包含<xref:System.Windows.Forms.Label.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7a98d-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="7a98d-113"><xref:System.Windows.Forms.Label.TextAlign%2A>属性可以设置标签中文本的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="7a98d-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="7a98d-114">有关详细信息，请参阅[如何：设置显示的文本的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="7a98d-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a98d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a98d-115">See also</span></span>
- <xref:System.Windows.Forms.Label>
- [<span data-ttu-id="7a98d-116">如何：调整 Windows 窗体标签控件以适应其内容的大小</span><span class="sxs-lookup"><span data-stu-id="7a98d-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="7a98d-117">如何：使用 Windows 窗体 Label 控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="7a98d-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
