---
title: 编译项目中的 XML 架构时发生错误
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 0cc565809792c619ca9903f9ef9b029b51a8aa17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>编译项目中的 XML 架构时发生错误
编译该项目中的 XML 架构时发生错误。 因此，XML IntelliSense 不可用。  
  
 在项目中包含的 XML 架构定义 (XSD) 架构时发生错误。 当你添加为项目设置与现有的 XSD 架构冲突的 XSD 架构 (.xsd) 文件时，将出现此错误。  
  
 **错误 ID:** BC36810  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   双击中的警告**错误列表**窗口。 Visual Basic 将转到 XSD 文件的警告的源中的位置。 更正 XSD 架构中的错误。  
  
-   确保所有必需的 XSD 架构 (.xsd) 文件都包括在项目中。 你可能需要单击**显示所有文件**上**项目**菜单以查看你.xsd 文件中**解决方案资源管理器**。 右击.xsd 文件，然后单击**包括在项目**要包含在你的项目中的文件。  
  
-   如果你使用的 XML 到架构向导，从同一源推断架构不止一次可以发生此错误。 在这种情况下，你可以从该项目中删除现有的 XSD 架构文件添加新的 XML 架构项模板，然后提供 XML 到架构向导与所有适用的 XML 源为你的项目。  
  
-   如果在 XSD 架构中不标识了任何错误，XML 编译器可能没有足够的信息来提供详细的错误消息。 你可以获取更详细的错误信息，如果你确保.xsd 文件的 XML 命名空间包含在你的项目匹配标识在 Visual Studio 中设置的 XML 架构的 XML 命名空间。  
  
## <a name="see-also"></a>请参阅  
 [“错误列表”窗口](/visualstudio/ide/reference/error-list-window)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
