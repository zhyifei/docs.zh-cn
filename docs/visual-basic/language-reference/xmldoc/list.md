---
title: '&lt;列表&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: f03924217393e1e909b086b282f1c62ddb471522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603608"
---
# <a name="ltlistgt-visual-basic"></a>&lt;列表&gt;(Visual Basic)
定义列表或表。  
  
## <a name="syntax"></a>语法  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### <a name="parameters"></a>参数  
 `type`  
 列表的类型。 项目符号列表、 编号的列表，或有两个列的表"表"的"number"必须是"项目符号"。  
  
 `term`  
 仅当`type`是"table"。 要定义的项，说明标记中定义。  
  
 `description`  
 时`type`是"项目符号"编号"`description`是在列表中的项时`type`是"table"`description`是定义`term`。  
  
## <a name="remarks"></a>备注  
 `<listheader>`块定义表或定义列表的标题。 当定义一个表，只需提供的条目`term`标题中。  
  
 使用指定列表中的每个项`<item>`块。 在创建时定义列表，则必须将同时指定`term`和`description`。 但是，对于表、 项目符号列表中或编号的列表，只需提供的条目`description`。  
  
 列表或表可以有任意多个`<item>`阻止根据需要。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<list>`标记来定义在备注部分中的项目符号列表。  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
