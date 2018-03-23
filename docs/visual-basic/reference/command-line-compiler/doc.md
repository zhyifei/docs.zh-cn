---
title: -doc
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0948b9ef0675541ca595bb297e01e62c9d79a181
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-doc"></a>-doc
将文档注释处理到一个 XML 文件中。  
  
## <a name="syntax"></a>语法  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`+` &#124; `-`|可选。 指定 +，或仅仅称为`-doc`，使编译器生成文档信息并将其放在 XML 文件。 指定`-`等同于不指定`-doc`，不导致要创建任何文档信息。|  
|`file`|如果使用 `-doc:`，则是必需的。 指定输出 XML 文件中，填入编译源代码文件中的注释。 如果文件名包含空格，请使用引号将名称 ("")。|  
  
## <a name="remarks"></a>备注  
 `-doc`选项控制是否编译器将生成包含文档注释的 XML 文件。 如果你使用`-doc:file`语法，`file`参数指定 XML 文件的名称。 如果你使用`-doc`或`-doc+`，编译器将从可执行文件或编译器正在创建的库中获取 XML 文件名称。 如果你使用`-doc-`或不指定`-doc`选项，编译器不创建 XML 文件。  
  
 在源代码文件中，文档注释可以在前面的以下定义：  
  
-   用户定义类型，如[类](../../../visual-basic/language-reference/statements/class-statement.md)或[接口](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   成员，例如一个字段，[事件](../../../visual-basic/language-reference/statements/event-statement.md)，[属性](../../../visual-basic/language-reference/statements/property-statement.md)，[函数](../../../visual-basic/language-reference/statements/function-statement.md)，或[子例程](../../../visual-basic/language-reference/statements/sub-statement.md)。  
  
 若要使用生成的 XML 文件与[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense)功能，请让你想要支持的程序集相同的 XML 文件的文件名称。 请确保 XML 文件与程序集相同的目录中，以便当中引用的程序集[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]项目，.xml 文件也可以找到。 XML 文档文件不是必需的 IntelliSense 项目中或在项目引用的项目中的代码工作的。  
  
 除非使用编译`/target:module`，XML 文件包含标记`<assembly></assembly>`。 这些标记指定包含编译输出文件的程序集清单的文件的名称。  
  
 请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)从你的代码中的注释生成文档的方法。  
  
|若要设置的文档在 Visual Studio 集成开发环境|  
|---|  
|1.在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“编译”选项卡。<br />3.设置中的值**生成 XML 文档文件**框。|  
  
## <a name="example"></a>示例  
 请参阅[使用 XML 编制文档您代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)有关的示例。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [使用 XML 记录代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
