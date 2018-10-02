---
title: '&lt;包括&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: da7a6c15c558fc56dbc6a874d4a28c4434f67668
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2018
ms.locfileid: "47455968"
---
# <a name="ltincludegt-visual-basic"></a>&lt;包括&gt;(Visual Basic)
表示描述的类型和成员在源代码中的另一个文件。  
  
## <a name="syntax"></a>语法  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>参数  
 `filename`  
 必须的。 包含文档的文件的名称。 可使用路径来限定文件名。 将`filename`在双引号 ("")。  
  
 `tagpath`  
 必须的。 `filename` 中标记的路径，它指向标记 `name`。 将该路径括在双引号 ("")。  
  
 `name`  
 必须的。 中位于注释前的标记的名称说明符。 `Name` 将具有`id`。  
  
 `id`  
 必须的。 标记的 ID（位于注释之前）。 将 ID 括在单引号 (' ')。  
  
## <a name="remarks"></a>备注  
 使用`<include>`标记引用另一个文件中描述的类型的注释和你的源代码中的成员。 这是对直接在源代码文件中放入文档注释的替代方法。  
  
 `<include>`标记使用 W3C XML 路径语言 (XPath) 1.0 版建议。 有关如何自定义的详细信息您`<include>`使用位于 http://www.w3.org/TR/xpath。  
  
## <a name="example"></a>示例  
 此示例使用`<include>`标记从名为的文件导入成员文档注释`commentFile.xml`。  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 格式`commentFile.xml`如下所示。  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a>请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
