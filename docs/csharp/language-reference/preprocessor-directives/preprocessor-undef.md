---
title: '#undef（C# 参考）'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 3957d58f61e51fab01618f5e1146be9cd0da58fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185962"
---
# <a name="undef-c-reference"></a>#undef（C# 参考）
`#undef` 允许你定义一个符号，这样一来，通过将该符号用作 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指令中的表达式，表达式将计算为 `false`。  
  
 可使用 [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 指令或 [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 编译器选项来定义符号。 文件中必须先出现 `#undef` 指令，才能使用任何非指令的语句。  
  
## <a name="example"></a>示例  

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

未定义 DEBUG

## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)
