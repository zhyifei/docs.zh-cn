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
# <a name="undef-c-reference"></a>#undef（C# 参考）
`#undef` 允许你定义一个符号，这样一来，通过将该符号用作 [#if](./preprocessor-if.md) 指令中的表达式，表达式将计算为 `false`。  
  
 可使用 [#define](./preprocessor-define.md) 指令或 [-define](../compiler-options/define-compiler-option.md) 编译器选项来定义符号。 文件中必须先出现 `#undef` 指令，才能使用任何非指令的语句。  
  
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

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 预处理器指令](./index.md)
