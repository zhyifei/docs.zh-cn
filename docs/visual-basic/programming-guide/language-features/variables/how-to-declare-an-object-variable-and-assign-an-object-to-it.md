---
title: 如何：声明对象变量并向其分配对象
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: eaaeda2a986584e6e1a2e0d2cda3890fb6187598
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344234"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="11c3b-102">如何：在 Visual Basic 中声明对象变量并为它分配对象</span><span class="sxs-lookup"><span data-stu-id="11c3b-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="11c3b-103">通过在[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)中指定 `As Object` 来声明[对象数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)的变量。</span><span class="sxs-lookup"><span data-stu-id="11c3b-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="11c3b-104">通过将对象置于赋值语句或初始化子句中的等号（`=`）之后，可以将对象分配给此类变量。</span><span class="sxs-lookup"><span data-stu-id="11c3b-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="11c3b-105">示例</span><span class="sxs-lookup"><span data-stu-id="11c3b-105">Example</span></span>

<span data-ttu-id="11c3b-106">下面的示例声明一个 `Object` 变量，并将当前的实例分配给它。</span><span class="sxs-lookup"><span data-stu-id="11c3b-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="11c3b-107">可以通过将变量初始化为其声明的一部分，来合并声明和赋值。</span><span class="sxs-lookup"><span data-stu-id="11c3b-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="11c3b-108">下面的示例与前面的示例等效。</span><span class="sxs-lookup"><span data-stu-id="11c3b-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="11c3b-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="11c3b-109">Compile the code</span></span>

<span data-ttu-id="11c3b-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="11c3b-110">This example requires:</span></span>

- <span data-ttu-id="11c3b-111">对 <xref:System> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="11c3b-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="11c3b-112">要放置 `Dim` 语句的类、结构或模块。</span><span class="sxs-lookup"><span data-stu-id="11c3b-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="11c3b-113">要在其中放置赋值语句的过程。</span><span class="sxs-lookup"><span data-stu-id="11c3b-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="11c3b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11c3b-114">See also</span></span>

- [<span data-ttu-id="11c3b-115">变量声明</span><span class="sxs-lookup"><span data-stu-id="11c3b-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="11c3b-116">对象变量</span><span class="sxs-lookup"><span data-stu-id="11c3b-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="11c3b-117">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="11c3b-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="11c3b-118">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="11c3b-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="11c3b-119">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="11c3b-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="11c3b-120">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="11c3b-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="11c3b-121">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="11c3b-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
