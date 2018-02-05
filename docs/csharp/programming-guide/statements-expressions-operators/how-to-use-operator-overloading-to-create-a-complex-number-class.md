---
title: "如何：使用运算符重载创建复数类（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e851b9d8a46f9cab73883a7b38761fed749c4f93
ms.sourcegitcommit: 22a48b64a0150a60b00b4fc4d8c62cde7f1670c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a><span data-ttu-id="bf4f8-102">如何：使用运算符重载创建复数类（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="bf4f8-102">How to: Use Operator Overloading to Create a Complex Number Class (C# Programming Guide)</span></span>
<span data-ttu-id="bf4f8-103">此示例演示如何使用运算符重载创建定义复数加法的复数类 `Complex`。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-103">This example shows how you can use operator overloading to create a complex number class `Complex` that defines complex addition.</span></span> <span data-ttu-id="bf4f8-104">该程序使用 `ToString` 方法替代来显示数字的虚部和实部以及加法结果。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-104">The program displays the imaginary and the real parts of the numbers and the addition result using an override of the `ToString` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf4f8-105">示例</span><span class="sxs-lookup"><span data-stu-id="bf4f8-105">Example</span></span>  
 [!code-csharp[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bf4f8-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf4f8-106">See Also</span></span>  
 [<span data-ttu-id="bf4f8-107">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bf4f8-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bf4f8-108">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="bf4f8-108">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="bf4f8-109">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bf4f8-109">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="bf4f8-110">重载运算符为何在 C# 中始终是静态的？</span><span class="sxs-lookup"><span data-stu-id="bf4f8-110">Why are overloaded operators always static in C#?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
