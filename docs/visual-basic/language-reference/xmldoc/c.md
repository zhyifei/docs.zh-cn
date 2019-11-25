---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348513"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)
Indicates that text within a description is code.  
  
## <a name="syntax"></a>语法  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>参数  
  
|参数|描述|  
|---|---|  
|`text`|要指示为代码的文本。|  
  
## <a name="remarks"></a>备注  
 The `<c>` tag gives you a way to indicate that text within a description should be marked as code. 使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 指示作为代码的多行文本。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
