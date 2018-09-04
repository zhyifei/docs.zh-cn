---
title: '&lt;示例&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 2de91d828fd9706b66f4c810486e54e2d3062de0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524512"
---
# <a name="ltexamplegt-visual-basic"></a>&lt;示例&gt;(Visual Basic)
指定成员的一个示例。  
  
## <a name="syntax"></a>语法  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a>参数  
 `description`  
 代码示例的说明。  
  
## <a name="remarks"></a>备注  
 `<example>`标记，可以指定如何使用方法或其他库成员的示例。 这通常涉及到使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 标记。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<example>`标记包含有关使用示例`ID`字段。  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
