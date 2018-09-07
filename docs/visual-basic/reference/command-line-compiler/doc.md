---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44082052"
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
|`+` &#124; `-`|可选。 指定 +，或只是`-doc`，使编译器生成文档信息并将其放在一个 XML 文件。 指定`-`相当于不指定`-doc`，若要创建任何文档信息。|  
|`file`|如果使用 `-doc:`，则是必需的。 指定输出 XML 文件中，填入编译源代码文件中的注释。 如果文件名包含空格，将名称括起来加上引号 ("")。|  
  
## <a name="remarks"></a>备注  
 `-doc`选项控制是否编译器生成包含文档注释的 XML 文件。 如果您使用`-doc:file`语法，`file`参数指定的 XML 文件的名称。 如果您使用`-doc`或`-doc+`，编译器将从可执行文件或编译器正在创建的库中获取 XML 文件名称。 如果您使用`-doc-`，或者不指定`-doc`选项，编译器不会创建一个 XML 文件。  
  
 在源代码文件中，文档注释之前可以放置以下定义：  
  
-   用户定义类型，如[类](../../../visual-basic/language-reference/statements/class-statement.md)或[接口](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   成员，一个字段，例如[事件](../../../visual-basic/language-reference/statements/event-statement.md)，[属性](../../../visual-basic/language-reference/statements/property-statement.md)，[函数](../../../visual-basic/language-reference/statements/function-statement.md)，或者[子例程](../../../visual-basic/language-reference/statements/sub-statement.md)。  
  
 若要使用 Visual Studio 使用生成的 XML 文件[IntelliSense](/visualstudio/ide/using-intellisense)功能，让你想要支持的程序集相同的 XML 文件的文件名。 请确保 XML 文件与程序集相同的目录中，以便当 Visual Studio 项目中引用的程序集，也会找到.xml 文件。 XML 文档文件不需要的 IntelliSense 功能在项目中或在项目引用的项目中的代码。  
  
 除非使用进行编译`/target:module`，XML 文件包含的标记`<assembly></assembly>`。 这些标记指定包含编译输出文件的程序集清单的文件的名称。  
  
 请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)从代码中的注释生成文档的方法。  
  
|若要设置-文档在 Visual Studio 集成开发环境|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“编译”选项卡。<br />3.中的值设置**生成 XML 文档文件**框。|  
  
## <a name="example"></a>示例  
 请参阅[使用 XML 记录您代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)有关的示例。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [使用 XML 记录代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
