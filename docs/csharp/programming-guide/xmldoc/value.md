---
title: '&lt;value&gt;（C# 编程指南）'
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 22de15560d6db6e8a70cea744dd9d85359336306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ltvaluegt-c-programming-guide"></a>&lt;value&gt;（C# 编程指南）
## <a name="syntax"></a>语法  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>参数  
 `property-description`  
 属性的说明。  
  
## <a name="remarks"></a>备注  
 \<value> 标记可以描述属性表示的值。 请注意，在 Visual Studio .NET 开发环境中通过代码向导添加属性时，将添加新属性的 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 标记。 然后，应手动添加 \<value> 标记，描述属性表示的值。  
  
 使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
