---
title: "&lt;备注&gt;(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f70c2d7df190d2ff8187882a9176dbe98984296
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltremarksgt-visual-basic"></a>&lt;备注&gt;(Visual Basic)
指定成员的备注部分。  
  
## <a name="syntax"></a>语法  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>参数  
 `description`  
 对成员的说明。  
  
## <a name="remarks"></a>备注  
 使用`<remarks>`标记来将有关补充与指定的信息的类型信息添加[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)。  
  
 此信息显示在对象浏览器。 有关对象浏览器的信息，请参阅[查看代码结构](/visualstudio/ide/viewing-the-structure-of-code)。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<remarks>`标记解释`UpdateRecord`方法执行。  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
