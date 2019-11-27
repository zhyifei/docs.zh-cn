---
title: 生存期
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
ms.openlocfilehash: 05a39388e8aa9681af60cf86a3df8346d744b69e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345314"
---
# <a name="lifetime-in-visual-basic"></a>Visual Basic 中的生存期
已声明元素的*生存期*是可供使用的时间段。 变量是具有生存期的唯一元素。 出于此目的，编译器将过程参数和函数返回视为变量的特殊情况。 变量的生存期表示它可以包含一个值的时间段。 它的值可以在其生存期内更改，但它始终保存某些值。  
  
## <a name="different-lifetimes"></a>不同生存期  
 *成员变量*（在模块级别声明，在任何过程之外）通常与声明该变量的元素具有相同的生存期。 在类或结构中声明的非共享变量作为为其声明的类或结构的每个实例的单独副本存在。 每个此类变量与实例的生存期相同。 但是，`Shared` 变量只有单个生存期，即应用程序运行的整个时间。  
  
 *局部变量*（在过程中声明）仅存在于声明它的过程正在运行。 这同样适用于该过程的参数和任何函数返回。 但是，如果该过程调用其他过程，则在调用的过程正在运行时，本地变量将保留其值。  
  
## <a name="beginning-of-lifetime"></a>生存期开头  
 当控件进入声明它的过程时，本地变量的生存期开始。 当过程开始运行时，每个本地变量都将被初始化为其数据类型的默认值。 当过程遇到指定初始值的 `Dim` 语句时，它会将这些变量设置为这些值，即使代码已将其他值分配给这些值也是如此。  
  
 结构变量的每个成员都初始化为一个单独的变量。 同样，数组变量的每个元素都是单独初始化的。  
  
 在过程中声明的块内声明的变量（如 `For` 循环）将在进入过程时被初始化。 无论代码是否执行块，这些初始化都将生效。  
  
## <a name="end-of-lifetime"></a>生存期结束  
 过程终止后，不会保留其局部变量的值，Visual Basic 将回收其内存。 下一次调用该过程时，将创建不用重新并重新初始化其所有局部变量。  
  
 当类或结构的实例终止时，其非共享变量将丢失其内存及其值。 类或结构的每个新实例都创建并重新初始化其非共享变量。 但是，在应用程序停止运行之前，会保留 `Shared` 变量。  
  
## <a name="extension-of-lifetime"></a>生存期扩展  
 如果使用 `Static` 关键字声明局部变量，则其生存期比其过程的执行时间长。 下表显示了过程声明如何确定 `Static` 变量存在的时间长度。  
  
|过程位置和共享|静态变量生存期开始|静态变量生存期结束|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|在模块中（默认情况下共享）|第一次调用该过程时|当应用程序停止运行时|  
|在类中，`Shared` （过程不是实例成员）|第一次在特定实例或类或结构名称本身上调用该过程|当应用程序停止运行时|  
|在类的实例中，不 `Shared` （过程是实例成员）|第一次在特定实例上调用该过程时|当发布实例进行垃圾回收（GC）时|  
  
## <a name="static-variables-of-the-same-name"></a>具有相同名称的静态变量  
 可以在多个过程中声明具有相同名称的静态变量。 如果这样做，Visual Basic 编译器会将每个此类变量视为一个单独的元素。 其中一个变量的初始化不会影响其他变量的值。 如果使用一组重载定义过程，并在每个重载中声明一个具有相同名称的静态变量，则这一点同样适用。  
  
## <a name="containing-elements-for-static-variables"></a>包含静态变量的元素  
 可以在类中声明静态局部变量，即在该类的过程中。 但是，不能在结构中声明静态局部变量，要么作为结构成员，要么在该结构内作为过程的局部变量。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>说明  
 下面的示例使用[Static](../../../../visual-basic/language-reference/modifiers/static.md)关键字声明一个变量。 （请注意，当[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)使用修饰符（如 `Static`）时，不需要 `Dim` 关键字。）  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbalrKeywords#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#13)]  
  
### <a name="comments"></a>注释  
 在前面的示例中，变量在 `runningTotal` 返回到调用代码后仍然存在 `applesSold`。 下次调用 `runningTotal` 时，`applesSold` 将保留其以前计算的值。  
  
 如果在未使用 `Static`的情况下声明 `applesSold`，则不会在对 `runningTotal`的调用之间保留以前的累计值。 下次调用 `runningTotal` 时，`applesSold` 将被重新创建并初始化为0，`runningTotal` 只返回与调用该值相同的值。  
  
### <a name="compiling-the-code"></a>编译代码  
 您可以将静态局部变量的值初始化为其声明的一部分。 如果声明要 `Static`的数组，则可以初始化其秩（维数）、每个维度的长度以及各个元素的值。  
  
### <a name="security"></a>安全  
 在前面的示例中，可以通过在模块级别声明 `applesSold` 来生成相同的生存期。 但是，如果您以这种方式更改了变量的作用域，则该过程将不再具有对它的独占访问权限。 由于其他过程可以访问 `applesSold` 和更改其值，因此，运行总计可能不可靠，并且代码可能更难以维护。  
  
## <a name="see-also"></a>另请参阅

- [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [范围 Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
