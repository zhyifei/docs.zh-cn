---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854725"
---
# <a name="ltcgt-visual-basic"></a>&lt;c&gt; (Visual Basic)
指示说明中的文本是代码。  
  
## <a name="syntax"></a>语法  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---|---|  
|`text`|要指示为代码的文本。|  
  
## <a name="remarks"></a>备注  
 `<c>`标记为您提供了一种方法，以指示说明中的文本应标记为代码。 使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 指示作为代码的多行文本。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<c>`指示的摘要部分中的标记`Counter`是代码。  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
