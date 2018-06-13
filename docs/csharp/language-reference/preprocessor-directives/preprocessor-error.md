---
title: '#error（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 9ea4c24dcc3c0a4d39499bee5900cb9c6cc768c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269394"
---
# <a name="error-c-reference"></a><span data-ttu-id="0312e-102">#error（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0312e-102">#error (C# Reference)</span></span>
<span data-ttu-id="0312e-103">`#error` 可从代码中的特定位置生成错误。</span><span class="sxs-lookup"><span data-stu-id="0312e-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="0312e-104">例如:</span><span class="sxs-lookup"><span data-stu-id="0312e-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="0312e-105">备注</span><span class="sxs-lookup"><span data-stu-id="0312e-105">Remarks</span></span>  
 <span data-ttu-id="0312e-106">`#error` 常用于条件指令中。</span><span class="sxs-lookup"><span data-stu-id="0312e-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="0312e-107">还可使用 [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) 生成用户定义警告。</span><span class="sxs-lookup"><span data-stu-id="0312e-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0312e-108">示例</span><span class="sxs-lookup"><span data-stu-id="0312e-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0312e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0312e-109">See Also</span></span>  
 [<span data-ttu-id="0312e-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0312e-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0312e-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0312e-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0312e-112">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="0312e-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
