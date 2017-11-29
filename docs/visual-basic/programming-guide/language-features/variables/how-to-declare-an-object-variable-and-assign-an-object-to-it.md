---
title: "如何：在 Visual Basic 中声明对象变量并为它分配对象"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4a682c7ae32ace0b1f859d52963342546a83f29
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="256c3-102">如何：在 Visual Basic 中声明对象变量并为它分配对象</span><span class="sxs-lookup"><span data-stu-id="256c3-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="256c3-103">声明的变量[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)通过指定`As Object`中[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="256c3-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="256c3-104">通过将对象放在等号后的对象分配给此类变量 (`=`) 在赋值语句或初始化子句中。</span><span class="sxs-lookup"><span data-stu-id="256c3-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="256c3-105">示例</span><span class="sxs-lookup"><span data-stu-id="256c3-105">Example</span></span>  
 <span data-ttu-id="256c3-106">下面的示例声明`Object`变量，并将分配到它的当前实例。</span><span class="sxs-lookup"><span data-stu-id="256c3-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="256c3-107">你可以通过将变量初始化为其声明的一部分组合的声明和分配。</span><span class="sxs-lookup"><span data-stu-id="256c3-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="256c3-108">下面的示例是等效于前面的示例。</span><span class="sxs-lookup"><span data-stu-id="256c3-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="256c3-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="256c3-109">Compiling the Code</span></span>  
 <span data-ttu-id="256c3-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="256c3-110">This example requires:</span></span>  
  
-   <span data-ttu-id="256c3-111">对 <xref:System> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="256c3-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="256c3-112">类、 结构或在其中放入的模块`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="256c3-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="256c3-113">在其中放入赋值语句过程。</span><span class="sxs-lookup"><span data-stu-id="256c3-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="256c3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="256c3-114">See Also</span></span>  
 [<span data-ttu-id="256c3-115">变量声明</span><span class="sxs-lookup"><span data-stu-id="256c3-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="256c3-116">对象变量</span><span class="sxs-lookup"><span data-stu-id="256c3-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="256c3-117">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="256c3-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="256c3-118">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="256c3-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="256c3-119">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="256c3-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="256c3-120">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="256c3-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="256c3-121">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="256c3-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
