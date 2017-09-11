---
title: "限制访问器可访问性（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accesibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: 26
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
ms.openlocfilehash: 347fffa4f612c5cb674a6529e46c0b1785670c95
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="1cf08-102">限制访问器可访问性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1cf08-102">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="1cf08-103">属性或索引器的 [get](../../../csharp/language-reference/keywords/get.md) 和 [set](../../../csharp/language-reference/keywords/set.md) 部分称为访问器。</span><span class="sxs-lookup"><span data-stu-id="1cf08-103">The [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="1cf08-104">默认情况下，这些访问器具有相同的可见性或访问级别：其所属属性或索引器的可见性或访问级别。</span><span class="sxs-lookup"><span data-stu-id="1cf08-104">By default these accessors have the same visibility, or access level: that of the property or indexer to which they belong.</span></span> <span data-ttu-id="1cf08-105">有关详细信息，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf08-105">For more information, see [accessibility levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="1cf08-106">不过，有时限制对其中某个访问器的访问是有益的。</span><span class="sxs-lookup"><span data-stu-id="1cf08-106">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="1cf08-107">通常是在保持 `get` 访问器可公开访问的情况下，限制 `set` 访问器的可访问性。</span><span class="sxs-lookup"><span data-stu-id="1cf08-107">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="1cf08-108">例如: </span><span class="sxs-lookup"><span data-stu-id="1cf08-108">For example:</span></span>  
  
 <span data-ttu-id="1cf08-109">[!code-cs[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1cf08-109">[!code-cs[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]</span></span>  
  
 <span data-ttu-id="1cf08-110">在此示例中，名为 `Name` 的属性定义 `get` 访问器和 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="1cf08-110">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="1cf08-111">`get` 访问器接收该属性本身的可访问性级别（此示例中为 `public`），而对于 `set` 访问器，则通过对该访问器本身应用 [protected](../../../csharp/language-reference/keywords/protected.md) 访问修饰符来进行显式限制。</span><span class="sxs-lookup"><span data-stu-id="1cf08-111">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../../csharp/language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="1cf08-112">对访问器的访问修饰符的限制</span><span class="sxs-lookup"><span data-stu-id="1cf08-112">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="1cf08-113">对属性或索引器使用访问修饰符受以下条件的制约：</span><span class="sxs-lookup"><span data-stu-id="1cf08-113">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
-   <span data-ttu-id="1cf08-114">不能对接口或显式[接口](../../../csharp/language-reference/keywords/interface.md)成员实现使用访问器修饰符。</span><span class="sxs-lookup"><span data-stu-id="1cf08-114">You cannot use accessor modifiers on an interface or an explicit [interface](../../../csharp/language-reference/keywords/interface.md) member implementation.</span></span>  
  
-   <span data-ttu-id="1cf08-115">仅当属性或索引器同时具有 `set` 和 `get` 访问器时，才能使用访问器修饰符。</span><span class="sxs-lookup"><span data-stu-id="1cf08-115">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="1cf08-116">这种情况下，只允许对其中一个访问器使用修饰符。</span><span class="sxs-lookup"><span data-stu-id="1cf08-116">In this case, the modifier is permitted on one only of the two accessors.</span></span>  
  
-   <span data-ttu-id="1cf08-117">如果属性或索引器具有 [override](../../../csharp/language-reference/keywords/override.md) 修饰符，则访问器修饰符必须与重写的访问器的访问器（如有）匹配。</span><span class="sxs-lookup"><span data-stu-id="1cf08-117">If the property or indexer has an [override](../../../csharp/language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
-   <span data-ttu-id="1cf08-118">访问器的可访问性级别必须比属性或索引器本身的可访问性级别具有更严格的限制。</span><span class="sxs-lookup"><span data-stu-id="1cf08-118">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="1cf08-119">重写访问器的访问修饰符</span><span class="sxs-lookup"><span data-stu-id="1cf08-119">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="1cf08-120">重写属性或索引器时，被重写的访问器对重写代码而言必须是可访问的。</span><span class="sxs-lookup"><span data-stu-id="1cf08-120">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="1cf08-121">此外，属性/索引器和访问器的可访问性级别都必须与相应的被重写属性/索引器和访问器匹配。</span><span class="sxs-lookup"><span data-stu-id="1cf08-121">Also, the accessibility level of both the property/indexer, and that of the accessors must match the corresponding overridden property/indexer and the accessors.</span></span> <span data-ttu-id="1cf08-122">例如: </span><span class="sxs-lookup"><span data-stu-id="1cf08-122">For example:</span></span>  
  
 <span data-ttu-id="1cf08-123">[!code-cs[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1cf08-123">[!code-cs[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]</span></span>  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="1cf08-124">实现接口</span><span class="sxs-lookup"><span data-stu-id="1cf08-124">Implementing Interfaces</span></span>  
 <span data-ttu-id="1cf08-125">使用访问器实现接口时，访问器不一定有访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="1cf08-125">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="1cf08-126">但如果使用一个访问器（如 `get`）实现接口，则另一个访问器可以具有访问修饰符，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="1cf08-126">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 <span data-ttu-id="1cf08-127">[!code-cs[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1cf08-127">[!code-cs[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]</span></span>  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="1cf08-128">访问器可访问性域</span><span class="sxs-lookup"><span data-stu-id="1cf08-128">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="1cf08-129">如果对访问器使用访问修饰符，则访问器的[可访问性域](../../../csharp/language-reference/keywords/accessibility-domain.md)由该修饰符确定。</span><span class="sxs-lookup"><span data-stu-id="1cf08-129">If you use an access modifier on the accessor, the [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="1cf08-130">如果未对访问器使用访问修饰符，则访问器的可访问性域由属性或索引器的可访问性级别确定。</span><span class="sxs-lookup"><span data-stu-id="1cf08-130">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cf08-131">示例</span><span class="sxs-lookup"><span data-stu-id="1cf08-131">Example</span></span>  
 <span data-ttu-id="1cf08-132">下面的示例包含三个类：`BaseClass`、`DerivedClass` 和 `MainClass`。</span><span class="sxs-lookup"><span data-stu-id="1cf08-132">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="1cf08-133">每个类的 `BaseClass`、`Name` 和 `Id` 都有两个属性。</span><span class="sxs-lookup"><span data-stu-id="1cf08-133">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="1cf08-134">该示例演示在使用限制性访问修饰符（如 [protected](../../../csharp/language-reference/keywords/protected.md) 或 [private](../../../csharp/language-reference/keywords/private.md)）时，`BaseClass` 的 `Id` 属性如何隐藏 `DerivedClass` 的 `Id` 属性。</span><span class="sxs-lookup"><span data-stu-id="1cf08-134">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../../csharp/language-reference/keywords/protected.md) or [private](../../../csharp/language-reference/keywords/private.md).</span></span> <span data-ttu-id="1cf08-135">因此，向该属性赋值时将调用 `BaseClass` 类中的属性。</span><span class="sxs-lookup"><span data-stu-id="1cf08-135">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="1cf08-136">将访问修饰符替换为 [public](../../../csharp/language-reference/keywords/public.md) 将使该属性可供访问。</span><span class="sxs-lookup"><span data-stu-id="1cf08-136">Replacing the access modifier by [public](../../../csharp/language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="1cf08-137">该示例还演示 `DerivedClass` 中 `Name` 属性上 `set` 访问器的限制性访问修饰符（如 `private` 或 `protected`）如何防止对该访问器的访问，并在向它赋值时生成错误。</span><span class="sxs-lookup"><span data-stu-id="1cf08-137">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 <span data-ttu-id="1cf08-138">[!code-cs[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="1cf08-138">[!code-cs[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="1cf08-139">注释</span><span class="sxs-lookup"><span data-stu-id="1cf08-139">Comments</span></span>  
 <span data-ttu-id="1cf08-140">注意，如果将声明 `new private string Id` 替换为 `new public string Id`，则得到如下输出：</span><span class="sxs-lookup"><span data-stu-id="1cf08-140">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="1cf08-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cf08-141">See Also</span></span>  
 <span data-ttu-id="1cf08-142">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1cf08-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1cf08-143">[属性](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="1cf08-143">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="1cf08-144">[索引器](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="1cf08-144">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="1cf08-145">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="1cf08-145">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)

