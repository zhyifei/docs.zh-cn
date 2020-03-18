---
title: '#error - C# 参考'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 28e77304edee617adc1422e6a52d0a617cd9b3bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173401"
---
# <a name="error-c-reference"></a><span data-ttu-id="a7b83-102">#error（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a7b83-102">#error (C# Reference)</span></span>
<span data-ttu-id="a7b83-103">`#error` 可从代码中的特定位置生成 [CS1029](../compiler-messages/cs1029.md) 用户定义的错误。</span><span class="sxs-lookup"><span data-stu-id="a7b83-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="a7b83-104">例如:</span><span class="sxs-lookup"><span data-stu-id="a7b83-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="a7b83-105">备注</span><span class="sxs-lookup"><span data-stu-id="a7b83-105">Remarks</span></span>  
 <span data-ttu-id="a7b83-106">`#error` 常用于条件指令中。</span><span class="sxs-lookup"><span data-stu-id="a7b83-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="a7b83-107">还可使用 [#warning](./preprocessor-warning.md) 生成用户定义警告。</span><span class="sxs-lookup"><span data-stu-id="a7b83-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7b83-108">示例</span><span class="sxs-lookup"><span data-stu-id="a7b83-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a7b83-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7b83-109">See also</span></span>

- [<span data-ttu-id="a7b83-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a7b83-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a7b83-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a7b83-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a7b83-112">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="a7b83-112">C# Preprocessor Directives</span></span>](./index.md)
