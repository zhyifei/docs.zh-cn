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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013187"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="7071a-102">如何：设置 Windows 窗体 NumericUpDown 控件的格式</span><span class="sxs-lookup"><span data-stu-id="7071a-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="7071a-103">可以配置在 Windows 窗体中显示值的方式<xref:System.Windows.Forms.NumericUpDown>控件。</span><span class="sxs-lookup"><span data-stu-id="7071a-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="7071a-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>属性确定显示小数点后的几位数字; 默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="7071a-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="7071a-105"><xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>属性确定是否将每隔三个十进制数字之间插入分隔符; 默认值为`false`。</span><span class="sxs-lookup"><span data-stu-id="7071a-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="7071a-106">如果控件可以显示的值而不是十进制格式的十六进制<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>属性设置为`true`; 默认值是`false`。</span><span class="sxs-lookup"><span data-stu-id="7071a-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="7071a-107">若要设置格式的数字值</span><span class="sxs-lookup"><span data-stu-id="7071a-107">To format the numeric value</span></span>  
  
-   <span data-ttu-id="7071a-108">通过设置显示十进制数值<xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>属性设置为一个整数，并设置<xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>属性设置为`true`或`false`。</span><span class="sxs-lookup"><span data-stu-id="7071a-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="7071a-109">或</span><span class="sxs-lookup"><span data-stu-id="7071a-109">-or-</span></span>  
  
-   <span data-ttu-id="7071a-110">通过设置显示十六进制值<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="7071a-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    >  <span data-ttu-id="7071a-111">即使值显示为十六进制窗体上，任何测试您对<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性要测试其十进制值。</span><span class="sxs-lookup"><span data-stu-id="7071a-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7071a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7071a-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="7071a-113">NumericUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="7071a-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="7071a-114">NumericUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="7071a-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
