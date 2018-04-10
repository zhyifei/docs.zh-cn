---
title: '#undef（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7a3c162c0ecb8bb39cc13a34dcd15fa3ce96ebb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="undef-c-reference"></a>#undef（C# 参考）
`#undef` 允许你定义一个符号，这样一来，通过将该符号用作 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指令中的表达式，表达式将计算为 `false`。  
  
 可使用 [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 指令或 [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 编译器选项来定义符号。 文件中必须先出现 `#undef` 指令，才能使用任何非指令的语句。  
  
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
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)
