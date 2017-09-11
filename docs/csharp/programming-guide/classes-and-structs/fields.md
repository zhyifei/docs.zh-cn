---
title: "字段（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8eef9bb644a28c69a1db59dcba3c12c9e3fa86b0
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="fields-c-programming-guide"></a><span data-ttu-id="b1525-102">字段（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b1525-102">Fields (C# Programming Guide)</span></span>
<span data-ttu-id="b1525-103">字段是在[类](../../../csharp/language-reference/keywords/class.md)或[结构](../../../csharp/language-reference/keywords/struct.md)中直接声明的任意类型的变量。</span><span class="sxs-lookup"><span data-stu-id="b1525-103">A *field* is a variable of any type that is declared directly in a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md).</span></span> <span data-ttu-id="b1525-104">字段是其包含类型的成员。</span><span class="sxs-lookup"><span data-stu-id="b1525-104">Fields are *members* of their containing type.</span></span>  
  
 <span data-ttu-id="b1525-105">类或结构可能具有实例字段和/或静态字段。</span><span class="sxs-lookup"><span data-stu-id="b1525-105">A class or struct may have instance fields or static fields or both.</span></span> <span data-ttu-id="b1525-106">实例字段特定于类型的实例。</span><span class="sxs-lookup"><span data-stu-id="b1525-106">Instance fields are specific to an instance of a type.</span></span> <span data-ttu-id="b1525-107">如果你有包含实例字段 F 的类 T，则可以创建两个类型为 T 的对象并修改每个对象中 F 的值，而不会影响另一个对象中的值。</span><span class="sxs-lookup"><span data-stu-id="b1525-107">If you have a class T, with an instance field F, you can create two objects of type T, and modify the value of F in each object without affecting the value in the other object.</span></span> <span data-ttu-id="b1525-108">与此相比，静态字段属于类本身，并在该类的所有实例之间共享。</span><span class="sxs-lookup"><span data-stu-id="b1525-108">By contrast, a static field belongs to the class itself, and is shared among all instances of that class.</span></span> <span data-ttu-id="b1525-109">从实例 A 进行的更改将立刻呈现给实例 B 和 C（如果它们访问该字段）。</span><span class="sxs-lookup"><span data-stu-id="b1525-109">Changes made from instance A will be visibly immediately to instances B and C if they access the field.</span></span>  
  
 <span data-ttu-id="b1525-110">通常情况下，应仅对具有 private 或 protected 可访问性的变量使用字段。</span><span class="sxs-lookup"><span data-stu-id="b1525-110">Generally, you should use fields only for variables that have private or protected accessibility.</span></span> <span data-ttu-id="b1525-111">类向客户端代码公开的数据应通过[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)、[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)和[索引器](../../../csharp/programming-guide/indexers/index.md)提供。</span><span class="sxs-lookup"><span data-stu-id="b1525-111">Data that your class exposes to client code should be provided through [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) and [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="b1525-112">通过使用这些构造间接访问内部字段，可以防止出现无效的输入值。</span><span class="sxs-lookup"><span data-stu-id="b1525-112">By using these constructs for indirect access to internal fields, you can guard against invalid input values.</span></span> <span data-ttu-id="b1525-113">存储由公共属性公开的数据的私有字段称为后备存储或支持字段。</span><span class="sxs-lookup"><span data-stu-id="b1525-113">A private field that stores the data exposed by a public property is called a *backing store* or *backing field*.</span></span>  
  
 <span data-ttu-id="b1525-114">字段通常存储必须对多个类方法可访问且存储时间必须长于任何单个方法的生存期的数据。</span><span class="sxs-lookup"><span data-stu-id="b1525-114">Fields typically store the data that must be accessible to more than one class method and must be stored for longer than the lifetime of any single method.</span></span> <span data-ttu-id="b1525-115">例如，表示日历日期的类可能具有三个整数字段：一个用于月、一个用于日、一个用于年。</span><span class="sxs-lookup"><span data-stu-id="b1525-115">For example, a class that represents a calendar date might have three integer fields: one for the month, one for the day, and one for the year.</span></span> <span data-ttu-id="b1525-116">不在单个方法作用域外使用的变量应声明为方法主体本身中的局部变量。</span><span class="sxs-lookup"><span data-stu-id="b1525-116">Variables that are not used outside the scope of a single method should be declared as *local variables* within the method body itself.</span></span>  
  
 <span data-ttu-id="b1525-117">字段是通过指定该字段的访问级别在类块中声明的，其后跟字段的类型，再跟字段的名称。</span><span class="sxs-lookup"><span data-stu-id="b1525-117">Fields are declared in the class block by specifying the access level of the field, followed by the type of the field, followed by the name of the field.</span></span> <span data-ttu-id="b1525-118">例如: </span><span class="sxs-lookup"><span data-stu-id="b1525-118">For example:</span></span>  
  
 <span data-ttu-id="b1525-119">[!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b1525-119">[!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]</span></span>  
  
 <span data-ttu-id="b1525-120">若要访问对象中的字段，请在对象名称后添加一个句点，后跟字段的名称，如 `objectname.fieldname` 中所示。</span><span class="sxs-lookup"><span data-stu-id="b1525-120">To access a field in an object, add a period after the object name, followed by the name of the field, as in `objectname.fieldname`.</span></span> <span data-ttu-id="b1525-121">例如：</span><span class="sxs-lookup"><span data-stu-id="b1525-121">For example:</span></span>  
  
 <span data-ttu-id="b1525-122">[!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b1525-122">[!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]</span></span>  
  
 <span data-ttu-id="b1525-123">声明字段时，可以使用赋值运算符为字段指定一个初始值。</span><span class="sxs-lookup"><span data-stu-id="b1525-123">A field can be given an initial value by using the assignment operator when the field is declared.</span></span> <span data-ttu-id="b1525-124">例如，若要为 `day` 字段自动赋值 `"Monday"`，则需要声明 `day`，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="b1525-124">To automatically assign the `day` field to `"Monday"`, for example, you would declare `day` as in the following example:</span></span>  
  
 <span data-ttu-id="b1525-125">[!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b1525-125">[!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]</span></span>  
  
 <span data-ttu-id="b1525-126">字段会在对象实例的构造函数被调用之前即刻初始化。</span><span class="sxs-lookup"><span data-stu-id="b1525-126">Fields are initialized immediately before the constructor for the object instance is called.</span></span> <span data-ttu-id="b1525-127">如果构造函数分配了字段的值，则它将覆盖在字段声明期间给定的任何值。</span><span class="sxs-lookup"><span data-stu-id="b1525-127">If the constructor assigns the value of a field, it will overwrite any value given during field declaration.</span></span> <span data-ttu-id="b1525-128">有关详细信息，请参阅[使用构造函数](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="b1525-128">For more information, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1525-129">字段初始化表达式不能引用其他实例字段。</span><span class="sxs-lookup"><span data-stu-id="b1525-129">A field initializer cannot refer to other instance fields.</span></span>  
  
 <span data-ttu-id="b1525-130">可以将字段标记为 [public](../../../csharp/language-reference/keywords/public.md)、[private](../../../csharp/language-reference/keywords/private.md)、[protected](../../../csharp/language-reference/keywords/protected.md)、[internal](../../../csharp/language-reference/keywords/internal.md) 或 `protected internal`。</span><span class="sxs-lookup"><span data-stu-id="b1525-130">Fields can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="b1525-131">这些访问修饰符定义该类的用户访问该字段的方式。</span><span class="sxs-lookup"><span data-stu-id="b1525-131">These access modifiers define how users of the class can access the fields.</span></span> <span data-ttu-id="b1525-132">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="b1525-132">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="b1525-133">可以选择性地将字段声明为[静态](../../../csharp/language-reference/keywords/static.md)。</span><span class="sxs-lookup"><span data-stu-id="b1525-133">A field can optionally be declared [static](../../../csharp/language-reference/keywords/static.md).</span></span> <span data-ttu-id="b1525-134">这可使字段可供调用方在任何时候进行调用，即使不存在任何类的实例。</span><span class="sxs-lookup"><span data-stu-id="b1525-134">This makes the field available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="b1525-135">有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="b1525-135">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="b1525-136">可以将字段声明为[只读](../../../csharp/language-reference/keywords/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="b1525-136">A field can be declared [readonly](../../../csharp/language-reference/keywords/readonly.md).</span></span> <span data-ttu-id="b1525-137">只能在初始化期间或在构造函数中为只读字段赋值。</span><span class="sxs-lookup"><span data-stu-id="b1525-137">A read-only field can only be assigned a value during initialization or in a constructor.</span></span> <span data-ttu-id="b1525-138">`static``readonly` 字段非常类似于常量，只不过 C# 编译器在编译时不具有对静态只读字段的值的访问权限，而只有在运行时才具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="b1525-138">A `static``readonly` field is very similar to a constant, except that the C# compiler does not have access to the value of a static read-only field at compile time, only at run time.</span></span> <span data-ttu-id="b1525-139">有关详细信息，请参阅[常量](../../../csharp/programming-guide/classes-and-structs/constants.md)。</span><span class="sxs-lookup"><span data-stu-id="b1525-139">For more information, see [Constants](../../../csharp/programming-guide/classes-and-structs/constants.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b1525-140">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b1525-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1525-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1525-141">See Also</span></span>  
 <span data-ttu-id="b1525-142">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b1525-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b1525-143">[类和结构](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="b1525-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="b1525-144">[使用构造函数](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="b1525-144">[Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span></span>  
 <span data-ttu-id="b1525-145">[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="b1525-145">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="b1525-146">[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="b1525-146">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 [<span data-ttu-id="b1525-147">抽象类、密封类及类成员</span><span class="sxs-lookup"><span data-stu-id="b1525-147">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)

