---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 741374cc375e33868239161af23a38af7680b290
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684062"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="8495b-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8495b-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="8495b-103">指定的可读取但不是会写入变量或属性。</span><span class="sxs-lookup"><span data-stu-id="8495b-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8495b-104">备注</span><span class="sxs-lookup"><span data-stu-id="8495b-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8495b-105">规则</span><span class="sxs-lookup"><span data-stu-id="8495b-105">Rules</span></span>  
  
-   <span data-ttu-id="8495b-106">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="8495b-106">**Declaration Context.**</span></span> <span data-ttu-id="8495b-107">只能在模块级别使用 `ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="8495b-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="8495b-108">这意味着声明上下文`ReadOnly`元素必须是类、 结构或模块，并且不能是源文件、 命名空间或过程。</span><span class="sxs-lookup"><span data-stu-id="8495b-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="8495b-109">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="8495b-109">**Combined Modifiers.**</span></span> <span data-ttu-id="8495b-110">不能指定`ReadOnly`一起使用`Static`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="8495b-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="8495b-111">**分配一个值。**</span><span class="sxs-lookup"><span data-stu-id="8495b-111">**Assigning a Value.**</span></span> <span data-ttu-id="8495b-112">代码使用`ReadOnly`属性不能将其值设置。</span><span class="sxs-lookup"><span data-stu-id="8495b-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="8495b-113">但是，有权访问基础存储的代码可以分配或在任何时间更改的值。</span><span class="sxs-lookup"><span data-stu-id="8495b-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="8495b-114">可以将值赋给`ReadOnly`变量仅在其声明中或在类或结构在其中定义的构造函数中。</span><span class="sxs-lookup"><span data-stu-id="8495b-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="8495b-115">何时使用只读变量</span><span class="sxs-lookup"><span data-stu-id="8495b-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="8495b-116">在有些情况下，不能使用[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)来声明和分配常量值。</span><span class="sxs-lookup"><span data-stu-id="8495b-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="8495b-117">例如，`Const`语句可能不接受的数据类型，你想要分配，或您可能不能在编译时使用的常量表达式计算的值。</span><span class="sxs-lookup"><span data-stu-id="8495b-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="8495b-118">您可能甚至不知道值在编译时。</span><span class="sxs-lookup"><span data-stu-id="8495b-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="8495b-119">在这些情况下，你可以使用`ReadOnly`变量来保存常量值。</span><span class="sxs-lookup"><span data-stu-id="8495b-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8495b-120">即使变量本身是引用类型，如数组或类实例，该变量的数据类型是否可以更改其成员`ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="8495b-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="8495b-121">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="8495b-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="8495b-122">在初始化时，该数组由指向`characterArray()`包含"x"、"y"和"z"。</span><span class="sxs-lookup"><span data-stu-id="8495b-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="8495b-123">因为变量`characterArray`是`ReadOnly`，只要该函数将初始化; 即，不能更改其值，不能为其分配一个新数组。</span><span class="sxs-lookup"><span data-stu-id="8495b-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="8495b-124">但是，您可以更改一个或多个数组成员的值。</span><span class="sxs-lookup"><span data-stu-id="8495b-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="8495b-125">过程调用后面`changeArrayElement`，指向的数组`characterArray()`包含"x"、"M"和"z"。</span><span class="sxs-lookup"><span data-stu-id="8495b-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="8495b-126">请注意，这是类似于声明过程参数为[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)，这阻止过程调用参数本身进行更改，但允许它以更改其成员。</span><span class="sxs-lookup"><span data-stu-id="8495b-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8495b-127">示例</span><span class="sxs-lookup"><span data-stu-id="8495b-127">Example</span></span>  
 <span data-ttu-id="8495b-128">下面的示例定义`ReadOnly`雇佣员工的日期的属性。</span><span class="sxs-lookup"><span data-stu-id="8495b-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="8495b-129">类存储的属性值在内部作为`Private`变量，并且仅在类中的代码可以更改此值。</span><span class="sxs-lookup"><span data-stu-id="8495b-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="8495b-130">但是，该属性是`Public`，并可以访问的类的任何代码可以读取该属性。</span><span class="sxs-lookup"><span data-stu-id="8495b-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 <span data-ttu-id="8495b-131">`ReadOnly` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="8495b-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="8495b-132">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="8495b-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="8495b-133">Property 语句</span><span class="sxs-lookup"><span data-stu-id="8495b-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="8495b-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="8495b-134">See also</span></span>
- [<span data-ttu-id="8495b-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="8495b-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="8495b-136">关键字</span><span class="sxs-lookup"><span data-stu-id="8495b-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
