---
title: <list>
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
ms.openlocfilehash: db5c571d2f2c59419c886f6596f4e4dbd30d7baf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352320"
---
# <a name="list-visual-basic"></a>\<列表 > （Visual Basic）
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
  
## <a name="parameters"></a>参数  
 `type`  
 列表的类型。 必须是项目符号列表的 "项目符号"、编号列表的 "数字" 或两列表的 "表"。  
  
 `term`  
 仅在 `type` 为 "table" 时使用。 要定义的术语，在 description 标记中定义。  
  
 `description`  
 当 `type` 为 "项目符号" 或 "数字" 时，当 `type` 为 "table" 时，`description` 是列表中的项，`description` 是 `term`的定义。  
  
## <a name="remarks"></a>备注  
 `<listheader>` 块定义表或定义列表的标题。 定义表时，只需为标题中的 `term` 提供条目。  
  
 列表中的每一项都指定了一个 `<item>` 块。 创建定义列表时，必须同时指定 `term` 和 `description`。 但是，对于表、项目符号列表或编号列表，只需为 `description`提供条目。  
  
 列表或表可以具有任意数量的 `<item>` 块（根据需要）。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用 `<list>` 标记在 "备注" 部分中定义项目符号列表。  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>另请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
