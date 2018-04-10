---
title: '#pragma（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f53bd0ed3f35f049b0a1cbb21c5b9a563f9fce9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-c-reference"></a>#pragma（C# 参考）
`#pragma` 为编译器给出特殊指令以编译它所在的文件。 这些指令必须受编译器支持。 即是说，不可使用 `#pragma` 创建自定义处理指令。 Microsoft C# 编译器支持以下两种 `#pragma` 指令：  
  
 [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [#pragma checksum](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>语法  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a>参数  
 `pragma-name`  
 已识别杂注的名称。  
  
 `pragma-arguments`  
 特定于杂注的参数。  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
 [#pragma checksum](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
