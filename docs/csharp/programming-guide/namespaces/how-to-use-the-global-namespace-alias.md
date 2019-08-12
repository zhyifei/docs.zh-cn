---
title: 如何：使用全局命名空间别名 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796292"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="32f9e-102">如何：使用全局命名空间别名（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="32f9e-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="32f9e-103">当具有同一名称的其他实体可能隐藏了成员时，访问全局[命名空间](../../../csharp/language-reference/keywords/namespace.md)中的成员的功能将十分有用。</span><span class="sxs-lookup"><span data-stu-id="32f9e-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="32f9e-104">例如，在下面的代码中，`Console` 解析为 `TestApp.Console` 而不是 <xref:System> 命名空间中的 `Console` 类型。</span><span class="sxs-lookup"><span data-stu-id="32f9e-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 <span data-ttu-id="32f9e-105">使用 `System.Console` 仍会导致错误，因为类 `TestApp.System` 隐藏了 `System` 命名空间：</span><span class="sxs-lookup"><span data-stu-id="32f9e-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 <span data-ttu-id="32f9e-106">但是，可以使用 `global::System.Console` 解决此错误，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32f9e-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 <span data-ttu-id="32f9e-107">如果左标识符为 `global`，则会在全局命名空间开始搜索右标识符。</span><span class="sxs-lookup"><span data-stu-id="32f9e-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="32f9e-108">例如，以下声明引用 `TestApp` 作为全局空间的成员。</span><span class="sxs-lookup"><span data-stu-id="32f9e-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 <span data-ttu-id="32f9e-109">显然，不建议将自己的命名空间的名称创建为 `System`，并且不可能会遇到发生此情况的代码。</span><span class="sxs-lookup"><span data-stu-id="32f9e-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="32f9e-110">但是，在大型项目中，很有可能会以一种或另一种形式发生命名空间重复。</span><span class="sxs-lookup"><span data-stu-id="32f9e-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="32f9e-111">在这些情况下，全局命名空间限定符可保证指定根命名空间。</span><span class="sxs-lookup"><span data-stu-id="32f9e-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f9e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="32f9e-112">See also</span></span>

- [<span data-ttu-id="32f9e-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="32f9e-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="32f9e-114">命名空间</span><span class="sxs-lookup"><span data-stu-id="32f9e-114">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="32f9e-115">::运算符</span><span class="sxs-lookup"><span data-stu-id="32f9e-115">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="32f9e-116">extern</span><span class="sxs-lookup"><span data-stu-id="32f9e-116">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
