---
title: <seealso> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: 430270c170f2829d9bf9b90d258c948176b9c086
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523327"
---
# <a name="seealso-c-programming-guide"></a>\<seealso>（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a>参数  
 cref = " `member`"  
 对可从当前编译环境调用的成员或字段的引用。 编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。`member` 必须在双引号 (" ") 内。  
  
 有关如何创建对泛型类型的 cref 引用的信息，请参阅 [\<see>](./see.md)。  
  
## <a name="remarks"></a>备注  
 使用 \<seealso> 标记，可以指定想要在“另请参阅”部分中显示的文本。 使用 [\<see>](./see.md) 从文本内指定链接。  
  
 使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 有关使用 \<seealso> 的示例，请参阅 [\<summary>](./summary.md)。  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../index.md)
- [建议的文档注释标记](./recommended-tags-for-documentation-comments.md)
