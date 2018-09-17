---
title: '&lt;typeparam&gt;（C# 编程指南）'
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: ec19060008c1c06c54c89dbddee7d24001bcdebc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45677742"
---
# <a name="lttypeparamgt-c-programming-guide"></a>&lt;typeparam&gt;（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>参数  
 `name`  
 类型参数的名称。 用双引号 (" ") 将名称引起来。  
  
 `description`  
 类型参数的说明。  
  
## <a name="remarks"></a>备注  
 在泛型类型或方法声明的注释中，应使用 `<typeparam>` 标记来描述类型参数。 为泛型类型或方法的每个类型参数添加标记。  
  
 有关详细信息，请参阅[泛型](../../../csharp/programming-guide/generics/index.md)。  
  
 `<typeparam>` 标记的文本将显示在 IntelliSense、[对象浏览器窗口](https://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)代码注释 Web 报表。  
  
 使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
