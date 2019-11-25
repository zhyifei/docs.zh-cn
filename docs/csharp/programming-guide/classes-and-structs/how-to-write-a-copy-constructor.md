---
title: 如何编写复制构造函数（C# 编程指南）
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 4ac7ccb55775019eb86d5345797d2fd74d3b9527
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970392"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="320de-102">如何编写复制构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="320de-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="320de-103">C# 不会为对象提供复制构造函数，但你可以自己编写一个。</span><span class="sxs-lookup"><span data-stu-id="320de-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="320de-104">示例</span><span class="sxs-lookup"><span data-stu-id="320de-104">Example</span></span>  
 <span data-ttu-id="320de-105">在下面的示例中，`Person`[类](../../language-reference/keywords/class.md)定义一个复制构造函数，该函数使用 `Person` 的实例作为其参数。</span><span class="sxs-lookup"><span data-stu-id="320de-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="320de-106">该参数的属性值分配给 `Person` 的新实例的属性。</span><span class="sxs-lookup"><span data-stu-id="320de-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="320de-107">该代码包含一个备用复制构造函数，该函数发送要复制到该类的实例构造函数的实例的 `Name` 和 `Age` 属性。</span><span class="sxs-lookup"><span data-stu-id="320de-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="320de-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="320de-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="320de-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="320de-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="320de-110">类和结构</span><span class="sxs-lookup"><span data-stu-id="320de-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="320de-111">构造函数</span><span class="sxs-lookup"><span data-stu-id="320de-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="320de-112">终结器</span><span class="sxs-lookup"><span data-stu-id="320de-112">Finalizers</span></span>](./destructors.md)
