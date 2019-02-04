---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 476b3f4f6b85908897e15f73bc23d2b060e337c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283642"
---
# <a name="param-visual-basic"></a>\<param > (Visual Basic)
定义的参数名称和说明。  
  
## <a name="syntax"></a>语法  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>参数  
 `name`  
 方法参数的名称。 用双引号 (" ") 将名称引起来。  
  
 `description`  
 参数的说明。  
  
## <a name="remarks"></a>备注  
 `<param>`标记应使用方法声明的注释，以描述一个方法的参数。  
  
 文本`<param>`标记将出现在以下位置：  
  
-   参数的 IntelliSense 信息。 有关详细信息，请参阅[使用 IntelliSense](/visualstudio/ide/using-intellisense)。  
  
-   对象浏览器。 有关详细信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。  
  
 使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用`<param>`标记来描述`id`参数。  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>请参阅
- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
