---
title: 如何：使用全局命名空间别名 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: 6d3e0740a472f74116712e737e49f86d4202dea5
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452802"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="8b337-102">如何：使用全局命名空间别名（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8b337-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="8b337-103">当具有同一名称的其他实体可能隐藏了成员时，访问全局[命名空间](../../../csharp/language-reference/keywords/namespace.md)中的成员的功能将十分有用。</span><span class="sxs-lookup"><span data-stu-id="8b337-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="8b337-104">例如，在下面的代码中，`Console` 解析为 `TestApp.Console` 而不是 <xref:System> 命名空间中的 `Console` 类型。</span><span class="sxs-lookup"><span data-stu-id="8b337-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 <span data-ttu-id="8b337-105">使用 `System.Console` 仍会导致错误，因为类 `TestApp.System` 隐藏了 `System` 命名空间：</span><span class="sxs-lookup"><span data-stu-id="8b337-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 <span data-ttu-id="8b337-106">但是，可以使用 `global::System.Console` 解决此错误，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b337-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 <span data-ttu-id="8b337-107">如果左标识符为 `global`，则会在全局命名空间开始搜索右标识符。</span><span class="sxs-lookup"><span data-stu-id="8b337-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="8b337-108">例如，以下声明引用 `TestApp` 作为全局空间的成员。</span><span class="sxs-lookup"><span data-stu-id="8b337-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 <span data-ttu-id="8b337-109">显然，不建议将自己的命名空间的名称创建为 `System`，并且不可能会遇到发生此情况的代码。</span><span class="sxs-lookup"><span data-stu-id="8b337-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="8b337-110">但是，在大型项目中，很有可能会以一种或另一种形式发生命名空间重复。</span><span class="sxs-lookup"><span data-stu-id="8b337-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="8b337-111">在这些情况下，全局命名空间限定符可保证指定根命名空间。</span><span class="sxs-lookup"><span data-stu-id="8b337-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b337-112">示例</span><span class="sxs-lookup"><span data-stu-id="8b337-112">Example</span></span>  
 <span data-ttu-id="8b337-113">在此示例中，命名空间 `System` 用于包括类 `TestClass`，因此， `global::System.Console` 必须用于引用 `System.Console` 类，该类由 `System` 命名空间隐藏。</span><span class="sxs-lookup"><span data-stu-id="8b337-113">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="8b337-114">此外，别名 `colAlias` 用于引用命名空间 `System.Collections`；因此，<xref:System.Collections.Hashtable?displayProperty=nameWithType> 实例是使用此别名而不是命名空间创建的。</span><span class="sxs-lookup"><span data-stu-id="8b337-114">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=nameWithType> was created using this alias instead of the namespace.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]  
  
<span data-ttu-id="8b337-115">**A 1**
**B 2**
**C 3**</span><span class="sxs-lookup"><span data-stu-id="8b337-115">**A 1**
**B 2**
**C 3**</span></span>

## <a name="see-also"></a><span data-ttu-id="8b337-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b337-116">See also</span></span>

- [<span data-ttu-id="8b337-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8b337-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8b337-118">命名空间</span><span class="sxs-lookup"><span data-stu-id="8b337-118">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="8b337-119">::运算符</span><span class="sxs-lookup"><span data-stu-id="8b337-119">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)
- [<span data-ttu-id="8b337-120">extern</span><span class="sxs-lookup"><span data-stu-id="8b337-120">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
