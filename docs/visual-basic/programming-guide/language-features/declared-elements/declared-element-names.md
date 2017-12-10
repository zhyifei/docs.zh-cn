---
title: "已声明的元素名称 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59fee9eb79af86df7f01bd77c27a929ef61fcfe2
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="declared-element-names-visual-basic"></a>已声明的元素名称 (Visual Basic)
每个声明的元素有一个名称，也称为*标识符*，即来引用它的代码使用。  
  
## <a name="rules"></a>规则  
 中的元素名称[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]必须遵守以下规则：  
  
-   它必须以字母字符或下划线开头 (`_`)。  
  
-   它必须仅包含字母字符、 十进制数字和下划线。  
  
-   如果以下划线开头，它必须包含至少一个字母字符或十进制数。  
  
-   它不得超过 1023年个字符长。  
  
 1023 个字符的长度限制也适用于整个字符串的完全限定名称，如`outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`。  
  
 下面的示例演示了一些有效的元素名称。  
  
 `aB123__45`  
  
 `_567`  
  
 下面的示例演示一些无效的元素名称。 第一个仅包含一个下划线、 十进制数字，开头开始第二个和第三个包含无效字符 （$）。  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  元素名称以下划线开头 (`_`) 不属于[语言独立性和独立于语言的组件](../../../../../docs/standard/language-independence-and-language-independent-components.md)(CLS)，因此符合 cls 的代码不能使用定义此类名称的组件。 但是，在元素名中的任何其他位置中以下划线是符合 CLS。  
  
### <a name="name-length-guidelines"></a>名称长度准则  
 在实践中，你的名称应尽可能短同时在仍然能够清楚地标识的元素的性质。 这可以提高代码的可读性，并减少行长度和源文件大小。  
  
 另一方面，你的名称不应为太短，它不会不充分描述该元素表示和你的代码如何使用它。 这是你代码的可读性很重要。 如果其他人尝试理解它，或你自己正在寻求通过它您在编写后很长时间，适合元素名称可以节省相当长的时间。  
  
## <a name="escaped-names"></a>转义的名称  
 通常，元素名称必须与任何不匹配的保留的关键字[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]，如`Case`或`Friend`。 但是，你可以定义*转义名称*，这由括号括起来 (`[ ]`)。 转义的名称可以匹配任何[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]关键字，因为括号消除了不明确性。 在更高版本在你的代码中引用名时，还可以使用括号。  
  
 一般情况下，应使用转义的名称时，才：  
  
-   你的代码已从早期版本的迁移[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]，没有保留关键字用作名称; 或  
  
-   你正在使用在其中给定的关键字不保留的另一种语言编写的代码。  
  
 否则，应考虑重命名元素，如果其名称与关键字冲突。 集成的开发环境 (IDE) 提供了执行此操作的简单办法。 有关详细信息，请参阅[重构](/visualstudio/vb-ide/refactoring-vb)。  
  
## <a name="case-sensitivity-in-names"></a>在名称中的区分大小写  
 中的元素名称[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]不区分大小写。 这意味着当编译器在比较两个字母大小写不同的名称，将其解释为相同的名称。 例如，它认为 `ABC` 和 `abc` 指的是同一个声明的元素。  
  
 但是，公共语言运行时 (CLR) 使用区分大小写的绑定。 因此，当你生成程序集或 DLL 并使其可供其他程序集使用时，则名称将不再不区分大小写。 例如，如果你用名为 `ABC`的元素定义类，而其他程序集通过公共语言运行时使用你的类，则元素必须指的是 `ABC`。 如果你以后重新编译你的类并将更改元素的名称与`abc`，则使用你的类的其他程序集将无法再访问该元素。 因此，发布程序集的更新版本时，不应该更改公共元素的字母大小写。  
  
## <a name="names-and-locales"></a>名称和区域设置  
 名称比较是独立于区域设置。 如果在一个区域设置中匹配两个名称，可确保在所有区域设置匹配。  
  
## <a name="see-also"></a>另请参阅  
 [已声明的元素](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [已声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [语句](../../../../visual-basic/language-reference/statements/index.md)
