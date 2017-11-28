---
title: "&lt;permission&gt;（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37bb37ea14edc1f91225f9b04b18b354d99579b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltpermissiongt-c-programming-guide"></a>&lt;permission&gt;（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>参数  
 cref = " `member`"  
 对可从当前编译环境调用的成员或字段的引用。 编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。 成员必须出现在双引号 (" ") 内。  
  
 有关如何创建对泛型类型的 cref 引用的信息，请参阅 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)。  
  
 `description`  
 对成员访问权限的说明。  
  
## <a name="remarks"></a>备注  
 使用 \<permission> 可以记录成员访问权限 <xref:System.Security.PermissionSet> 类可指定对成员的访问权限。  
  
 使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
