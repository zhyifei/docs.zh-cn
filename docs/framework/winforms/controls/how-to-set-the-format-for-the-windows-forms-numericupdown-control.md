---
title: "如何：设置 Windows 窗体 NumericUpDown 控件的格式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4ff6d8e584e65482285012af351ebd1a669b806
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>如何：设置 Windows 窗体 NumericUpDown 控件的格式
你可以配置 Windows 窗体中显示值的方式<xref:System.Windows.Forms.NumericUpDown>控件。 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>属性决定小数点后出现多少个号码; 默认值为 0。 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>属性确定是否将每隔三个十进制数字之间插入分隔符; 默认值为`false`。 如果控件可以显示值而不是十进制格式的十六进制<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>属性设置为`true`; 默认值是`false`。  
  
### <a name="to-format-the-numeric-value"></a>若要设置格式的数字值  
  
-   通过设置显示的十进制值<xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>属性设置为一个整数，并设置<xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>属性`true`或`false`。  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     或  
  
-   通过设置显示的十六进制值<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>属性`true`。  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  即使的值将显示为十六进制窗体上，任何测试您对执行<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性将正在测试其十进制值。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.NumericUpDown>  
 [NumericUpDown 控件](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [NumericUpDown 控件概述](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
