---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 96ef62d53fd1cc806c0dc72d2d0781b1c6297dc6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970865"
---
# <a name="para-visual-basic"></a>\<para > (Visual Basic)
指定内容的格式设置为一个段落。  
  
## <a name="syntax"></a>语法  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a>参数  
 `content`  
 段落文本。  
  
## <a name="remarks"></a>备注  
 `<para>`标记是用于标记内，例如[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)， [\<备注 >](../../../visual-basic/language-reference/xmldoc/remarks.md)，或[\<返回 >](../../../visual-basic/language-reference/xmldoc/returns.md)，并允许您向文本添加结构。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<para>`拆分备注部分的标记`UpdateRecord`分成两个段落的方法。  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅
- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
