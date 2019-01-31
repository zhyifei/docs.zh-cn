---
title: <list> (Visual Basic)
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
ms.openlocfilehash: 522450e4efcecaf74968ddb492b536aa98dc0b13
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260280"
---
# <a name="list-visual-basic"></a>\<列表 > (Visual Basic)
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
 列表的类型。 对于项目符号列表、 编号的列表，或两列的表"表"的"number"必须为"bullet"。  
  
 `term`  
 仅当使用`type`是"table"。 要定义的术语，说明标记中定义。  
  
 `description`  
 当`type`"bullet"或"数字"`description`是列表中的项时`type`是"table"`description`的定义是`term`。  
  
## <a name="remarks"></a>备注  
 `<listheader>`块定义的表或定义列表的标题。 在定义表时，只需提供的条目`term`标题中。  
  
 使用指定列表中的每个项`<item>`块。 创建定义列表时，必须指定`term`和`description`。 但是，对于表、 项目符号列表或编号的列表，只需提供的条目`description`。  
  
 列表或表可以有任意多个`<item>`根据需要将阻止。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<list>`标记以在备注部分中定义的项目符号列表。  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>请参阅
- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
