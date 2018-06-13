---
title: 如何：在 LINQ 外部使用 Lambda 表达式（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: a7b7d25adab7ce1fc777b3bdbe581666ab952413
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328950"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="e6ff8-102">如何：在 LINQ 外部使用 Lambda 表达式（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e6ff8-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="e6ff8-103">Lambda 表达式并不只限于在 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询中使用。</span><span class="sxs-lookup"><span data-stu-id="e6ff8-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="e6ff8-104">可以在需要委托值的任何地方（也就是在可以使用匿名方法的任何地方）使用这些表达式。</span><span class="sxs-lookup"><span data-stu-id="e6ff8-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="e6ff8-105">下面的示例演示如何在 Windows 窗体事件处理程序中使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="e6ff8-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="e6ff8-106">请注意，输入的类型（<xref:System.Object> 和 <xref:System.Windows.Forms.MouseEventArgs>）由编译器推理，因此不必在 lambda 输入参数中显式给定。</span><span class="sxs-lookup"><span data-stu-id="e6ff8-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6ff8-107">示例</span><span class="sxs-lookup"><span data-stu-id="e6ff8-107">Example</span></span>  
  
```  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6ff8-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6ff8-108">See Also</span></span>  
 [<span data-ttu-id="e6ff8-109">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="e6ff8-109">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [<span data-ttu-id="e6ff8-110">匿名方法</span><span class="sxs-lookup"><span data-stu-id="e6ff8-110">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [<span data-ttu-id="e6ff8-111">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="e6ff8-111">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
