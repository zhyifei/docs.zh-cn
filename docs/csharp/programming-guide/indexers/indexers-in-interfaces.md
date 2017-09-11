---
title: "接口中的索引器（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
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
ms.openlocfilehash: 2715602dadea40324f613bb07b5dd332ed18c25c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="6cde5-102">接口中的索引器（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="6cde5-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="6cde5-103">可以在[接口](../../../csharp/language-reference/keywords/interface.md)上声明索引器。</span><span class="sxs-lookup"><span data-stu-id="6cde5-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="6cde5-104">接口索引器的访问器与[类](../../../csharp/language-reference/keywords/class.md)索引器的访问器有所不同，差异如下：</span><span class="sxs-lookup"><span data-stu-id="6cde5-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="6cde5-105">接口访问器不使用修饰符。</span><span class="sxs-lookup"><span data-stu-id="6cde5-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="6cde5-106">接口访问器没有正文。</span><span class="sxs-lookup"><span data-stu-id="6cde5-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="6cde5-107">因此，访问器的用途是指示索引器为读写、只读还是只写。</span><span class="sxs-lookup"><span data-stu-id="6cde5-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="6cde5-108">下面是接口索引器访问器的示例：</span><span class="sxs-lookup"><span data-stu-id="6cde5-108">The following is an example of an interface indexer accessor:</span></span>  
  
 <span data-ttu-id="6cde5-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6cde5-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="6cde5-110">索引器的签名必须不同于同一接口中声明的所有其他索引器的签名。</span><span class="sxs-lookup"><span data-stu-id="6cde5-110">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cde5-111">示例</span><span class="sxs-lookup"><span data-stu-id="6cde5-111">Example</span></span>  
 <span data-ttu-id="6cde5-112">下面的示例演示如何实现接口索引器。</span><span class="sxs-lookup"><span data-stu-id="6cde5-112">The following example shows how to implement interface indexers.</span></span>  
  
 <span data-ttu-id="6cde5-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6cde5-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="6cde5-114">在前面的示例中，可通过使用接口成员的完全限定名来使用显示接口成员实现。</span><span class="sxs-lookup"><span data-stu-id="6cde5-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="6cde5-115">例如：</span><span class="sxs-lookup"><span data-stu-id="6cde5-115">For example:</span></span>  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 <span data-ttu-id="6cde5-116">但仅当类采用相同的索引签名实现多个接口时，才需用到完全限定名称以避免歧义。</span><span class="sxs-lookup"><span data-stu-id="6cde5-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="6cde5-117">例如，如果 `Employee` 类正在实现接口 `ICitizen` 和接口 `IEmployee`，而这两个接口具有相同的索引签名，则需要用到显式接口成员实现。</span><span class="sxs-lookup"><span data-stu-id="6cde5-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="6cde5-118">即是说以下索引器声明：</span><span class="sxs-lookup"><span data-stu-id="6cde5-118">That is, the following indexer declaration:</span></span>  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 <span data-ttu-id="6cde5-119">在 `IEmployee` 接口中实现索引器，而以下声明：</span><span class="sxs-lookup"><span data-stu-id="6cde5-119">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 <span data-ttu-id="6cde5-120">在 `ICitizen` 接口中实现索引器。</span><span class="sxs-lookup"><span data-stu-id="6cde5-120">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cde5-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cde5-121">See Also</span></span>  
 <span data-ttu-id="6cde5-122">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6cde5-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6cde5-123">[索引器](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="6cde5-123">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="6cde5-124">[属性](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="6cde5-124">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="6cde5-125">接口</span><span class="sxs-lookup"><span data-stu-id="6cde5-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

