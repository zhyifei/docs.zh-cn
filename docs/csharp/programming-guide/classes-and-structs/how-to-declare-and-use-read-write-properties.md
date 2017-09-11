---
title: "如何：声明和使用读/写属性（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e5e4ca1feff203dc2ab88c0d1dfae8098508fec7
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="df882-102">如何：声明和使用读/写属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="df882-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="df882-103">属性提供了公共数据成员的便利性，且不会产生未受保护、不可控制和未经验证地访问对象的数据的风险。</span><span class="sxs-lookup"><span data-stu-id="df882-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="df882-104">这通过访问器实现：从基础数据成员中赋值和检索值的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="df882-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="df882-105">[set](../../../csharp/language-reference/keywords/set.md) 访问器可分配数据成员，[get](../../../csharp/language-reference/keywords/get.md) 访问器检索数据成员值。</span><span class="sxs-lookup"><span data-stu-id="df882-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="df882-106">此示例演示具有两个属性的 `Person` 类：`Name`（字符串）和 `Age`（整型）。</span><span class="sxs-lookup"><span data-stu-id="df882-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="df882-107">这两个属性均提供 `get` 和 `set` 访问器，因此它们被视为读/写属性。</span><span class="sxs-lookup"><span data-stu-id="df882-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df882-108">示例</span><span class="sxs-lookup"><span data-stu-id="df882-108">Example</span></span>  
 <span data-ttu-id="df882-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="df882-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="df882-110">可靠编程</span><span class="sxs-lookup"><span data-stu-id="df882-110">Robust Programming</span></span>  
 <span data-ttu-id="df882-111">在前面的示例中，`Name` 和 `Age` 属性为 [public](../../../csharp/language-reference/keywords/public.md)，同时包含 `get` 和 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="df882-111">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="df882-112">这使得任何对象均可读取和写入这些属性。</span><span class="sxs-lookup"><span data-stu-id="df882-112">This allows any object to read and write these properties.</span></span> <span data-ttu-id="df882-113">但是，有时需要排除其中的一个访问器。</span><span class="sxs-lookup"><span data-stu-id="df882-113">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="df882-114">例如，省略 `set` 访问器可使属性为只读：</span><span class="sxs-lookup"><span data-stu-id="df882-114">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 <span data-ttu-id="df882-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="df882-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="df882-116">或者，可以公开一个访问器，但使另一个访问器为私有或受保护。</span><span class="sxs-lookup"><span data-stu-id="df882-116">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="df882-117">有关详细信息，请参阅[非对称性访问器可访问性](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)。</span><span class="sxs-lookup"><span data-stu-id="df882-117">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="df882-118">声明属性后，便可使用这些属性，就像它们是类的字段一样。</span><span class="sxs-lookup"><span data-stu-id="df882-118">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="df882-119">在获取和设置属性的值时，这允许一种非常自然的语法，如以下语句所示：</span><span class="sxs-lookup"><span data-stu-id="df882-119">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 <span data-ttu-id="df882-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="df882-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span></span>  
  
 <span data-ttu-id="df882-121">请注意，在属性 `set` 方法中，特殊的 `value` 变量为可用。</span><span class="sxs-lookup"><span data-stu-id="df882-121">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="df882-122">此变量包含用户指定的值，例如：</span><span class="sxs-lookup"><span data-stu-id="df882-122">This variable contains the value that the user specified, for example:</span></span>  
  
 <span data-ttu-id="df882-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="df882-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span></span>  
  
 <span data-ttu-id="df882-124">请注意在 `Person` 对象上递增 `Age` 属性的简洁语法：</span><span class="sxs-lookup"><span data-stu-id="df882-124">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 <span data-ttu-id="df882-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="df882-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span></span>  
  
 <span data-ttu-id="df882-126">如果将单独的 `set` 和 `get` 方法用于模型属性，则等效的代码可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="df882-126">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="df882-127">`ToString` 方法在此示例中被重写：</span><span class="sxs-lookup"><span data-stu-id="df882-127">The `ToString` method is overridden in this example:</span></span>  
  
 <span data-ttu-id="df882-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="df882-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span></span>  
  
 <span data-ttu-id="df882-129">请注意，`ToString` 未显式用于程序中。</span><span class="sxs-lookup"><span data-stu-id="df882-129">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="df882-130">默认情况下，通过 `WriteLine` 调用对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="df882-130">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df882-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df882-131">See Also</span></span>  
 <span data-ttu-id="df882-132">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="df882-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="df882-133">[属性](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="df882-133">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="df882-134">类和结构</span><span class="sxs-lookup"><span data-stu-id="df882-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

