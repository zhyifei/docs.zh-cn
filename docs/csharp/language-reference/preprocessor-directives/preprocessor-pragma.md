---
title: '#pragma - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65ca38ff6993117b6ed9f716d4ac93ba2d4a9ddf
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605667"
---
# <a name="pragma-c-reference"></a>#pragma（C# 参考）
`#pragma` 为编译器给出特殊指令以编译它所在的文件。 这些指令必须受编译器支持。 即是说，不可使用 `#pragma` 创建自定义处理指令。 Microsoft C# 编译器支持以下两种 `#pragma` 指令：  
  
 [#pragma warning](./preprocessor-pragma-warning.md)  
  
 [#pragma checksum](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>语法  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a>参数  
 `pragma-name`  
 已识别杂注的名称。  
  
 `pragma-arguments`  
 特定于杂注的参数。  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 预处理器指令](./index.md)
- [#pragma warning](./preprocessor-pragma-warning.md)
- [#pragma checksum](./preprocessor-pragma-checksum.md)
