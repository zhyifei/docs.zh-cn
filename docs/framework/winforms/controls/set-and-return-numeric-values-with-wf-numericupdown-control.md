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
ms.openlocfilehash: c73200eb1c373f1d723ba82f2e6be5b625496b59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300497"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="dadbf-102">如何：使用 Windows 窗体 NumericUpDown 控件设置和返回数值</span><span class="sxs-lookup"><span data-stu-id="dadbf-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="dadbf-103">Windows 窗体的数值<xref:System.Windows.Forms.NumericUpDown>控件由其<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dadbf-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="dadbf-104">就像使用任何其他属性一样，您可以编写控件的值的条件测试。</span><span class="sxs-lookup"><span data-stu-id="dadbf-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="dadbf-105">一次<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性设置，可以直接通过编写代码来执行操作，来调整它也可以调用<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>和<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="dadbf-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="dadbf-106">若要设置的数字值</span><span class="sxs-lookup"><span data-stu-id="dadbf-106">To set the numeric value</span></span>  
  
1. <span data-ttu-id="dadbf-107">将一个值赋给<xref:System.Windows.Forms.NumericUpDown.Value%2A>属性在代码中或在属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="dadbf-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="dadbf-108">或</span><span class="sxs-lookup"><span data-stu-id="dadbf-108">-or-</span></span>  
  
2. <span data-ttu-id="dadbf-109">调用<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>或<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>方法来增加或减少值中指定的数量<xref:System.Windows.Forms.NumericUpDown.Increment%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dadbf-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="dadbf-110">若要返回的数值</span><span class="sxs-lookup"><span data-stu-id="dadbf-110">To return the numeric value</span></span>  
  
-   <span data-ttu-id="dadbf-111">访问<xref:System.Windows.Forms.NumericUpDown.Value%2A>在代码中的属性。</span><span class="sxs-lookup"><span data-stu-id="dadbf-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dadbf-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="dadbf-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [<span data-ttu-id="dadbf-113">NumericUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="dadbf-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="dadbf-114">NumericUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="dadbf-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
