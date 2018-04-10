---
title: '&lt;值&gt;(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a72c6330596e59d26fbae9d13f6b9c8b1987e519
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltvaluegt-visual-basic"></a>&lt;值&gt;(Visual Basic)
指定属性的说明。  
  
## <a name="syntax"></a>语法  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>参数  
 `property-description`  
 属性的说明。  
  
## <a name="remarks"></a>备注  
 使用`<value>`标记来描述属性。 请注意，当你添加在 Visual Studio 开发环境中使用代码向导某个属性，它将添加[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)标记为新的属性。 然后，应手动添加`<value>`标记来描述该属性表示的值。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<value>`标记来描述哪些值`Counter`属性包含。  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
