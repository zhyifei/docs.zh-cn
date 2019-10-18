---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524032"
---
# <a name="code-visual-basic"></a>\<code > （Visual Basic）
指示文本为多行代码。  
  
## <a name="syntax"></a>语法  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>参数  
 `content`  
 要标记为代码的文本。  
  
## <a name="remarks"></a>备注  
 使用 `<code>` 标记将多行指示为代码。 使用 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) 指示应将说明内的文本标记为代码。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用 \<code > 标记，包括使用 `ID` 字段的示例代码。  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
