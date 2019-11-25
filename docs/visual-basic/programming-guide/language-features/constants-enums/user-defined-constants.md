---
title: 用户定义的常量
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 194a420b3749ca5c858a65c07b8c164287c1582a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354009"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="b93eb-102">用户定义的常量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b93eb-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="b93eb-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span><span class="sxs-lookup"><span data-stu-id="b93eb-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="b93eb-104">顾名思义，常量存储在应用程序的执行过程中保持不变的值。</span><span class="sxs-lookup"><span data-stu-id="b93eb-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="b93eb-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span><span class="sxs-lookup"><span data-stu-id="b93eb-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="b93eb-106">Constants you create yourself are described as *user-defined*.</span><span class="sxs-lookup"><span data-stu-id="b93eb-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="b93eb-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span><span class="sxs-lookup"><span data-stu-id="b93eb-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="b93eb-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span><span class="sxs-lookup"><span data-stu-id="b93eb-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="b93eb-109">Const Statement Usage</span><span class="sxs-lookup"><span data-stu-id="b93eb-109">Const Statement Usage</span></span>  
 <span data-ttu-id="b93eb-110">A `Const` statement can represent a mathematical or date/time quantity:</span><span class="sxs-lookup"><span data-stu-id="b93eb-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 <span data-ttu-id="b93eb-111">It also can define `String` constants:</span><span class="sxs-lookup"><span data-stu-id="b93eb-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 <span data-ttu-id="b93eb-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span><span class="sxs-lookup"><span data-stu-id="b93eb-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="b93eb-113">You can even define constants in terms of previously defined constants:</span><span class="sxs-lookup"><span data-stu-id="b93eb-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="b93eb-114">Scope of User-Defined Constants</span><span class="sxs-lookup"><span data-stu-id="b93eb-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="b93eb-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span><span class="sxs-lookup"><span data-stu-id="b93eb-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="b93eb-116">You can specify scope in any of the following ways:</span><span class="sxs-lookup"><span data-stu-id="b93eb-116">You can specify scope in any of the following ways:</span></span>  
  
- <span data-ttu-id="b93eb-117">To create a constant that exists only within a procedure, declare it within that procedure.</span><span class="sxs-lookup"><span data-stu-id="b93eb-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
- <span data-ttu-id="b93eb-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span><span class="sxs-lookup"><span data-stu-id="b93eb-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="b93eb-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span><span class="sxs-lookup"><span data-stu-id="b93eb-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="b93eb-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span><span class="sxs-lookup"><span data-stu-id="b93eb-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="b93eb-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="b93eb-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="b93eb-122">Avoiding Circular References</span><span class="sxs-lookup"><span data-stu-id="b93eb-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="b93eb-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span><span class="sxs-lookup"><span data-stu-id="b93eb-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="b93eb-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span><span class="sxs-lookup"><span data-stu-id="b93eb-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 <span data-ttu-id="b93eb-125">If a cycle occurs, Visual Basic generates a compiler error.</span><span class="sxs-lookup"><span data-stu-id="b93eb-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b93eb-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b93eb-126">See also</span></span>

- [<span data-ttu-id="b93eb-127">Const 语句</span><span class="sxs-lookup"><span data-stu-id="b93eb-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="b93eb-128">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="b93eb-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="b93eb-129">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="b93eb-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="b93eb-130">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="b93eb-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="b93eb-131">枚举概述</span><span class="sxs-lookup"><span data-stu-id="b93eb-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="b93eb-132">常量概述</span><span class="sxs-lookup"><span data-stu-id="b93eb-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="b93eb-133">How to: Declare an Enumeration</span><span class="sxs-lookup"><span data-stu-id="b93eb-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="b93eb-134">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="b93eb-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="b93eb-135">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="b93eb-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
