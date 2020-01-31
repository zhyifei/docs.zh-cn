---
title: 如何：打印图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 2435b3bc14747a00d2a0fc03a9ebd21ae43c5369
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740641"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>如何：在 Windows 窗体中打印图形
通常，您需要在基于 Windows 的应用程序中打印图形。 <xref:System.Drawing.Graphics> 类提供将对象绘制到设备（如屏幕或打印机）的方法。  
  
### <a name="to-print-graphics"></a>打印图形  
  
1. 将 <xref:System.Drawing.Printing.PrintDocument> 组件添加到窗体。  
  
2. 在 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件处理程序中，使用 <xref:System.Drawing.Printing.PrintPageEventArgs> 类的 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 属性指示打印机要打印的图形类型。  
  
     下面的代码示例演示了一个事件处理程序，用于在边框内创建蓝色椭圆。 该矩形具有以下位置和维度：从100开始150，宽度为250，高度为250。  
  
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
  
     （视觉C#对象和C++视觉对象）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Windows 窗体打印支持](windows-forms-print-support.md)
