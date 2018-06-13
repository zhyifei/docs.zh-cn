---
title: 如何：使用 Windows 窗体 NumericUpDown 控件设置和返回数值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: e214f556224577c3029b2b742784e58932d792f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535556"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="97fdc-102">如何：使用 Windows 窗体 NumericUpDown 控件设置和返回数值</span><span class="sxs-lookup"><span data-stu-id="97fdc-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="97fdc-103">Windows 窗体的数字值<xref:System.Windows.Forms.NumericUpDown>控件由其<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="97fdc-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="97fdc-104">你可以编写控件的值的条件测试，即可按与任何其他属性一样。</span><span class="sxs-lookup"><span data-stu-id="97fdc-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="97fdc-105">一次<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性设置，你可以直接通过编写代码来执行操作，调整它也可以调用<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>和<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="97fdc-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="97fdc-106">若要设置的数字值</span><span class="sxs-lookup"><span data-stu-id="97fdc-106">To set the numeric value</span></span>  
  
1.  <span data-ttu-id="97fdc-107">将值赋给<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性在代码中或在属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="97fdc-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="97fdc-108">-或-</span><span class="sxs-lookup"><span data-stu-id="97fdc-108">-or-</span></span>  
  
2.  <span data-ttu-id="97fdc-109">调用<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>或<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>方法来增加或减少值方法中指定的量<xref:System.Windows.Forms.NumericUpDown.Increment%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="97fdc-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="97fdc-110">若要返回的数值</span><span class="sxs-lookup"><span data-stu-id="97fdc-110">To return the numeric value</span></span>  
  
-   <span data-ttu-id="97fdc-111">访问<xref:System.Windows.Forms.NumericUpDown.Value%2A>在代码中的属性。</span><span class="sxs-lookup"><span data-stu-id="97fdc-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="97fdc-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="97fdc-112">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="97fdc-113">NumericUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="97fdc-113">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="97fdc-114">NumericUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="97fdc-114">NumericUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
