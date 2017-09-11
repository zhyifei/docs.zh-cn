---
title: "while（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ed531c83dba02b38576bf8354b1ff92f075048bc
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="while-c-reference"></a><span data-ttu-id="23d99-102">while（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="23d99-102">while (C# Reference)</span></span>
<span data-ttu-id="23d99-103">`while` 语句执行一条语句或一个语句块，直到指定的表达式的计算结果为 `false` 为止。</span><span class="sxs-lookup"><span data-stu-id="23d99-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d99-104">示例</span><span class="sxs-lookup"><span data-stu-id="23d99-104">Example</span></span>  
 <span data-ttu-id="23d99-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="23d99-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d99-106">示例</span><span class="sxs-lookup"><span data-stu-id="23d99-106">Example</span></span>  
 <span data-ttu-id="23d99-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="23d99-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d99-108">示例</span><span class="sxs-lookup"><span data-stu-id="23d99-108">Example</span></span>  
 <span data-ttu-id="23d99-109">因为 `while` 表达式的测试在每次执行循环之前开始，所以 `while` 循环执行零次或多次。</span><span class="sxs-lookup"><span data-stu-id="23d99-109">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="23d99-110">这不同于 [do](../../../csharp/language-reference/keywords/do.md) 循环，该循环执行一次或多次。</span><span class="sxs-lookup"><span data-stu-id="23d99-110">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="23d99-111">[break](../../../csharp/language-reference/keywords/break.md)、[goto](../../../csharp/language-reference/keywords/goto.md)、[return](../../../csharp/language-reference/keywords/return.md) 或 [throw](../../../csharp/language-reference/keywords/throw.md) 语句将控制转移到循环外时，`while` 循环可能终止。</span><span class="sxs-lookup"><span data-stu-id="23d99-111">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="23d99-112">若要将控制传递到下一个迭代，而不退出循环，则使用 [continue](../../../csharp/language-reference/keywords/continue.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="23d99-112">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="23d99-113">注意前面三个示例的输出差异，具体取决于 `int n` 递增的位置。</span><span class="sxs-lookup"><span data-stu-id="23d99-113">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="23d99-114">在以下示例中，未生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="23d99-114">In the example below no output is generated.</span></span>  
  
 <span data-ttu-id="23d99-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="23d99-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="23d99-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="23d99-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="23d99-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="23d99-117">See Also</span></span>  
 <span data-ttu-id="23d99-118">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="23d99-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="23d99-119">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="23d99-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="23d99-120">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="23d99-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="23d99-121">[while Statement (C++)](/cpp/cpp/while-statement-cpp) （while 语句 (C++)）</span><span class="sxs-lookup"><span data-stu-id="23d99-121">[while Statement (C++)](/cpp/cpp/while-statement-cpp) </span></span>  
 [<span data-ttu-id="23d99-122">迭代语句</span><span class="sxs-lookup"><span data-stu-id="23d99-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

