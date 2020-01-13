---
title: 如何编写复制构造函数（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: aa6feb1b07f491a90a78684e254910d387b9bccd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714841"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="8c05f-102">如何编写复制构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8c05f-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="8c05f-103">C# 不会为对象提供复制构造函数，但你可以自己编写一个。</span><span class="sxs-lookup"><span data-stu-id="8c05f-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c05f-104">示例</span><span class="sxs-lookup"><span data-stu-id="8c05f-104">Example</span></span>  
 <span data-ttu-id="8c05f-105">在下面的示例中，`Person`[类](../../language-reference/keywords/class.md)定义一个复制构造函数，该函数使用 `Person` 的实例作为其参数。</span><span class="sxs-lookup"><span data-stu-id="8c05f-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="8c05f-106">该参数的属性值分配给 `Person` 的新实例的属性。</span><span class="sxs-lookup"><span data-stu-id="8c05f-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="8c05f-107">该代码包含一个备用复制构造函数，该函数发送要复制到该类的实例构造函数的实例的 `Name` 和 `Age` 属性。</span><span class="sxs-lookup"><span data-stu-id="8c05f-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="8c05f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c05f-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="8c05f-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8c05f-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8c05f-110">类和结构</span><span class="sxs-lookup"><span data-stu-id="8c05f-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="8c05f-111">构造函数</span><span class="sxs-lookup"><span data-stu-id="8c05f-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="8c05f-112">终结器</span><span class="sxs-lookup"><span data-stu-id="8c05f-112">Finalizers</span></span>](./destructors.md)
