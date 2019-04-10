---
title: 如何：设置 Windows 窗体 NumericUpDown 控件的格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5957a44c7b07aa1b8d8df32667f023c0873ec1de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186130"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>如何：设置 Windows 窗体 NumericUpDown 控件的格式
可以配置在 Windows 窗体中显示值的方式<xref:System.Windows.Forms.NumericUpDown>控件。 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>属性确定显示小数点后的几位数字; 默认值为 0。 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>属性确定是否将每隔三个十进制数字之间插入分隔符; 默认值为`false`。 如果控件可以显示的值而不是十进制格式的十六进制<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>属性设置为`true`; 默认值是`false`。  
  
### <a name="to-format-the-numeric-value"></a>若要设置格式的数字值  
  
-   通过设置显示十进制数值<xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>属性设置为一个整数，并设置<xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>属性设置为`true`或`false`。  
  
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
  
-   通过设置显示十六进制值<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>属性设置为`true`。  
  
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
    >  即使值显示为十六进制窗体上，任何测试您对<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性要测试其十进制值。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown 控件](numericupdown-control-windows-forms.md)
- [NumericUpDown 控件概述](numericupdown-control-overview-windows-forms.md)
