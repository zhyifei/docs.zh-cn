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
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>如何：调整 Windows 窗体标签控件大小以适应其内容
Windows 窗体<xref:System.Windows.Forms.Label>控件均可以是单行或多行，并且它可以为固定大小，或可以自动调整自身大小以适应其标题。 <xref:System.Windows.Forms.Label.AutoSize%2A>属性可帮助你调整控件大小以适应更大或更小的标题，即如果标题将更改在运行时特别有用的大小。  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>若要使动态调整大小以适应其内容的标签控件  
  
1.  设置其<xref:System.Windows.Forms.Label.AutoSize%2A>属性`true`。  
  
 如果<xref:System.Windows.Forms.Label.AutoSize%2A>设置为`false`中, 指定的词语<xref:System.Windows.Forms.Label.Text%2A>属性将换到下一行如果可能，但不是会增长到控件。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用 Windows 窗体 Label 控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [Label 控件概述](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Label 控件](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
