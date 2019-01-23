---
title: Inherits 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 329b4f68874d29d141001800ed326a454a878ab8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502893"
---
# <a name="inherits-statement"></a><span data-ttu-id="706fd-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="706fd-102">Inherits Statement</span></span>
<span data-ttu-id="706fd-103">导致当前类或接口继承另一个类或接口集的属性、 变量、 属性、 过程和事件。</span><span class="sxs-lookup"><span data-stu-id="706fd-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="706fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="706fd-104">Syntax</span></span>  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="706fd-105">部件</span><span class="sxs-lookup"><span data-stu-id="706fd-105">Parts</span></span>  
  
|<span data-ttu-id="706fd-106">术语</span><span class="sxs-lookup"><span data-stu-id="706fd-106">Term</span></span>|<span data-ttu-id="706fd-107">定义</span><span class="sxs-lookup"><span data-stu-id="706fd-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="706fd-108">必需。</span><span class="sxs-lookup"><span data-stu-id="706fd-108">Required.</span></span> <span data-ttu-id="706fd-109">此类派生的类的名称。</span><span class="sxs-lookup"><span data-stu-id="706fd-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="706fd-110">或</span><span class="sxs-lookup"><span data-stu-id="706fd-110">-or-</span></span><br /><br /> <span data-ttu-id="706fd-111">此接口派生的接口的名称。</span><span class="sxs-lookup"><span data-stu-id="706fd-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="706fd-112">使用逗号分隔多个名称。</span><span class="sxs-lookup"><span data-stu-id="706fd-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="706fd-113">备注</span><span class="sxs-lookup"><span data-stu-id="706fd-113">Remarks</span></span>  
 <span data-ttu-id="706fd-114">如果使用，`Inherits`语句必须是类或接口定义中的第一个非空、 非注释行。</span><span class="sxs-lookup"><span data-stu-id="706fd-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="706fd-115">它应紧接`Class`或`Interface`语句。</span><span class="sxs-lookup"><span data-stu-id="706fd-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="706fd-116">可以使用`Inherits`只能在类或接口中。</span><span class="sxs-lookup"><span data-stu-id="706fd-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="706fd-117">这意味着继承的声明上下文不能是源文件、 命名空间、 结构、 模块、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="706fd-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="706fd-118">规则</span><span class="sxs-lookup"><span data-stu-id="706fd-118">Rules</span></span>  
  
-   <span data-ttu-id="706fd-119">**类继承。**</span><span class="sxs-lookup"><span data-stu-id="706fd-119">**Class Inheritance.**</span></span> <span data-ttu-id="706fd-120">如果类使用`Inherits`语句中，可以指定只有一个基类。</span><span class="sxs-lookup"><span data-stu-id="706fd-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="706fd-121">类不能从嵌套在它的类继承。</span><span class="sxs-lookup"><span data-stu-id="706fd-121">A class cannot inherit from a class nested within it.</span></span>  
  
-   <span data-ttu-id="706fd-122">**接口继承。**</span><span class="sxs-lookup"><span data-stu-id="706fd-122">**Interface Inheritance.**</span></span> <span data-ttu-id="706fd-123">如果接口使用`Inherits`语句，则可以指定一个或多个基接口。</span><span class="sxs-lookup"><span data-stu-id="706fd-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="706fd-124">您可以即使它们每个定义具有相同名称的成员，从两个接口继承。</span><span class="sxs-lookup"><span data-stu-id="706fd-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="706fd-125">如果这样做，实现代码必须使用名称限定来指定它正在实现的成员。</span><span class="sxs-lookup"><span data-stu-id="706fd-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="706fd-126">接口不能从具有限制性更强的访问级别的另一个接口继承。</span><span class="sxs-lookup"><span data-stu-id="706fd-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="706fd-127">例如，`Public`不能继承自接口`Friend`接口。</span><span class="sxs-lookup"><span data-stu-id="706fd-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="706fd-128">接口不能从嵌套在它的接口继承。</span><span class="sxs-lookup"><span data-stu-id="706fd-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="706fd-129">.NET Framework 中的类继承的一个示例是<xref:System.ArgumentException>类，该类继承自<xref:System.SystemException>类。</span><span class="sxs-lookup"><span data-stu-id="706fd-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="706fd-130">这提供了到<xref:System.ArgumentException>所有预定义的属性和所需的系统异常，如过程<xref:System.Exception.Message%2A>属性和<xref:System.Exception.ToString%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="706fd-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="706fd-131">.NET Framework 中的接口继承的一个示例是<xref:System.Collections.ICollection>接口，该类继承自<xref:System.Collections.IEnumerable>接口。</span><span class="sxs-lookup"><span data-stu-id="706fd-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="706fd-132">这将导致<xref:System.Collections.ICollection>继承需要遍历集合的枚举器的定义。</span><span class="sxs-lookup"><span data-stu-id="706fd-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="706fd-133">示例</span><span class="sxs-lookup"><span data-stu-id="706fd-133">Example</span></span>  
 <span data-ttu-id="706fd-134">下面的示例使用`Inherits`语句，以显示一个类的名为`thisClass`可继承的名为的基类的所有成员`anotherClass`。</span><span class="sxs-lookup"><span data-stu-id="706fd-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="706fd-135">示例</span><span class="sxs-lookup"><span data-stu-id="706fd-135">Example</span></span>  
 <span data-ttu-id="706fd-136">下面的示例显示了多个接口继承。</span><span class="sxs-lookup"><span data-stu-id="706fd-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 <span data-ttu-id="706fd-137">名为的接口`thisInterface`现在包括中的所有定义<xref:System.IComparable>， <xref:System.IDisposable>，和<xref:System.IFormattable>接口继承的成员分别提供有关特定于类型的比较的两个对象，释放分配的资源表示为对象的值和`String`。</span><span class="sxs-lookup"><span data-stu-id="706fd-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="706fd-138">实现的类`thisInterface`必须实现每个基接口的每个成员。</span><span class="sxs-lookup"><span data-stu-id="706fd-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="706fd-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="706fd-139">See also</span></span>
- [<span data-ttu-id="706fd-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="706fd-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="706fd-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="706fd-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="706fd-142">对象和类</span><span class="sxs-lookup"><span data-stu-id="706fd-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="706fd-143">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="706fd-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="706fd-144">接口</span><span class="sxs-lookup"><span data-stu-id="706fd-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
