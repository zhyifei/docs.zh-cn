---
title: 如何：编写复制构造函数 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: bdc352566052f4cec1686176131e9b1e1b768794
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596602"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="bd55a-102">如何：编写复制构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="bd55a-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="bd55a-103">C# 不会为对象提供复制构造函数，但你可以自己编写一个。</span><span class="sxs-lookup"><span data-stu-id="bd55a-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd55a-104">示例</span><span class="sxs-lookup"><span data-stu-id="bd55a-104">Example</span></span>  
 <span data-ttu-id="bd55a-105">在下面的示例中，`Person`[类](../../language-reference/keywords/class.md)定义一个复制构造函数，该函数使用 `Person` 的实例作为其参数。</span><span class="sxs-lookup"><span data-stu-id="bd55a-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="bd55a-106">该参数的属性值分配给 `Person` 的新实例的属性。</span><span class="sxs-lookup"><span data-stu-id="bd55a-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="bd55a-107">该代码包含一个备用复制构造函数，该函数发送要复制到该类的实例构造函数的实例的 `Name` 和 `Age` 属性。</span><span class="sxs-lookup"><span data-stu-id="bd55a-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="bd55a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd55a-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="bd55a-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bd55a-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bd55a-110">类和结构</span><span class="sxs-lookup"><span data-stu-id="bd55a-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="bd55a-111">构造函数</span><span class="sxs-lookup"><span data-stu-id="bd55a-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="bd55a-112">终结器</span><span class="sxs-lookup"><span data-stu-id="bd55a-112">Finalizers</span></span>](./destructors.md)
