---
title: '#error - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: b335dfeed23d43938c66f0753590af55ac99b12a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235577"
---
# <a name="error-c-reference"></a><span data-ttu-id="8b2c9-102">#error（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8b2c9-102">#error (C# Reference)</span></span>
<span data-ttu-id="8b2c9-103">`#error` 可从代码中的特定位置生成 [CS1029](../compiler-messages/cs1029.md) 用户定义的错误。</span><span class="sxs-lookup"><span data-stu-id="8b2c9-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="8b2c9-104">例如:</span><span class="sxs-lookup"><span data-stu-id="8b2c9-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="8b2c9-105">备注</span><span class="sxs-lookup"><span data-stu-id="8b2c9-105">Remarks</span></span>  
 <span data-ttu-id="8b2c9-106">`#error` 常用于条件指令中。</span><span class="sxs-lookup"><span data-stu-id="8b2c9-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="8b2c9-107">还可使用 [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) 生成用户定义警告。</span><span class="sxs-lookup"><span data-stu-id="8b2c9-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b2c9-108">示例</span><span class="sxs-lookup"><span data-stu-id="8b2c9-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8b2c9-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b2c9-109">See Also</span></span>

- [<span data-ttu-id="8b2c9-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8b2c9-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8b2c9-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8b2c9-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8b2c9-112">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="8b2c9-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
