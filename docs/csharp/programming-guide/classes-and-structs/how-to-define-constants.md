---
title: 如何：在 C# 中定义常量
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 26d46335df3333379d5577a5c21a85a39eb6e43a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713193"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="19516-102">如何：在 C# 中定义常量</span><span class="sxs-lookup"><span data-stu-id="19516-102">How to: Define Constants in C#</span></span>
<span data-ttu-id="19516-103">常量是在编译时设置其值并且永远不能更改其值的字段。</span><span class="sxs-lookup"><span data-stu-id="19516-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="19516-104">使用常量可以为特殊值提供有意义的名称，而不是数字文本（“幻数”）。</span><span class="sxs-lookup"><span data-stu-id="19516-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19516-105">在 C# 中，不能以 C 和 C++ 中通常采用的方式使用 [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 预处理器指令定义常量。</span><span class="sxs-lookup"><span data-stu-id="19516-105">In C# the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="19516-106">若要定义整型类型（`int`、`byte` 等）的常量值，请使用枚举类型。</span><span class="sxs-lookup"><span data-stu-id="19516-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="19516-107">有关详细信息，请参阅[枚举](../../../csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="19516-107">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="19516-108">若要定义非整型常量，一种方法是将它们分组到一个名为 `Constants` 的静态类。</span><span class="sxs-lookup"><span data-stu-id="19516-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="19516-109">这要求对常量的所有引用都在其前面加上该类名，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="19516-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19516-110">示例</span><span class="sxs-lookup"><span data-stu-id="19516-110">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 <span data-ttu-id="19516-111">使用类名限定符有助于确保你和使用该常量的其他人了解它是常量并且不能修改。</span><span class="sxs-lookup"><span data-stu-id="19516-111">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19516-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="19516-112">See also</span></span>

- [<span data-ttu-id="19516-113">类和结构</span><span class="sxs-lookup"><span data-stu-id="19516-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
