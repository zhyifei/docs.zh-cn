---
title: 处理 XML 文件
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 4230fd88b4b60c631135f5b7fb15f4b6272b5351
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347306"
---
# <a name="processing-the-xml-file-visual-basic"></a>处理 XML 文件 (Visual Basic)
编译器为代码（已标记以生成文档）中的每个构造生成一个 ID 字符串。 (For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md).) The ID string uniquely identifies the construct. Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item.  
  
 The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.  
  
 编译器在生成 ID 字符串时应遵循以下规则：  
  
- 字符串不得包含空格。  
  
- ID 字符串的第一部分标识被标识的成员类型，单个字符后跟一个冒号。 The following member types are used.  
  
|字符|描述|  
|---|---|  
|N|namespace<br /><br /> You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.|  
|T|type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|field: `Dim`|  
|P|property: `Property` (including default properties)|  
|M|method: `Sub`, `Function`, `Declare`, `Operator`|  
|E|event: `Event`|  
|!|错误字符串<br /><br /> 字符串的其余部分提供有关错误的信息。 The Visual Basic compiler generates error information for links that cannot be resolved.|  
  
- The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace. The name of the item, its enclosing type(s), and the namespace are separated by periods. If the name of the item itself contains periods, they are replaced by the number sign (#). It is assumed that no item has a number sign directly in its name. For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.  
  
- 对于属性和方法，如果方法带有自变量，则后跟用括号括起来的自变量列表。 如果没有任何自变量，则不会出现括号。 确保自变量之间用逗号分隔。 The encoding of each argument follows directly how it is encoded in a .NET Framework signature.  
  
## <a name="example"></a>示例  
 The following code shows how the ID strings for a class and its members are generated.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>请参阅

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
