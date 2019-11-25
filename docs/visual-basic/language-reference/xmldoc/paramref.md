---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 78227a17584271f91283198e95f5aa389b3ef14b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352283"
---
# <a name="paramref-visual-basic"></a>\<paramref> (Visual Basic)
Formats a word as a parameter.  
  
## <a name="syntax"></a>语法  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a>参数  
 `name`  
 要引用的参数的名称。 用双引号 (" ") 将名称引起来。  
  
## <a name="remarks"></a>备注  
 The `<paramref>` tag gives you a way to indicate that a word is a parameter. The XML file can be processed to format this parameter in some distinct way.  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 This example uses the `<paramref>` tag to refer to the `id` parameter.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
