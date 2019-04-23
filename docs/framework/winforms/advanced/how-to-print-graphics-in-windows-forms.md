---
title: 如何：在 Windows 窗体中打印图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 55459482d0994c581164128b17c08a7ca90d0717
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339094"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="0916a-102">如何：在 Windows 窗体中打印图形</span><span class="sxs-lookup"><span data-stu-id="0916a-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="0916a-103">通常情况下，想要在基于 Windows 的应用程序中打印图形。</span><span class="sxs-lookup"><span data-stu-id="0916a-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="0916a-104"><xref:System.Drawing.Graphics>类提供了对象绘制到设备，如屏幕或打印机的方法。</span><span class="sxs-lookup"><span data-stu-id="0916a-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="0916a-105">若要打印图形</span><span class="sxs-lookup"><span data-stu-id="0916a-105">To print graphics</span></span>  
  
1. <span data-ttu-id="0916a-106">添加<xref:System.Drawing.Printing.PrintDocument>向窗体组件。</span><span class="sxs-lookup"><span data-stu-id="0916a-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="0916a-107">在中<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件处理程序，使用<xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>属性的<xref:System.Drawing.Printing.PrintPageEventArgs>类，以指示要打印的图形类型上的打印机。</span><span class="sxs-lookup"><span data-stu-id="0916a-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="0916a-108">下面的代码示例显示了用于创建一个蓝色的椭圆的边框内的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0916a-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="0916a-109">矩形具有的以下位置和尺寸： 开始为 100，150 具有 250 的宽度和高度为 250。</span><span class="sxs-lookup"><span data-stu-id="0916a-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     <span data-ttu-id="0916a-110">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0916a-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0916a-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0916a-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="0916a-112">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="0916a-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
