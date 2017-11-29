---
title: "&lt;代码&gt;(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7c1d8ab3db0c36c6a2935b9ffbef15e87df5ebc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltcodegt-visual-basic"></a>&lt;代码&gt;(Visual Basic)
指示该文本是多行代码。  
  
## <a name="syntax"></a>语法  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a>参数  
 `content`  
 要将标记为代码的文本。  
  
## <a name="remarks"></a>备注  
 使用`<code>`标记以指示多行代码。 使用 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) 指示应将说明内的文本标记为代码。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用\<代码 > 标记，包括示例代码使用`ID`字段。  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
