---
title: '#error - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: f18dbd007e80397b815256231a1d56e5ca50010e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608557"
---
# <a name="error-c-reference"></a><span data-ttu-id="88e8a-102">#error（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="88e8a-102">#error (C# Reference)</span></span>
<span data-ttu-id="88e8a-103">`#error` 可从代码中的特定位置生成 [CS1029](../compiler-messages/cs1029.md) 用户定义的错误。</span><span class="sxs-lookup"><span data-stu-id="88e8a-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="88e8a-104">例如:</span><span class="sxs-lookup"><span data-stu-id="88e8a-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="88e8a-105">备注</span><span class="sxs-lookup"><span data-stu-id="88e8a-105">Remarks</span></span>  
 <span data-ttu-id="88e8a-106">`#error` 常用于条件指令中。</span><span class="sxs-lookup"><span data-stu-id="88e8a-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="88e8a-107">还可使用 [#warning](./preprocessor-warning.md) 生成用户定义警告。</span><span class="sxs-lookup"><span data-stu-id="88e8a-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88e8a-108">示例</span><span class="sxs-lookup"><span data-stu-id="88e8a-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="88e8a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="88e8a-109">See also</span></span>

- [<span data-ttu-id="88e8a-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="88e8a-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="88e8a-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="88e8a-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="88e8a-112">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="88e8a-112">C# Preprocessor Directives</span></span>](./index.md)
