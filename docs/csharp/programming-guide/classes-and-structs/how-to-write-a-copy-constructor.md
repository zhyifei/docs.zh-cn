---
title: 如何：编写复制构造函数（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 8a7cc85d40272918f4839d13fcccb79b558eeac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322492"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="83dd1-102">如何：编写复制构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="83dd1-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="83dd1-103">C# 不会为对象提供复制构造函数，但你可以自己编写一个。</span><span class="sxs-lookup"><span data-stu-id="83dd1-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83dd1-104">示例</span><span class="sxs-lookup"><span data-stu-id="83dd1-104">Example</span></span>  
 <span data-ttu-id="83dd1-105">在下面的示例中，`Person`[类](../../../csharp/language-reference/keywords/class.md)定义一个复制构造函数，该函数使用 `Person` 的实例作为其参数。</span><span class="sxs-lookup"><span data-stu-id="83dd1-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="83dd1-106">该参数的属性值分配给 `Person` 的新实例的属性。</span><span class="sxs-lookup"><span data-stu-id="83dd1-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="83dd1-107">该代码包含一个备用复制构造函数，该函数发送要复制到该类的实例构造函数的实例的 `Name` 和 `Age` 属性。</span><span class="sxs-lookup"><span data-stu-id="83dd1-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="83dd1-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="83dd1-108">See Also</span></span>  
 <xref:System.ICloneable>  
 [<span data-ttu-id="83dd1-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="83dd1-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="83dd1-110">类和结构</span><span class="sxs-lookup"><span data-stu-id="83dd1-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="83dd1-111">构造函数</span><span class="sxs-lookup"><span data-stu-id="83dd1-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="83dd1-112">终结器</span><span class="sxs-lookup"><span data-stu-id="83dd1-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
