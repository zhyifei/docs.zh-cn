---
title: '#else（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c3468d35a6e45c06f46fe8671708ce01a3cc7b65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="else-c-reference"></a>#else（C# 参考）
`#else` 允许创建复合条件指令，因此，如果先前 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 或（可选）[#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 指令中的表达式没有一个为 `true`，则编译器将对介于 `#else` 和后续 `#endif` 之间的所有代码进行评估。  
  
## <a name="remarks"></a>备注  
 [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) 必须是 `#else` 之后的下一个预处理器指令。 有关如何使用 `#else` 的示例，请参阅 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)。  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)
