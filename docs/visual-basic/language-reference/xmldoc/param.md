---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4405fdf2defbb27aa2146d20083fd406d1f07236
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352287"
---
# <a name="param-visual-basic"></a>\<param> (Visual Basic)
Defines a parameter name and description.  
  
## <a name="syntax"></a>语法  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>参数  
 `name`  
 方法参数的名称。 用双引号 (" ") 将名称引起来。  
  
 `description`  
 参数的说明。  
  
## <a name="remarks"></a>备注  
 The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.  
  
 The text for the `<param>` tag will appear in the following locations:  
  
- Parameter Info of IntelliSense. 有关详细信息，请参阅[使用 IntelliSense](/visualstudio/ide/using-intellisense)。  
  
- Object Browser. 有关详细信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 This example uses the `<param>` tag to describe the `id` parameter.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
