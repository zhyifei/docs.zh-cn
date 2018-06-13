---
title: Implements 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 5afc7e4e3a03dfab1288e50e65e5076bdd438f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604206"
---
# <a name="implements-statement"></a><span data-ttu-id="a5116-102">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="a5116-102">Implements Statement</span></span>
<span data-ttu-id="a5116-103">指定一个或多个接口，或必须在类中实现的接口成员或它在其中出现的结构定义。</span><span class="sxs-lookup"><span data-stu-id="a5116-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5116-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5116-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="a5116-105">部件</span><span class="sxs-lookup"><span data-stu-id="a5116-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="a5116-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="a5116-106">Required.</span></span> <span data-ttu-id="a5116-107">其属性、 过程和事件都由相应成员中的类或结构实现接口。</span><span class="sxs-lookup"><span data-stu-id="a5116-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="a5116-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="a5116-108">Required.</span></span> <span data-ttu-id="a5116-109">正在实现的接口的成员。</span><span class="sxs-lookup"><span data-stu-id="a5116-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5116-110">备注</span><span class="sxs-lookup"><span data-stu-id="a5116-110">Remarks</span></span>  
 <span data-ttu-id="a5116-111">接口是集合接口封装的原型表示的成员 （属性、 过程和事件）。</span><span class="sxs-lookup"><span data-stu-id="a5116-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="a5116-112">接口包含仅成员; 的声明类和结构实现这些成员。</span><span class="sxs-lookup"><span data-stu-id="a5116-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="a5116-113">有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a5116-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="a5116-114">`Implements`语句必须紧跟`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="a5116-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="a5116-115">当实现接口时，则必须实现该接口中声明的所有成员。</span><span class="sxs-lookup"><span data-stu-id="a5116-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="a5116-116">省略任何成员被视为可语法错误。</span><span class="sxs-lookup"><span data-stu-id="a5116-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="a5116-117">若要实现的单个成员，你可以指定[实现](../../../visual-basic/language-reference/statements/implements-clause.md)关键字 (即独立于`Implements`语句) 声明中的类或结构的成员时。</span><span class="sxs-lookup"><span data-stu-id="a5116-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="a5116-118">有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a5116-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="a5116-119">类可以使用[私有](../../../visual-basic/language-reference/modifiers/private.md)了只能由强制转换到一个变量中实现的类的实例声明为接口类型的访问的属性和过程，但这些成员的实现。</span><span class="sxs-lookup"><span data-stu-id="a5116-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5116-120">示例</span><span class="sxs-lookup"><span data-stu-id="a5116-120">Example</span></span>  
 <span data-ttu-id="a5116-121">下面的示例演示如何使用`Implements`语句来实现接口成员。</span><span class="sxs-lookup"><span data-stu-id="a5116-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="a5116-122">它定义一个名为的接口`ICustomerInfo`事件、 属性和过程。</span><span class="sxs-lookup"><span data-stu-id="a5116-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="a5116-123">类`customerInfo`实现该接口中定义的所有成员。</span><span class="sxs-lookup"><span data-stu-id="a5116-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="a5116-124">请注意，类`customerInfo`使用`Implements`语句在单独的源的代码行以指示类实现的所有成员上`ICustomerInfo`接口。</span><span class="sxs-lookup"><span data-stu-id="a5116-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="a5116-125">然后，在类中的每个成员使用`Implements`关键字作为其成员声明，以指示，它可实现该接口成员的一部分。</span><span class="sxs-lookup"><span data-stu-id="a5116-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5116-126">示例</span><span class="sxs-lookup"><span data-stu-id="a5116-126">Example</span></span>  
 <span data-ttu-id="a5116-127">下面的两个过程演示如何使用在前面的示例实现的接口。</span><span class="sxs-lookup"><span data-stu-id="a5116-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="a5116-128">若要测试的实现，请将这些过程添加到项目中并调用`testImplements`过程。</span><span class="sxs-lookup"><span data-stu-id="a5116-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a5116-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5116-129">See Also</span></span>  
 [<span data-ttu-id="a5116-130">Implements</span><span class="sxs-lookup"><span data-stu-id="a5116-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="a5116-131">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="a5116-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="a5116-132">接口</span><span class="sxs-lookup"><span data-stu-id="a5116-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
