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
# <a name="error-c-reference"></a>#error（C# 参考）
`#error` 可从代码中的特定位置生成 [CS1029](../compiler-messages/cs1029.md) 用户定义的错误。 例如:  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>备注  
 `#error` 常用于条件指令中。  
  
 还可使用 [#warning](./preprocessor-warning.md) 生成用户定义警告。  
  
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
  
## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 预处理器指令](./index.md)
