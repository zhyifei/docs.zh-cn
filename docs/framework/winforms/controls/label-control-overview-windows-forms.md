---
title: "Label 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f68642eb5f996722097976e042006afbf366ae39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="d4cb6-102">Label 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="d4cb6-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="d4cb6-103">Windows 窗体<xref:System.Windows.Forms.Label>控件用于显示文本或图像的用户无法编辑。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="d4cb6-104">它们用于标识窗体上的对象-哪些某个控件的说明进行的操作如果单击，例如，或以响应运行时事件或应用程序中的过程中显示信息。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="d4cb6-105">例如，可以使用标签将描述性标题添加到文本框、 列表框、 组合框和等等。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="d4cb6-106">你还可以编写在运行时通过响应事件中的标签显示的文本更改的代码。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="d4cb6-107">例如，如果你的应用程序需要几分钟时间才能处理变更，你可以在标签中显示的处理状态消息。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="d4cb6-108">使用标签控件</span><span class="sxs-lookup"><span data-stu-id="d4cb6-108">Working with the Label Control</span></span>  
 <span data-ttu-id="d4cb6-109">因为<xref:System.Windows.Forms.Label>控件不能接收焦点，所以也可以用来创建其他控件的访问键。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="d4cb6-110">访问键允许用户通过按 ALT 键和访问键选择另一个控件。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="d4cb6-111">有关详细信息，请参阅[为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)和[如何： 使用 Windows 窗体标签控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-111">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="d4cb6-112">中包含标签中显示的标题<xref:System.Windows.Forms.Label.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="d4cb6-113"><xref:System.Windows.Forms.Label.TextAlign%2A>属性可以设置在标签中的文本的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="d4cb6-114">有关详细信息，请参阅[如何： 设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cb6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4cb6-115">See Also</span></span>  
 <xref:System.Windows.Forms.Label>  
 [<span data-ttu-id="d4cb6-116">如何：重设 Windows 窗体 Label 控件大小以适应其内容</span><span class="sxs-lookup"><span data-stu-id="d4cb6-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="d4cb6-117">如何：使用 Windows 窗体 Label 控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="d4cb6-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
