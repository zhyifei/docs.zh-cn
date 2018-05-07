---
title: Visual Basic 中的生存期
ms.date: 07/20/2015
helpviewer_keywords:
- static variables [Visual Basic], lifetime
- static variables [Visual Basic], Visual Basic
- declared elements [Visual Basic], lifetime
- Shared variable lifetime [Visual Basic]
- lifetime [Visual Basic], declared elements
- lifetime [Visual Basic], Visual Basic
- lifetime [Visual Basic]
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
ms.openlocfilehash: d32639f1c392d53a7e9f6258440b6c0925d27a5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="lifetime-in-visual-basic"></a>Visual Basic 中的生存期
*生存期*的已声明的元素是的时间段期间它是可供使用。 变量是具有生存期的唯一元素。 为此，编译器将过程参数和函数返回值视为变量的特殊情况。 变量的生存期表示在此期间它可以存放一个值的时间。 其值可以更改在其生存期内，但它始终包含一些值。  
  
## <a name="different-lifetimes"></a>不同的生存期  
 A*成员变量*（在模块级别，任何过程之外声明） 通常具有在其中声明的元素的生存期相同。 声明的类或结构中的非共享的变量作为单独的类或结构声明它的每个实例的副本存在。 每个此类变量具有相同的生存期与它的实例。 但是，`Shared`变量仅有单个生存期，即持续运行你的应用程序的整个时间。  
  
 A*局部变量*（过程内部声明） 运行在其中声明该过程时才存在。 这还适用于该过程的参数和返回任何函数。 但是，如果该过程调用其他过程，本地变量保留其值时运行的被调用的过程。  
  
## <a name="beginning-of-lifetime"></a>生存期的开头  
 本地变量的生存期开始时控制进入在其中声明该过程。 每个本地变量初始化为其数据类型的默认值，只要该过程开始运行。 当过程遇到`Dim`语句中指定初始值，它将设置这些变量为这些值，即使你的代码必须对其分配了其他值。  
  
 就像它是单独的变量初始化结构变量的每个成员。 同样，单独初始化数组变量的每个元素。  
  
 在过程内块内声明的变量 (如`For`循环) 初始化在进入该过程。 无论你的代码执行该块，则这些初始化会生效。  
  
## <a name="end-of-lifetime"></a>生存期结束时的  
 当过程终止时，不保留其本地变量的值，并 Visual Basic 回收其内存。 下次调用过程中，所有其本地变量重新创建和重新初始化。  
  
 当类或结构的实例终止时，其非共享的变量将丢失其内存和它们的值。 每个类或结构的新实例创建，并重新初始化其非共享的变量。 但是，`Shared`变量被保留，直到你的应用程序停止运行。  
  
## <a name="extension-of-lifetime"></a>生存期的扩展  
 如果声明的局部变量`Static`关键字，它的生存期即比其过程的执行时间长。 下表显示如何过程声明确定多长时间`Static`变量存在。  
  
|过程位置和共享|静态变量生存期开始|静态变量的生存期结束|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|（默认情况下共享） 模块中|在首次调用该过程|在你的应用程序停止运行时|  
|在类中， `Shared` （过程不是一个实例成员）|第一次调用过程对特定实例或者对类或结构名称本身|在你的应用程序停止运行时|  
|类的实例中不`Shared`（过程是一个实例成员）|第一次特定实例上调用过程|当垃圾回收 (GC) 释放该实例|  
  
## <a name="static-variables-of-the-same-name"></a>具有相同名称的静态变量  
 您可以声明具有相同名称在多个过程中的静态变量。 如果执行此操作时，Visual Basic 编译器会将每个此类变量视为一个单独的元素。 其中一个变量的初始化并不影响其他的值。 这同样适用如果定义一个具有一组重载过程并声明中每个重载具有相同名称的静态变量。  
  
## <a name="containing-elements-for-static-variables"></a>静态变量包含的元素  
 你可以在该类中的过程，即声明静态局部变量一个类中。 但是，不能声明为静态局部变量结构中，为结构成员或为该结构内的一个过程的局部变量。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的示例声明的变量[静态](../../../../visual-basic/language-reference/modifiers/static.md)关键字。 (请注意，不需要`Dim`关键字时[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)使用修饰符，如`Static`。)  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>注释  
 在前面的示例中，变量`applesSold`继续执行步骤后存在`runningTotal`返回到调用代码。 下一次`runningTotal`调用时，`applesSold`会保留其以前计算的值。  
  
 如果`applesSold`已声明但未使用`Static`，以前的累积的值将不会保留调用之间`runningTotal`。 下一次`runningTotal`调用，`applesSold`本来会被重新创建和初始化为 0，和`runningTotal`将只返回与其调用的相同值。  
  
### <a name="compiling-the-code"></a>编译代码  
 你可以初始化为其声明的一部分的静态本地变量的值。 如果你声明一个数组是`Static`，则可以初始化其秩 （维数）、 每个维度的长度和各个元素的值。  
  
### <a name="security"></a>安全性  
 在前面的示例中，您可以通过声明中生成相同的生存期`applesSold`在模块级别。 如果发生这种方式更改变量的作用域，但是，该过程将不再具有到它的独占访问权限。 由于无法访问其他过程`applesSold`并将其值更改，运行总计可能是不可靠并且代码可能会更难以维护。  
  
## <a name="see-also"></a>请参阅  
 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [在 Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)
