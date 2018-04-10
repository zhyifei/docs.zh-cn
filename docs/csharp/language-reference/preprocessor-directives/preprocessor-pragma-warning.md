---
title: '#杂注警告（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5330b448dc2b328992b2d29699557d20df56dee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-warning-c-reference"></a>#pragma warning（C# 参考）
`#pragma warning` 可以启用或禁用特定警告。  
  
## <a name="syntax"></a>语法  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a>参数  
 `warning-list`  
 以逗号分隔的警告编号的列表。 “CS”前缀是可选的。  
  
 未指定警告编号时，`disable` 会禁用所有警告，`restore` 会启用所有警告。  
  
> [!NOTE]
>  若要在 Visual Studio 中查找警告编号，请生成项目，然后在“输出”窗口中查找警告编号。  
  
## <a name="example"></a>示例  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [C# 编译器错误](../../../csharp/language-reference/compiler-messages/index.md)
