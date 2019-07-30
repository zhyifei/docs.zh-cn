---
title: 如何：声明对象变量, 并将对象分配给 Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 71949d50b01d7f252a988e86ca259261086d3b3b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630869"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="658e1-102">如何：声明对象变量, 并将对象分配给 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="658e1-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="658e1-103">通过在[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)中指定`As Object`来声明[对象数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)的变量。</span><span class="sxs-lookup"><span data-stu-id="658e1-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="658e1-104">通过在赋值语句或初始化子句中将对象放置在等号 (`=`) 之后, 可以将对象分配给此类变量。</span><span class="sxs-lookup"><span data-stu-id="658e1-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="658e1-105">示例</span><span class="sxs-lookup"><span data-stu-id="658e1-105">Example</span></span>

<span data-ttu-id="658e1-106">下面的示例声明一个`Object`变量, 并将当前的实例分配给它。</span><span class="sxs-lookup"><span data-stu-id="658e1-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="658e1-107">可以通过将变量初始化为其声明的一部分, 来合并声明和赋值。</span><span class="sxs-lookup"><span data-stu-id="658e1-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="658e1-108">下面的示例与前面的示例等效。</span><span class="sxs-lookup"><span data-stu-id="658e1-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a><span data-ttu-id="658e1-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="658e1-109">Compiling the Code</span></span>

<span data-ttu-id="658e1-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="658e1-110">This example requires:</span></span>

- <span data-ttu-id="658e1-111">对 <xref:System> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="658e1-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="658e1-112">要在其中放置语句的`Dim`类、结构或模块。</span><span class="sxs-lookup"><span data-stu-id="658e1-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="658e1-113">要在其中放置赋值语句的过程。</span><span class="sxs-lookup"><span data-stu-id="658e1-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="658e1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="658e1-114">See also</span></span>

- [<span data-ttu-id="658e1-115">变量声明</span><span class="sxs-lookup"><span data-stu-id="658e1-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="658e1-116">对象变量</span><span class="sxs-lookup"><span data-stu-id="658e1-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="658e1-117">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="658e1-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="658e1-118">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="658e1-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="658e1-119">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="658e1-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="658e1-120">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="658e1-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="658e1-121">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="658e1-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
