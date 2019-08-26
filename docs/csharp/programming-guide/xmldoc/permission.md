---
title: <permission> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: e9eb50394f01072a194d3f746577707f89ba65dd
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587881"
---
# <a name="permission-c-programming-guide"></a>\<permission>（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>参数  
 cref = " `member`"  
 对可从当前编译环境调用的成员或字段的引用。 编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。 成员必须出现在双引号 (" ") 内  。  
  
 有关如何创建对泛型类型的 cref 引用的信息，请参阅 [\<see>](./see.md)。  
  
 `description`  
 对成员访问权限的说明。  
  
## <a name="remarks"></a>备注  
 使用 \<permission> 可以记录成员访问权限 <xref:System.Security.PermissionSet> 类可指定对成员的访问权限。  
  
 使用 [/doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../index.md)
- [建议的文档注释标记](./recommended-tags-for-documentation-comments.md)
