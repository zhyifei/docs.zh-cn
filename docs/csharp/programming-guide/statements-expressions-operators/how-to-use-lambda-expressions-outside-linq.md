---
title: 如何：在 LINQ 外部使用 Lambda 表达式（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: eb9fea64b8aeb96a880b7e177673c1316b7aa4c1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261522"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="b5d14-102">如何：在 LINQ 外部使用 Lambda 表达式（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b5d14-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="b5d14-103">Lambda 表达式并不只限于在 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询中使用。</span><span class="sxs-lookup"><span data-stu-id="b5d14-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="b5d14-104">可以在需要委托值的任何地方（也就是在可以使用匿名方法的任何地方）使用这些表达式。</span><span class="sxs-lookup"><span data-stu-id="b5d14-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="b5d14-105">下面的示例演示如何在 Windows 窗体事件处理程序中使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="b5d14-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="b5d14-106">请注意，输入的类型（<xref:System.Object> 和 <xref:System.Windows.Forms.MouseEventArgs>）由编译器推理，因此不必在 lambda 输入参数中显式给定。</span><span class="sxs-lookup"><span data-stu-id="b5d14-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5d14-107">示例</span><span class="sxs-lookup"><span data-stu-id="b5d14-107">Example</span></span>  
  
```csharp  
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
  
## <a name="see-also"></a><span data-ttu-id="b5d14-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5d14-108">See Also</span></span>

- [<span data-ttu-id="b5d14-109">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="b5d14-109">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [<span data-ttu-id="b5d14-110">匿名方法</span><span class="sxs-lookup"><span data-stu-id="b5d14-110">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [<span data-ttu-id="b5d14-111">语言集成查询 (LINQ))</span><span class="sxs-lookup"><span data-stu-id="b5d14-111">Language Integrated Query (LINQ))</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
