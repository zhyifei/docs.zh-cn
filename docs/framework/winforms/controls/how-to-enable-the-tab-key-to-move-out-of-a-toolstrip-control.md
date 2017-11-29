---
title: "如何：使 Tab 键能够移出 ToolStrip 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5f4583a0381af6f0f85f9c2e2aea1d122f5174ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>如何：使 Tab 键能够移出 ToolStrip 控件
使用以下过程以使用户能够按 TAB 键能够移出的<xref:System.Windows.Forms.ToolStrip>的 tab 键顺序的下一个控件。  
  
 <xref:System.Windows.Forms.ToolStrip>接受第一次按 TAB 键和箭头键中的选择项<xref:System.Windows.Forms.ToolStrip>。 当用户在第二次按 TAB 键时，它将用户带到下一个控件的 tab 键顺序。  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>若要使用户能够按 TAB 键能够移出 ToolStrip 到下一个控件  
  
-   设置<xref:System.Windows.Forms.ToolStrip.TabStop%2A>属性<xref:System.Windows.Forms.ToolStrip>到`true`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
