---
title: '&lt;typeparamref&gt;（C# 编程指南）'
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: c14b3f788c474f2e345f8325d45b942d0f3008da
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530151"
---
# <a name="lttypeparamrefgt-c-programming-guide"></a>&lt;typeparamref&gt;（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a>参数  
 `name`  
 类型参数的名称。 用双引号 (" ") 将名称引起来。  
  
## <a name="remarks"></a>备注  
 有关泛型类型中的类型参数及方法的详细信息，请参阅[泛型](../../../csharp/programming-guide/generics/index.md)。  
  
 通过此标记，文档文件的使用者可显著设置字体格式，例如采用斜体。  
  
 使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
