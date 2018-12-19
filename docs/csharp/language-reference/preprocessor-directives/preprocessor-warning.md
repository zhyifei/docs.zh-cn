---
title: '#warning - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 08fcefd904ad43c781017087082592120e21f5cd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236825"
---
# <a name="warning-c-reference"></a><span data-ttu-id="be92a-102">#warning（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="be92a-102">#warning (C# Reference)</span></span>
<span data-ttu-id="be92a-103">`#warning` 允许你从代码中的特定位置生成 [ CS1030](../../misc/cs1030.md) 第一级编译器警告。</span><span class="sxs-lookup"><span data-stu-id="be92a-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="be92a-104">例如:</span><span class="sxs-lookup"><span data-stu-id="be92a-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="be92a-105">备注</span><span class="sxs-lookup"><span data-stu-id="be92a-105">Remarks</span></span>
 <span data-ttu-id="be92a-106">`#warning` 常用于条件指令中。</span><span class="sxs-lookup"><span data-stu-id="be92a-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="be92a-107">还可使用 [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) 生成用户定义错误。</span><span class="sxs-lookup"><span data-stu-id="be92a-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be92a-108">示例</span><span class="sxs-lookup"><span data-stu-id="be92a-108">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="be92a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="be92a-109">See Also</span></span>

- [<span data-ttu-id="be92a-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="be92a-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="be92a-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="be92a-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="be92a-112">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="be92a-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
