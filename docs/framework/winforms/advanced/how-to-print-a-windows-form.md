---
title: 如何：打印 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 42940654a0754ac3616ca7983af07d20607f480f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-print-a-windows-form"></a>如何：打印 Windows 窗体
作为开发过程的一部分，你通常将想要打印一份 Windows 窗体。 下面的代码示例演示如何通过使用打印一份当前窗体<xref:System.Drawing.Graphics.CopyFromScreen%2A>方法。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 这是包含一个完整的代码示例`Main`方法。  
  
## <a name="robust-programming"></a>可靠编程  
 以下情况可能会导致异常：  
  
-   你没有访问打印机的权限。  
  
-   没有安装打印机。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 若要运行此代码示例，你必须有权访问你的计算机上使用的打印机。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Printing.PrintDocument>  
 [如何：使用 GDI+ 呈现图像](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [如何：在 Windows 窗体中打印图形](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
