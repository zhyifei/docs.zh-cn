---
title: '&lt;paramref&gt; - C# 编程指南'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 21f8eb293a006a748c876a3b816eae3a799d3d7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640883"
---
# <a name="ltparamrefgt-c-programming-guide"></a>&lt;paramref&gt;（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>参数  
 `name`  
 要引用的参数的名称。 用双引号 (" ") 将名称引起来。  
  
## <a name="remarks"></a>备注  
 \<paramref> 标记提供一种方式，用于指示 \<summary> 或 \<remarks> 块等代码注释中的单词引用某个参数。 可以处理 XML 文件以明显的方式设置此单词的格式，如使用粗体或斜体。  
  
 使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)
- [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
