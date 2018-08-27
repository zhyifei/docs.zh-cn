---
title: Implements 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 805813506b957afb326c71ee4bbb15837726e4e5
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "42907991"
---
# <a name="implements-statement"></a><span data-ttu-id="b8627-102">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="b8627-102">Implements Statement</span></span>
<span data-ttu-id="b8627-103">指定一个或多个接口，或必须在类中实现的接口成员或结构定义中的出现。</span><span class="sxs-lookup"><span data-stu-id="b8627-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8627-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8627-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="b8627-105">部件</span><span class="sxs-lookup"><span data-stu-id="b8627-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="b8627-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="b8627-106">Required.</span></span> <span data-ttu-id="b8627-107">一个其属性、 过程和事件是由类或结构中的相应成员来实现的接口。</span><span class="sxs-lookup"><span data-stu-id="b8627-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="b8627-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="b8627-108">Required.</span></span> <span data-ttu-id="b8627-109">正在实现的接口的成员。</span><span class="sxs-lookup"><span data-stu-id="b8627-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8627-110">备注</span><span class="sxs-lookup"><span data-stu-id="b8627-110">Remarks</span></span>  
 <span data-ttu-id="b8627-111">接口是集合接口封装的原型表示的成员 （属性、 过程和事件）。</span><span class="sxs-lookup"><span data-stu-id="b8627-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="b8627-112">接口包含仅成员; 的声明类和结构实现这些成员。</span><span class="sxs-lookup"><span data-stu-id="b8627-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="b8627-113">有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b8627-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b8627-114">`Implements`语句必须紧跟`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="b8627-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="b8627-115">当实现接口时，必须实现该接口中声明的所有成员。</span><span class="sxs-lookup"><span data-stu-id="b8627-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="b8627-116">省略任何成员被视为是语法错误。</span><span class="sxs-lookup"><span data-stu-id="b8627-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="b8627-117">若要实现单个成员，则指定[实现](../../../visual-basic/language-reference/statements/implements-clause.md)关键字 (即独立于`Implements`语句) 中的类或结构的成员的声明时。</span><span class="sxs-lookup"><span data-stu-id="b8627-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="b8627-118">有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b8627-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b8627-119">类可以使用[专用](../../../visual-basic/language-reference/modifiers/private.md)了仅通过强制转换到一个变量中的实现类实例声明为接口的类型的可访问的属性和过程，但这些成员实现。</span><span class="sxs-lookup"><span data-stu-id="b8627-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8627-120">示例</span><span class="sxs-lookup"><span data-stu-id="b8627-120">Example</span></span>  
 <span data-ttu-id="b8627-121">下面的示例演示如何使用`Implements`语句来实现的接口成员。</span><span class="sxs-lookup"><span data-stu-id="b8627-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="b8627-122">它定义一个接口，名为`ICustomerInfo`与事件、 属性和过程。</span><span class="sxs-lookup"><span data-stu-id="b8627-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="b8627-123">类`customerInfo`实现在接口中定义的所有成员。</span><span class="sxs-lookup"><span data-stu-id="b8627-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="b8627-124">请注意，该类`customerInfo`使用`Implements`单独的源文件的代码行以指示该类实现的所有成员上的语句`ICustomerInfo`接口。</span><span class="sxs-lookup"><span data-stu-id="b8627-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="b8627-125">然后，在类中的每个成员使用`Implements`关键字作为其成员声明，以指示它实现该接口成员的一部分。</span><span class="sxs-lookup"><span data-stu-id="b8627-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8627-126">示例</span><span class="sxs-lookup"><span data-stu-id="b8627-126">Example</span></span>  
 <span data-ttu-id="b8627-127">以下两个过程演示如何使用在前面的示例实现的接口。</span><span class="sxs-lookup"><span data-stu-id="b8627-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="b8627-128">若要测试实现，请将这些过程添加到项目中并调用`testImplements`过程。</span><span class="sxs-lookup"><span data-stu-id="b8627-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b8627-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8627-129">See Also</span></span>  
 [<span data-ttu-id="b8627-130">Implements</span><span class="sxs-lookup"><span data-stu-id="b8627-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="b8627-131">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="b8627-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="b8627-132">接口</span><span class="sxs-lookup"><span data-stu-id="b8627-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
