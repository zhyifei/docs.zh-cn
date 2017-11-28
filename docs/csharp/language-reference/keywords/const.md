---
title: "const（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords: const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f54b686b170622ca1ead736a9f614c9bbef52dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="const-c-reference"></a><span data-ttu-id="72436-102">const（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="72436-102">const (C# Reference)</span></span>
<span data-ttu-id="72436-103">使用 `const` 关键字来声明某个常量字段或常量局部变量。</span><span class="sxs-lookup"><span data-stu-id="72436-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="72436-104">常量字段和常量局部变量不是变量并且不能修改。</span><span class="sxs-lookup"><span data-stu-id="72436-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="72436-105">常量可以为数字、布尔值、字符串或 null 引用。</span><span class="sxs-lookup"><span data-stu-id="72436-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="72436-106">不要创建常量来表示你需要随时更改的信息。</span><span class="sxs-lookup"><span data-stu-id="72436-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="72436-107">例如，不要使用常量字段来存储服务的价格、产品版本号或公司的品牌名称。</span><span class="sxs-lookup"><span data-stu-id="72436-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="72436-108">这些值会随着时间发生变化；因为编译器会传播常量，所以必须重新编译通过库编译的其他代码以查看更改。</span><span class="sxs-lookup"><span data-stu-id="72436-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="72436-109">另请参阅 [readonly](../../../csharp/language-reference/keywords/readonly.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="72436-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="72436-110">例如：</span><span class="sxs-lookup"><span data-stu-id="72436-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="72436-111">备注</span><span class="sxs-lookup"><span data-stu-id="72436-111">Remarks</span></span>  
 <span data-ttu-id="72436-112">常数声明的类型指定声明引入的成员类型。</span><span class="sxs-lookup"><span data-stu-id="72436-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="72436-113">常量局部变量或常量字段的初始值设定项必须是一个可以隐式转换为目标类型的常量表达式。</span><span class="sxs-lookup"><span data-stu-id="72436-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="72436-114">常数表达式是在编译时可被完全计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="72436-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="72436-115">因此，对于引用类型的常数，可能的值只能是 `string` 和 null 引用。</span><span class="sxs-lookup"><span data-stu-id="72436-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="72436-116">常数声明可以声明多个常数，例如：</span><span class="sxs-lookup"><span data-stu-id="72436-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="72436-117">不允许在常数声明中使用 `static` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="72436-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="72436-118">常数可以参与常数表达式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="72436-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="72436-119">[readonly](../../../csharp/language-reference/keywords/readonly.md) 关键字与 `const` 关键字不同。</span><span class="sxs-lookup"><span data-stu-id="72436-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="72436-120">
          
          
          `const` 字段只能在该字段的声明中初始化。</span><span class="sxs-lookup"><span data-stu-id="72436-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="72436-121">
          
          
          `readonly` 字段可以在声明或构造函数中初始化。</span><span class="sxs-lookup"><span data-stu-id="72436-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="72436-122">因此，根据所使用的构造函数，`readonly` 字段可能具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="72436-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="72436-123">另外，虽然 `const` 字段是编译时常量，但 `readonly` 字段可用于运行时常量，如此行所示：`public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="72436-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="72436-124">示例</span><span class="sxs-lookup"><span data-stu-id="72436-124">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="72436-125">示例</span><span class="sxs-lookup"><span data-stu-id="72436-125">Example</span></span>  
 <span data-ttu-id="72436-126">此示例说明如何将常数用作局部变量。</span><span class="sxs-lookup"><span data-stu-id="72436-126">This example demonstrates how to use constants as local variables.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="72436-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="72436-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72436-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72436-128">See Also</span></span>  
 [<span data-ttu-id="72436-129">C# 参考</span><span class="sxs-lookup"><span data-stu-id="72436-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="72436-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="72436-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="72436-131">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="72436-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="72436-132">修饰符</span><span class="sxs-lookup"><span data-stu-id="72436-132">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="72436-133">只读</span><span class="sxs-lookup"><span data-stu-id="72436-133">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)
