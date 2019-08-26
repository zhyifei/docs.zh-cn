---
title: '#undef - C# 参考'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: fdf22e90be766e87e823a7f8cc27ea00c17d2bb5
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605585"
---
# <a name="undef-c-reference"></a><span data-ttu-id="ad222-102">#undef（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ad222-102">#undef (C# Reference)</span></span>
<span data-ttu-id="ad222-103">`#undef` 允许你定义一个符号，这样一来，通过将该符号用作 [#if](./preprocessor-if.md) 指令中的表达式，表达式将计算为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ad222-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="ad222-104">可使用 [#define](./preprocessor-define.md) 指令或 [-define](../compiler-options/define-compiler-option.md) 编译器选项来定义符号。</span><span class="sxs-lookup"><span data-stu-id="ad222-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="ad222-105">文件中必须先出现 `#undef` 指令，才能使用任何非指令的语句。</span><span class="sxs-lookup"><span data-stu-id="ad222-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad222-106">示例</span><span class="sxs-lookup"><span data-stu-id="ad222-106">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="ad222-107">未定义 DEBUG </span><span class="sxs-lookup"><span data-stu-id="ad222-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="ad222-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad222-108">See also</span></span>

- [<span data-ttu-id="ad222-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ad222-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ad222-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ad222-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ad222-111">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="ad222-111">C# Preprocessor Directives</span></span>](./index.md)
