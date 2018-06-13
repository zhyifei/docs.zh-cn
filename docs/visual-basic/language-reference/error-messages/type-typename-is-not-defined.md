---
title: 类型&#39; &lt;typename&gt; &#39;未定义
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 20f36a06000d0197ad80b83766f6612a474d5758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595181"
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>类型&#39; &lt;typename&gt; &#39;未定义
该语句已对尚未定义的类型引用。 你可以定义一种类型的声明语句中诸如`Enum`， `Structure`， `Class`，或`Interface`。  
  
 **错误 ID:** BC30002  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   请确保类型定义和它的引用都使用相同的拼写。  
  
-   请确保类型定义为引用可访问。 例如，如果类型是另一个模块中并已被声明为`Private`、 将类型定义移到引用的模块或将其声明`Public`。  
  
-   请确保类型的命名空间不会重新定义您的项目中。 如果是，使用`Global`关键字用于完全限定类型名称。 例如，如果一个项目定义的命名空间名为`System`、<xref:System.Object?displayProperty=nameWithType>无法访问类型，除非它是使用完全限定`Global`关键字： `Global.System.Object`。  
  
-   如果定义的类型，但在 Visual Basic、 单击未注册的对象库或在其中定义的类型库**添加引用**上**项目**菜单，然后选择适当的对象库或类型库。  
  
-   请确保该类型所在的目标.NET Framework 配置文件一部分的程序集中。 有关详细信息，请参阅 [.NET Framework 目标错误疑难解答](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)
