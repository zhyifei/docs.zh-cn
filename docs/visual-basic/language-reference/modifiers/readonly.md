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
ms.openlocfilehash: 748c38835cec83cefe54535f90d40ec3a030e4f4
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250379"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="497b9-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="497b9-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="497b9-103">指定可以读取但不能写入变量或属性。</span><span class="sxs-lookup"><span data-stu-id="497b9-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="497b9-104">备注</span><span class="sxs-lookup"><span data-stu-id="497b9-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="497b9-105">规则</span><span class="sxs-lookup"><span data-stu-id="497b9-105">Rules</span></span>  
  
- <span data-ttu-id="497b9-106">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="497b9-106">**Declaration Context.**</span></span> <span data-ttu-id="497b9-107">只能在模块级别使用 `ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="497b9-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="497b9-108">这意味着 `ReadOnly` 元素的声明上下文必须是类、结构或模块，不能是源文件、命名空间或过程。</span><span class="sxs-lookup"><span data-stu-id="497b9-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="497b9-109">**组合修饰符。**</span><span class="sxs-lookup"><span data-stu-id="497b9-109">**Combined Modifiers.**</span></span> <span data-ttu-id="497b9-110">不能在同一声明中同时指定 `ReadOnly` 和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="497b9-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="497b9-111">**赋值。**</span><span class="sxs-lookup"><span data-stu-id="497b9-111">**Assigning a Value.**</span></span> <span data-ttu-id="497b9-112">使用 `ReadOnly` 属性的代码不能设置其值。</span><span class="sxs-lookup"><span data-stu-id="497b9-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="497b9-113">但有权访问基础存储的代码可以随时分配或更改值。</span><span class="sxs-lookup"><span data-stu-id="497b9-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="497b9-114">只能在其声明中或在定义它的类或结构的构造函数中为 @no__t 0 变量赋值。</span><span class="sxs-lookup"><span data-stu-id="497b9-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="497b9-115">何时使用 ReadOnly 变量</span><span class="sxs-lookup"><span data-stu-id="497b9-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="497b9-116">在某些情况下，不能使用[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)来声明和分配常量值。</span><span class="sxs-lookup"><span data-stu-id="497b9-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="497b9-117">例如，`Const` 语句可能不接受您要分配的数据类型，或者您可能无法在编译时使用常量表达式来计算值。</span><span class="sxs-lookup"><span data-stu-id="497b9-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="497b9-118">在编译时，您甚至不知道值。</span><span class="sxs-lookup"><span data-stu-id="497b9-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="497b9-119">在这些情况下，可以使用 `ReadOnly` 变量来保存常量值。</span><span class="sxs-lookup"><span data-stu-id="497b9-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="497b9-120">如果该变量的数据类型是引用类型（如数组或类实例），则即使该变量本身 @no__t 为0，也可以更改其成员。</span><span class="sxs-lookup"><span data-stu-id="497b9-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="497b9-121">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="497b9-121">The following example illustrates this.</span></span>  
  
 ```vb
 ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
 Sub ChangeArrayElement()
     characterArray(1) = "M"c
 End Sub
 ```
  
 <span data-ttu-id="497b9-122">初始化后，@no__t 为的数组包含 "x"、"y" 和 "z"。</span><span class="sxs-lookup"><span data-stu-id="497b9-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="497b9-123">由于变量 `characterArray` @no__t 为-1，因此在初始化后，不能更改其值;也就是说，不能向其分配新数组。</span><span class="sxs-lookup"><span data-stu-id="497b9-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="497b9-124">但是，您可以更改一个或多个数组成员的值。</span><span class="sxs-lookup"><span data-stu-id="497b9-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="497b9-125">调用过程后 `ChangeArrayElement`，`characterArray()` 指向的数组包含 "x"、"M" 和 "z"。</span><span class="sxs-lookup"><span data-stu-id="497b9-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>
  
 <span data-ttu-id="497b9-126">请注意，这类似于将过程参数声明为[ByVal](byval.md)，这会阻止过程更改调用自变量本身，但允许该过程更改其成员。</span><span class="sxs-lookup"><span data-stu-id="497b9-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="497b9-127">示例</span><span class="sxs-lookup"><span data-stu-id="497b9-127">Example</span></span>

<span data-ttu-id="497b9-128">下面的示例为雇用员工的日期定义 `ReadOnly` 属性。</span><span class="sxs-lookup"><span data-stu-id="497b9-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="497b9-129">类将属性值作为 `Private` 变量在内部存储，并且只有类中的代码可以更改该值。</span><span class="sxs-lookup"><span data-stu-id="497b9-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="497b9-130">但是，属性为 `Public`，任何可访问类的代码都可以读取属性。</span><span class="sxs-lookup"><span data-stu-id="497b9-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>
  
[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]
  
<span data-ttu-id="497b9-131">`ReadOnly` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="497b9-131">The `ReadOnly` modifier can be used in these contexts:</span></span>
  
- [<span data-ttu-id="497b9-132">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="497b9-132">Dim Statement</span></span>](../statements/dim-statement.md) 
- [<span data-ttu-id="497b9-133">Property 语句</span><span class="sxs-lookup"><span data-stu-id="497b9-133">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="497b9-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="497b9-134">See also</span></span>

- [<span data-ttu-id="497b9-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="497b9-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="497b9-136">关键字</span><span class="sxs-lookup"><span data-stu-id="497b9-136">Keywords</span></span>](../keywords/index.md)
