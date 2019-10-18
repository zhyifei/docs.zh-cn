---
title: <para> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524743"
---
# <a name="para-visual-basic"></a>\<para > （Visual Basic）
指定将内容的格式设置为段落。  
  
## <a name="syntax"></a>语法  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>参数  
 `content`  
 段落文本。  
  
## <a name="remarks"></a>备注  
 @No__t_0 标记在标记内使用，如[\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)、 [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md)或[\<returns](../../../visual-basic/language-reference/xmldoc/returns.md)>，并允许向文本中添加结构。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用 `<para>` 标记将 `UpdateRecord` 方法的备注部分拆分为两个段落。  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
