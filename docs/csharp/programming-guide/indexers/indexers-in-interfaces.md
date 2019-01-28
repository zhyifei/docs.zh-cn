---
title: 接口中的索引器 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 5d2dc8f5bdb0b89d5fd265ad86cbb13401bc8b14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523579"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="ae7d0-102">接口中的索引器（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ae7d0-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="ae7d0-103">可以在[接口](../../../csharp/language-reference/keywords/interface.md)上声明索引器。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="ae7d0-104">接口索引器的访问器与[类](../../../csharp/language-reference/keywords/class.md)索引器的访问器有所不同，差异如下：</span><span class="sxs-lookup"><span data-stu-id="ae7d0-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="ae7d0-105">接口访问器不使用修饰符。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="ae7d0-106">接口访问器没有正文。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="ae7d0-107">因此，访问器的用途是指示索引器为读写、只读还是只写。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="ae7d0-108">下面是接口索引器访问器的示例：</span><span class="sxs-lookup"><span data-stu-id="ae7d0-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 <span data-ttu-id="ae7d0-109">索引器的签名必须不同于同一接口中声明的所有其他索引器的签名。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae7d0-110">示例</span><span class="sxs-lookup"><span data-stu-id="ae7d0-110">Example</span></span>  
 <span data-ttu-id="ae7d0-111">下面的示例演示如何实现接口索引器。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 <span data-ttu-id="ae7d0-112">在前面的示例中，可通过使用接口成员的完全限定名来使用显示接口成员实现。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="ae7d0-113">例如:</span><span class="sxs-lookup"><span data-stu-id="ae7d0-113">For example:</span></span>  
  
```  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="ae7d0-114">但仅当类采用相同的索引签名实现多个接口时，才需用到完全限定名称以避免歧义。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="ae7d0-115">例如，如果 `Employee` 类正在实现接口 `ICitizen` 和接口 `IEmployee`，而这两个接口具有相同的索引签名，则需要用到显式接口成员实现。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="ae7d0-116">即是说以下索引器声明：</span><span class="sxs-lookup"><span data-stu-id="ae7d0-116">That is, the following indexer declaration:</span></span>  
  
```  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="ae7d0-117">在 `IEmployee` 接口中实现索引器，而以下声明：</span><span class="sxs-lookup"><span data-stu-id="ae7d0-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="ae7d0-118">在 `ICitizen` 接口中实现索引器。</span><span class="sxs-lookup"><span data-stu-id="ae7d0-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7d0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae7d0-119">See also</span></span>

- [<span data-ttu-id="ae7d0-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ae7d0-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ae7d0-121">索引器</span><span class="sxs-lookup"><span data-stu-id="ae7d0-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)
- [<span data-ttu-id="ae7d0-122">属性</span><span class="sxs-lookup"><span data-stu-id="ae7d0-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="ae7d0-123">接口</span><span class="sxs-lookup"><span data-stu-id="ae7d0-123">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
