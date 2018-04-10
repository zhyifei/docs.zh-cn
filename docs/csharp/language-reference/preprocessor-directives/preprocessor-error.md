---
title: '#error（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23528ae81e4ddca23c67c937ca2588ab4c982e98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="error-c-reference"></a>#error（C# 参考）
`#error` 可从代码中的特定位置生成错误。 例如:   
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>备注  
 `#error` 常用于条件指令中。  
  
 还可使用 [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) 生成用户定义警告。  
  
## <a name="example"></a>示例  
  
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
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)
