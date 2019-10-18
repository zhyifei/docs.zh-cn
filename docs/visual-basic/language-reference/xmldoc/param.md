---
title: <param> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c62eab6b1fb1ba1cc7de83c12d7205cf0bbe46fa
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524729"
---
# <a name="param-visual-basic"></a>\<param > （Visual Basic）
定义参数名称和说明。  
  
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
 应在方法声明的注释中使用 `<param>` 标记来描述方法的参数之一。  
  
 @No__t_0 标记的文本将出现在以下位置：  
  
- IntelliSense 的参数信息。 有关详细信息，请参阅[使用 IntelliSense](/visualstudio/ide/using-intellisense)。  
  
- 对象浏览器。 有关详细信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。  
  
 使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
 此示例使用 `<param>` 标记来描述 `id` 参数。  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>请参阅

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
