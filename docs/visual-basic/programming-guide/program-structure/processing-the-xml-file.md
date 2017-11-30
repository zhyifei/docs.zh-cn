---
title: "处理 XML 文件 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d44f58951d99f1b4b551af75dc0a0e895e337e2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="processing-the-xml-file-visual-basic"></a>处理 XML 文件 (Visual Basic)
编译器为代码（已标记以生成文档）中的每个构造生成一个 ID 字符串。 (有关如何标记代码的信息，请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)。)ID 字符串唯一标识构造。 处理 XML 文件的程序可以使用的 ID 字符串以标识相应[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]元数据/反射项。  
  
 XML 文件不是代码的你; 分层表示形式它是与每个元素的生成 ID 的平面列表。  
  
 编译器在生成 ID 字符串时应遵循以下规则：  
  
-   在字符串中不放置任何空格。  
  
-   ID 字符串的第一部分标识的标识，与单个字符跟一个冒号的成员的类型。 使用以下成员类型。  
  
|字符|描述|  
|---|---|  
|N|namespace<br /><br /> 无法将文档注释添加到命名空间中，但可以对它们的 CREF 引用支持的位置。|  
|T|类型： `Class`， `Module`， `Interface`， `Structure`， `Enum`，`Delegate`|  
|F|字段：`Dim`|  
|P|属性： `Property` （包括默认属性）|  
|M|方法： `Sub`， `Function`， `Declare`，`Operator`|  
|E|事件：`Event`|  
|!|错误字符串<br /><br /> 字符串的其余部分提供有关错误的信息。 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将生成错误无法解析的链接的信息。|  
  
-   第二部分`String`是项，在命名空间的根目录的完全限定的名称。 用句点分隔的项、 其封闭类型和命名空间的名称。 如果项本身的名称包含句点，因为它们被替代数字符号 （#）。 假定任何项，直接在其名称中有数字符号。 例如，完全限定的名称的`String`构造函数将`System.String.#ctor`。  
  
-   对于属性和方法，如果方法带有自变量，则后跟用括号括起来的自变量列表。 如果没有任何自变量，则不会出现括号。 确保自变量之间用逗号分隔。 编码的每个自变量都直接遵循中的编码方式[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]签名。  
  
## <a name="example"></a>示例  
 下面的代码演示如何的 ID 字符串的类，并生成其成员。  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
