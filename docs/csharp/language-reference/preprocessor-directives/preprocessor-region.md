---
title: "#<a name=\"region-c-reference\"></a>region（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#region'
helpviewer_keywords: '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cce4a8ac79c4687280e28618d8863d16cd193a3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="region-c-reference"></a>#region（C# 参考）
利用 `#region`，可以指定在使用 Visual Studio Code 编辑器的[大纲功能](/visualstudio/ide/outlining)时可展开或折叠的代码块。 在较长的代码文件中，能够折叠或隐藏一个或多个区域会十分便利，这样，可将精力集中于当前处理的文件部分。 下面的示例演示如何定义区域：  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>备注  
 `#region` 块必须通过 [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) 指令终止。  
  
 `#region` 块不能与 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 块重叠。 但是，可以将 `#region` 块嵌套在 `#if` 块内，或将 `#if` 块嵌套在 `#region` 块内。  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)
