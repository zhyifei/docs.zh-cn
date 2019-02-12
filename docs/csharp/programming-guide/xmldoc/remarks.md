---
title: <remarks> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: b290315cd9c36281c110bbf0c6246468a1a899b2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259158"
---
# <a name="remarks-c-programming-guide"></a>\<remarks>（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>参数  
 `Description`  
 对成员的说明。  
  
## <a name="remarks"></a>备注  
 \<remarks> 标记用于添加有关某个类型的信息，从而补充由 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 指定的信息。 此信息显示在对象浏览器窗口中。  
  
 使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)
- [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
