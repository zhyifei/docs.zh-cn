---
title: '#elif（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 423cedfb947964172a6e06d54a6dd3c76d91e9f3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864422"
---
# <a name="elif-c-reference"></a><span data-ttu-id="414ae-102">#elif（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="414ae-102">#elif (C# Reference)</span></span>
<span data-ttu-id="414ae-103">`#elif` 可以创建复合条件指令。</span><span class="sxs-lookup"><span data-stu-id="414ae-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="414ae-104">如果之前的 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 和任何之前的可选 `#elif` 指令表达式的值为 `true`，则计算 `#elif` 表达式。</span><span class="sxs-lookup"><span data-stu-id="414ae-104">The `#elif` expression will be evaluated if neither the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="414ae-105">如果 `#elif` 表达式计算结果为 `true`，编译器将计算 `#elif` 和下一条件指令间的所有代码。</span><span class="sxs-lookup"><span data-stu-id="414ae-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="414ae-106">例如:</span><span class="sxs-lookup"><span data-stu-id="414ae-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="414ae-107">可以使用运算符 `==`（相等）、`!=`（不相等）、`&&`（和）以及`||`（或）计算多个符号。</span><span class="sxs-lookup"><span data-stu-id="414ae-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="414ae-108">还可以用括号对符号和运算符进行分组。</span><span class="sxs-lookup"><span data-stu-id="414ae-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="414ae-109">备注</span><span class="sxs-lookup"><span data-stu-id="414ae-109">Remarks</span></span>  
 <span data-ttu-id="414ae-110">`#elif` 等效于使用：</span><span class="sxs-lookup"><span data-stu-id="414ae-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="414ae-111">使用 `#elif` 更简单，因为每个 `#if` 均需要 [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)，但 `#elif` 可在没有匹配的 `#endif` 的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="414ae-111">Using `#elif` is simpler, because each `#if` requires a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="414ae-112">有关如何使用 `#elif` 的示例，请参阅 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)。</span><span class="sxs-lookup"><span data-stu-id="414ae-112">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414ae-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="414ae-113">See Also</span></span>

- [<span data-ttu-id="414ae-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="414ae-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="414ae-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="414ae-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="414ae-116">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="414ae-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
