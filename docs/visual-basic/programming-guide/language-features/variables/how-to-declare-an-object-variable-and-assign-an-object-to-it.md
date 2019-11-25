---
title: 'How to: Declare an Object Variable and Assign an Object to It'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 4cfad1d820b584d4610d24c392b14ac3958471b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352909"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="fe189-102">如何：在 Visual Basic 中声明对象变量并为它分配对象</span><span class="sxs-lookup"><span data-stu-id="fe189-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="fe189-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fe189-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="fe189-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span><span class="sxs-lookup"><span data-stu-id="fe189-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="fe189-105">示例</span><span class="sxs-lookup"><span data-stu-id="fe189-105">Example</span></span>

<span data-ttu-id="fe189-106">The following example declares an `Object` variable and assigns the current instance to it.</span><span class="sxs-lookup"><span data-stu-id="fe189-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="fe189-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span><span class="sxs-lookup"><span data-stu-id="fe189-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="fe189-108">The following example is equivalent to the preceding example.</span><span class="sxs-lookup"><span data-stu-id="fe189-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a><span data-ttu-id="fe189-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="fe189-109">Compiling the Code</span></span>

<span data-ttu-id="fe189-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fe189-110">This example requires:</span></span>

- <span data-ttu-id="fe189-111">对 <xref:System> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="fe189-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="fe189-112">A class, structure, or module in which to put the `Dim` statement.</span><span class="sxs-lookup"><span data-stu-id="fe189-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="fe189-113">A procedure in which to put the assignment statement.</span><span class="sxs-lookup"><span data-stu-id="fe189-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe189-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe189-114">See also</span></span>

- [<span data-ttu-id="fe189-115">变量声明</span><span class="sxs-lookup"><span data-stu-id="fe189-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="fe189-116">对象变量</span><span class="sxs-lookup"><span data-stu-id="fe189-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="fe189-117">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="fe189-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="fe189-118">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe189-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="fe189-119">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="fe189-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="fe189-120">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="fe189-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="fe189-121">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="fe189-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
