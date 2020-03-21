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
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182533"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>如何：在 Windows 窗体中打印图形
通常，您需要在基于 Windows 的应用程序中打印图形。 类<xref:System.Drawing.Graphics>提供将对象绘制到设备（如屏幕或打印机）的方法。  
  
### <a name="to-print-graphics"></a>打印图形  
  
1. 向表单<xref:System.Drawing.Printing.PrintDocument>添加组件。  
  
2. 在<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件处理程序中<xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>，使用<xref:System.Drawing.Printing.PrintPageEventArgs>类的属性指示打印机打印的图形类型。  
  
     下面的代码示例显示了用于在边界矩形内创建蓝色椭圆的事件处理程序。 矩形具有以下位置和尺寸：从 100 开始，150 开头，宽度为 250，高度为 250。  
  
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
  
     （视觉 C# 和视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
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
