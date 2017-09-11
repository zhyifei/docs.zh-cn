---
title: "属性和索引器之间的比较（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: 14
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
ms.openlocfilehash: 4bb2de1cfdcf4a8a7c847dfabe8d69124a4adf90
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="3827b-102">属性和索引器之间的比较（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3827b-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="3827b-103">索引器与属性相似。</span><span class="sxs-lookup"><span data-stu-id="3827b-103">Indexers are like properties.</span></span> <span data-ttu-id="3827b-104">除下表所示的差别外，对属性访问器定义的所有规则也适用于索引器访问器。</span><span class="sxs-lookup"><span data-stu-id="3827b-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="3827b-105">属性</span><span class="sxs-lookup"><span data-stu-id="3827b-105">Property</span></span>|<span data-ttu-id="3827b-106">索引器</span><span class="sxs-lookup"><span data-stu-id="3827b-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="3827b-107">允许以将方法视作公共数据成员的方式调用方法。</span><span class="sxs-lookup"><span data-stu-id="3827b-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="3827b-108">通过在对象自身上使用数组表示法，允许访问对象内部集合的元素。</span><span class="sxs-lookup"><span data-stu-id="3827b-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="3827b-109">通过简单名称访问。</span><span class="sxs-lookup"><span data-stu-id="3827b-109">Accessed through a simple name.</span></span>|<span data-ttu-id="3827b-110">通过索引访问。</span><span class="sxs-lookup"><span data-stu-id="3827b-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="3827b-111">可为静态成员或实例成员。</span><span class="sxs-lookup"><span data-stu-id="3827b-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="3827b-112">必须是实例成员。</span><span class="sxs-lookup"><span data-stu-id="3827b-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="3827b-113">属性的 [get](../../../csharp/language-reference/keywords/get.md) 访问器没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="3827b-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="3827b-114">索引器的 `get` 访问器具有与索引器相同的形参列表。</span><span class="sxs-lookup"><span data-stu-id="3827b-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="3827b-115">属性的 [set](../../../csharp/language-reference/keywords/set.md) 访问器包含隐式 `value` 参数。</span><span class="sxs-lookup"><span data-stu-id="3827b-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="3827b-116">索引器的 `set` 访问器具有与索引器相同的形参列表，[value](../../../csharp/language-reference/keywords/value.md) 参数也是如此。</span><span class="sxs-lookup"><span data-stu-id="3827b-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="3827b-117">通过[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)支持简短语法。</span><span class="sxs-lookup"><span data-stu-id="3827b-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="3827b-118">不支持简短语法。</span><span class="sxs-lookup"><span data-stu-id="3827b-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3827b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3827b-119">See Also</span></span>  
 <span data-ttu-id="3827b-120">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3827b-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3827b-121">[索引器](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="3827b-121">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="3827b-122">属性</span><span class="sxs-lookup"><span data-stu-id="3827b-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

