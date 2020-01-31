---
title: 设置 NumericUpDown 控件的格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742184"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>방법: Windows Forms NumericUpDown 컨트롤의 형식 설정
你可以配置值在 Windows 窗体 <xref:System.Windows.Forms.NumericUpDown> 控件中的显示方式。 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 属性确定小数点后显示的数字数;默认值为0。 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 属性确定是否在每三位十进制数之间插入分隔符;默认值为 `false`。 如果 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 属性设置为 `true`，则控件可以以十六进制而不是十进制格式显示值;默认值为 `false`。  
  
### <a name="to-format-the-numeric-value"></a>设置数值的格式  
  
- 通过将 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 属性设置为整数并将 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 属性设置为 `true` 或 `false`来显示十进制值。  
  
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
  
     -또는-  
  
- 通过将 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 属性设置为 `true`来显示十六进制值。  
  
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
    > 即使值以十六进制形式显示在窗体上，对 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 属性执行的任何测试也将测试其小数值。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown 컨트롤](numericupdown-control-windows-forms.md)
- [NumericUpDown 컨트롤 개요](numericupdown-control-overview-windows-forms.md)
