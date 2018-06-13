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
ms.locfileid: "33522264"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="353d2-102">如何：打印 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="353d2-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="353d2-103">作为开发过程的一部分，你通常将想要打印一份 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="353d2-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="353d2-104">下面的代码示例演示如何通过使用打印一份当前窗体<xref:System.Drawing.Graphics.CopyFromScreen%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="353d2-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="353d2-105">示例</span><span class="sxs-lookup"><span data-stu-id="353d2-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="353d2-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="353d2-106">Compiling the Code</span></span>  
 <span data-ttu-id="353d2-107">这是包含一个完整的代码示例`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="353d2-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="353d2-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="353d2-108">Robust Programming</span></span>  
 <span data-ttu-id="353d2-109">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="353d2-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="353d2-110">你没有访问打印机的权限。</span><span class="sxs-lookup"><span data-stu-id="353d2-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="353d2-111">没有安装打印机。</span><span class="sxs-lookup"><span data-stu-id="353d2-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="353d2-112">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="353d2-112">.NET Framework Security</span></span>  
 <span data-ttu-id="353d2-113">若要运行此代码示例，你必须有权访问你的计算机上使用的打印机。</span><span class="sxs-lookup"><span data-stu-id="353d2-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353d2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="353d2-114">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="353d2-115">如何：使用 GDI+ 呈现图像</span><span class="sxs-lookup"><span data-stu-id="353d2-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [<span data-ttu-id="353d2-116">如何：在 Windows 窗体中打印图形</span><span class="sxs-lookup"><span data-stu-id="353d2-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
