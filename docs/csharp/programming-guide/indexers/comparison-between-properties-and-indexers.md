---
title: 属性和索引器之间的比较（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 3a78b97f2cac1f2c49be03bc351d9b6f4b6438e6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861437"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="373e0-102">属性和索引器之间的比较（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="373e0-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="373e0-103">索引器与属性相似。</span><span class="sxs-lookup"><span data-stu-id="373e0-103">Indexers are like properties.</span></span> <span data-ttu-id="373e0-104">除下表所示的差别外，对属性访问器定义的所有规则也适用于索引器访问器。</span><span class="sxs-lookup"><span data-stu-id="373e0-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="373e0-105">属性</span><span class="sxs-lookup"><span data-stu-id="373e0-105">Property</span></span>|<span data-ttu-id="373e0-106">索引器</span><span class="sxs-lookup"><span data-stu-id="373e0-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="373e0-107">允许以将方法视作公共数据成员的方式调用方法。</span><span class="sxs-lookup"><span data-stu-id="373e0-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="373e0-108">通过在对象自身上使用数组表示法，允许访问对象内部集合的元素。</span><span class="sxs-lookup"><span data-stu-id="373e0-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="373e0-109">通过简单名称访问。</span><span class="sxs-lookup"><span data-stu-id="373e0-109">Accessed through a simple name.</span></span>|<span data-ttu-id="373e0-110">通过索引访问。</span><span class="sxs-lookup"><span data-stu-id="373e0-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="373e0-111">可为静态成员或实例成员。</span><span class="sxs-lookup"><span data-stu-id="373e0-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="373e0-112">必须是实例成员。</span><span class="sxs-lookup"><span data-stu-id="373e0-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="373e0-113">属性的 [get](../../../csharp/language-reference/keywords/get.md) 访问器没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="373e0-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="373e0-114">索引器的 `get` 访问器具有与索引器相同的形参列表。</span><span class="sxs-lookup"><span data-stu-id="373e0-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="373e0-115">属性的 [set](../../../csharp/language-reference/keywords/set.md) 访问器包含隐式 `value` 参数。</span><span class="sxs-lookup"><span data-stu-id="373e0-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="373e0-116">索引器的 `set` 访问器具有与索引器相同的形参列表，[value](../../../csharp/language-reference/keywords/value.md) 参数也是如此。</span><span class="sxs-lookup"><span data-stu-id="373e0-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="373e0-117">通过[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)支持简短语法。</span><span class="sxs-lookup"><span data-stu-id="373e0-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="373e0-118">不支持简短语法。</span><span class="sxs-lookup"><span data-stu-id="373e0-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="373e0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="373e0-119">See Also</span></span>

- [<span data-ttu-id="373e0-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="373e0-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="373e0-121">索引器</span><span class="sxs-lookup"><span data-stu-id="373e0-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="373e0-122">属性</span><span class="sxs-lookup"><span data-stu-id="373e0-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
