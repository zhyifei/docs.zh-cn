---
title: "如何：使用 Windows 窗体 GroupBox 控件对控件分组"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50d29de04b4e221105bb02e58de01344f13af69f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>如何：使用 Windows 窗体 GroupBox 控件对控件分组
Windows 窗体<xref:System.Windows.Forms.GroupBox>控制用于其他控件进行分组。 有三个与组控件的原因：  
  
-   若要创建适用于清除用户界面相关的窗体元素的直观分组。  
  
-   若要创建 （的单选按钮，例如） 以编程方式分组。  
  
-   用于在设计时，请作为一个单元中移动控件。  
  
### <a name="to-create-a-group-of-controls"></a>若要创建一组控件  
  
1.  绘制<xref:System.Windows.Forms.GroupBox>窗体上的控件。  
  
2.  将其他控件添加到组中，绘制每个分组框内。  
  
     如果你有想要将括在组中的现有控件，可以选择所有控件，将它们剪切到剪贴板，再都选择<xref:System.Windows.Forms.GroupBox>控制，然后将它们粘贴到组框。 你还可以将其拖到组框。  
  
3.  设置<xref:System.Windows.Forms.GroupBox.Text%2A>分组框为适当标题的属性。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.GroupBox>  
 [GroupBox 控件](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
