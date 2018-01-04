---
title: "如何：调整 Windows 窗体标签控件大小以适应其内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2c34506ca33af80b83f365893e56a5a9d437b89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="bb8f2-102">如何：调整 Windows 窗体标签控件大小以适应其内容</span><span class="sxs-lookup"><span data-stu-id="bb8f2-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="bb8f2-103">Windows 窗体<xref:System.Windows.Forms.Label>控件均可以是单行或多行，并且它可以为固定大小，或可以自动调整自身大小以适应其标题。</span><span class="sxs-lookup"><span data-stu-id="bb8f2-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="bb8f2-104"><xref:System.Windows.Forms.Label.AutoSize%2A>属性可帮助你调整控件大小以适应更大或更小的标题，即如果标题将更改在运行时特别有用的大小。</span><span class="sxs-lookup"><span data-stu-id="bb8f2-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="bb8f2-105">若要使动态调整大小以适应其内容的标签控件</span><span class="sxs-lookup"><span data-stu-id="bb8f2-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="bb8f2-106">设置其<xref:System.Windows.Forms.Label.AutoSize%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="bb8f2-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="bb8f2-107">如果<xref:System.Windows.Forms.Label.AutoSize%2A>设置为`false`中, 指定的词语<xref:System.Windows.Forms.Label.Text%2A>属性将换到下一行如果可能，但不是会增长到控件。</span><span class="sxs-lookup"><span data-stu-id="bb8f2-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8f2-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb8f2-108">See Also</span></span>  
 [<span data-ttu-id="bb8f2-109">如何：使用 Windows 窗体 Label 控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="bb8f2-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [<span data-ttu-id="bb8f2-110">Label 控件概述</span><span class="sxs-lookup"><span data-stu-id="bb8f2-110">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="bb8f2-111">Label 控件</span><span class="sxs-lookup"><span data-stu-id="bb8f2-111">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
