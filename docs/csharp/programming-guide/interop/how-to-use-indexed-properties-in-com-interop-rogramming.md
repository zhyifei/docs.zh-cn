---
title: "如何：在 COM 互操作编程中使用索引属性（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
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
ms.openlocfilehash: 19e620415adefd6190d3896377eaf6a7cf944f28
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="fbd5c-102">如何：在 COM 互操作编程中使用索引属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fbd5c-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="fbd5c-103">索引属性改进了在 C# 编程中使用具有参数的 COM 属性的方式。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="fbd5c-104">结合使用索引属性与 Visual C# 中的其他功能（如[命名实参和可选实参](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)、一种新类型（[动态](../../../csharp/language-reference/keywords/dynamic.md)）以及[嵌入类型信息](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)）可以增强 Microsoft Office 编程。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="fbd5c-105">在早期版本的 C# 中，仅当 `get` 方法没有参数且 `set` 方法有且只有一个值参数时，方法才能作为属性访问。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="fbd5c-106">但是，并非所有 COM 属性都符合上述限制。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="fbd5c-107">例如，Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) 属性具有一个 `get` 访问器，它需要该范围名称的一个参数。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-107">For example, the Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="fbd5c-108">过去，由于无法直接访问 `Range` 属性，因此必须使用 `get_Range` 方法，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fbd5c-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd5c-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span></span>  
  
 <span data-ttu-id="fbd5c-110">利用索引属性，你可以改为编写以下代码：</span><span class="sxs-lookup"><span data-stu-id="fbd5c-110">Indexed properties enable you to write the following instead:</span></span>  
  
 <span data-ttu-id="fbd5c-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd5c-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbd5c-112">上一示例还使用了[可选实参](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)功能，以便忽略 `Type.Missing`。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-112">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="fbd5c-113">与在 Visual C# 2008 及更早版本中设置 [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) 对象的 `Value` 属性的值类似，需要两个参数。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-113">Similarly to set the value of the `Value` property of a [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="fbd5c-114">一个为指定范围值类型的可选参数提供实参。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-114">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="fbd5c-115">另一个提供 `Value` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-115">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="fbd5c-116">下面的示例说明了这些方法。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-116">The following examples illustrate these techniques.</span></span> <span data-ttu-id="fbd5c-117">两者都将 A1 单元格的值设置为 `Name`。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-117">Both set the value of the A1 cell to `Name`.</span></span>
  
 <span data-ttu-id="fbd5c-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd5c-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span></span>  
  
 <span data-ttu-id="fbd5c-119">利用索引属性，你可以改为编写以下代码。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-119">Indexed properties enable you to write the following code instead.</span></span>  
  
 <span data-ttu-id="fbd5c-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd5c-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span></span>  
  
 <span data-ttu-id="fbd5c-121">你不能创建自己的索引属性。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-121">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="fbd5c-122">该功能仅支持使用现有索引属性。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-122">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbd5c-123">示例</span><span class="sxs-lookup"><span data-stu-id="fbd5c-123">Example</span></span>  
 <span data-ttu-id="fbd5c-124">以下代码显示完整示例。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-124">The following code shows a complete example.</span></span> <span data-ttu-id="fbd5c-125">有关如何设置访问 Office API 的项目的详细信息，请参阅[如何：使用 Visual C# 功能访问 Office 互操作对象](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="fbd5c-125">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 <span data-ttu-id="fbd5c-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbd5c-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd5c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbd5c-127">See Also</span></span>  
 <span data-ttu-id="fbd5c-128">[已命名自变量和可选自变量](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="fbd5c-128">[Named and Optional Arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span></span>  
 <span data-ttu-id="fbd5c-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="fbd5c-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span></span>  
 <span data-ttu-id="fbd5c-130">[使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="fbd5c-130">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="fbd5c-131">[如何：在 Office 编程中使用命名实参和可选实参](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="fbd5c-131">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="fbd5c-132">[如何：使用 Visual C# 功能访问 Office 互操作对象](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fbd5c-132">[How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span></span>  
 [<span data-ttu-id="fbd5c-133">演练：Office 编程</span><span class="sxs-lookup"><span data-stu-id="fbd5c-133">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)

