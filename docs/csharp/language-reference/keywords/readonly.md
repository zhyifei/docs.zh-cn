---
title: "readonly（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords: readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b499f9fc5121afe6c2e92bcf8c5d2ac593b4c06c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-c-reference"></a><span data-ttu-id="99a4f-102">readonly（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="99a4f-102">readonly (C# Reference)</span></span>
<span data-ttu-id="99a4f-103">`readonly` 关键字是一个可在字段上使用的修饰符。</span><span class="sxs-lookup"><span data-stu-id="99a4f-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="99a4f-104">当字段声明包括 `readonly` 修饰符时，该声明引入的字段赋值只能作为声明的一部分出现，或者出现在同一类的构造函数中。</span><span class="sxs-lookup"><span data-stu-id="99a4f-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99a4f-105">示例</span><span class="sxs-lookup"><span data-stu-id="99a4f-105">Example</span></span>  
 <span data-ttu-id="99a4f-106">在此示例中，即使在类构造函数中给字段 `year` 赋了值，它的值仍无法在 `ChangeYear` 方法中更改：</span><span class="sxs-lookup"><span data-stu-id="99a4f-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="99a4f-107">只能在下列上下文中对 `readonly` 字段进行赋值：</span><span class="sxs-lookup"><span data-stu-id="99a4f-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="99a4f-108">在声明中初始化变量时，例如：</span><span class="sxs-lookup"><span data-stu-id="99a4f-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="99a4f-109">对于实例字段，在包含字段声明的类的实例构造函数中；或者，对于静态字段，在包含字段声明的类的静态构造函数中。</span><span class="sxs-lookup"><span data-stu-id="99a4f-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="99a4f-110">也只有在这些上下文中，将 `readonly` 字段作为 [out](../../../csharp/language-reference/keywords/out.md) 或 [ref](../../../csharp/language-reference/keywords/ref.md) 参数传递才有效。</span><span class="sxs-lookup"><span data-stu-id="99a4f-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99a4f-111">`readonly` 关键字不同于 [const](../../../csharp/language-reference/keywords/const.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="99a4f-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="99a4f-112">`const` 字段只能在该字段的声明中初始化。</span><span class="sxs-lookup"><span data-stu-id="99a4f-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="99a4f-113">
          
          
          `readonly` 字段可以在声明或构造函数中初始化。</span><span class="sxs-lookup"><span data-stu-id="99a4f-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="99a4f-114">因此，根据所使用的构造函数，`readonly` 字段可能具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="99a4f-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="99a4f-115">另外，虽然 `const` 字段是编译时常量，但 `readonly` 字段可用于运行时常量，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="99a4f-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="99a4f-116">示例</span><span class="sxs-lookup"><span data-stu-id="99a4f-116">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="99a4f-117">在前面的示例中，如果使用如下的语句：</span><span class="sxs-lookup"><span data-stu-id="99a4f-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="99a4f-118">将收到编译器错误消息：</span><span class="sxs-lookup"><span data-stu-id="99a4f-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="99a4f-119">这与尝试给常数赋值时收到的错误相同。</span><span class="sxs-lookup"><span data-stu-id="99a4f-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="99a4f-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="99a4f-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99a4f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99a4f-121">See Also</span></span>  
 [<span data-ttu-id="99a4f-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="99a4f-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="99a4f-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="99a4f-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="99a4f-124">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="99a4f-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="99a4f-125">修饰符</span><span class="sxs-lookup"><span data-stu-id="99a4f-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="99a4f-126">const</span><span class="sxs-lookup"><span data-stu-id="99a4f-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="99a4f-127">字段</span><span class="sxs-lookup"><span data-stu-id="99a4f-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
