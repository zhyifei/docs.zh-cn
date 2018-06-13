---
title: Namespace 或类型中的项目级导入指定&#39; &lt;qualifiedelementname&gt; &#39;不&#39;t 包含任何公共成员，或者找不到
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: d6d0c931262d892ec3e65888a76f25218b23d868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595808"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace 或类型中的项目级导入指定&#39; &lt;qualifiedelementname&gt; &#39;不&#39;t 包含任何公共成员，或者找不到
Namespace 或类型中的项目级导入的指定\<qualifiedelementname > 不包含任何公共成员，或无法找到。 请确保命名空间或类型定义，并且包含至少一个公共成员。 请确保该别名名称不包含其他别名。  
  
 一个项目的导入属性所指定的包含的元素不能找到或未定义任何`Public`成员。  
  
 A*包含元素*可以是命名空间、 类、 结构、 模块、 接口或枚举。 包含的元素包含成员，例如变量、 过程或其他包含的元素。  
  
 导入的目的是允许你访问命名空间或类型成员的代码，而无需限定它们。 你的项目可能还需要添加对命名空间或类型的引用。 详细信息，请参阅"导入包含元素"中[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。  
  
 如果编译器找不到指定的包含元素，它无法解析使用它的引用。 如果它找到的元素，但该元素不公开任何`Public`成员，则任何引用都不会成功。 在任一情况下是没有意义，来导入元素。  
  
 你使用**项目设计器**可指定要导入元素。 使用**导入命名空间**部分**引用**页。 你可以到达**项目设计器**通过双击**我的项目**图标**解决方案资源管理器**。  
  
 **错误 ID:** BC40057  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  打开**项目设计器**并切换到**引用**页。  
  
2.  在**导入命名空间**部分中，验证是否可从你的项目访问包含的元素。  
  
3.  验证包含元素公开至少一个`Public`成员。  
  
## <a name="see-also"></a>请参阅  
 [项目设计器 ->“引用”页 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
