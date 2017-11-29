---
title: "结构和类 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08e31481feac7a6184c6b29269d193c749f440ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="structures-and-classes-visual-basic"></a>结构和类 (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]统一的结构和类，因此这两个实体支持的大多数功能相同的语法。 但是，也有重要区别结构和类。  
  
 类具有引用类型的优点-传递一个引用是比传递的所有数据的结构变量更高效。 另一方面，结构不需要全局堆上的内存的分配。  
  
 因为无法从结构中继承，结构仅应该用于不需要进行扩展的对象。 当你想要创建的对象具有小型实例大小，并且考虑到类而不是结构的性能特征，请使用结构。  
  
## <a name="similarities"></a>相似之处  
 结构和类是在以下方面类似：  
  
-   都*容器*类型，这意味着，它们包含其他类型作为成员。  
  
-   都具有成员，它们可以包括构造函数、 方法、 属性、 字段、 常量、 枚举、 事件和事件处理程序。 但是，不要混淆具有声明这些成员*元素*的结构。  
  
-   两者的成员可以分别有不同访问级别。 例如，可以声明一个成员`Public`和另一个`Private`。  
  
-   两者都可以实现接口。  
  
-   同时可以包含共享的构造函数，或不带参数。  
  
-   两者都可以公开*默认属性*，前提是属性采用至少一个参数。  
  
-   同时可以声明并引发事件，并且两者都可以声明委托。  
  
## <a name="differences"></a>差异  
 结构和类在以下方面不同：  
  
-   结构是*值类型*; 类是*引用类型*。 结构类型的变量包含结构的数据，而不是那样包含对数据作为类类型的引用。  
  
-   结构使用堆栈分配;类使用堆分配。  
  
-   所有的结构元素都是`Public`默认情况下; 类变量和常量是`Private`默认情况下，其他类成员时`Public`默认情况下。 此行为对于类成员提供了与默认值的 Visual Basic 6.0 系统的兼容性。  
  
-   结构必须具有至少一个非共享变量或非共享、 非自定义事件的元素;类可以是完全为空。  
  
-   结构元素不能声明为`Protected`; 可以类成员。  
  
-   一个结构的过程可以处理事件，只有为[共享](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub`过程中，并仅通过的方式[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md); 任何类的过程可以处理事件，使用任一[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)关键字或`AddHandler`语句。 有关详细信息，请参阅[事件](../../../../visual-basic/programming-guide/language-features/events/index.md)。  
  
-   结构变量声明不能指定初始值设定项或数组; 的初始大小可以类变量声明。  
  
-   结构隐式继承自<xref:System.ValueType?displayProperty=nameWithType>类并不能从任何其他类型; 继承类可以从任何类或类而不继承<xref:System.ValueType?displayProperty=nameWithType>。  
  
-   结构是不可继承;类是。  
  
-   结构永远不会被终止，因此，公共语言运行时 (CLR) 永远不会调用<xref:System.Object.Finalize%2A>任何结构; 方法类终止垃圾回收器 (GC)，后者将调用<xref:System.Object.Finalize%2A>上检测到有任何活动的引用时的类剩余时间。  
  
-   结构不需要构造函数;类一样。  
  
-   结构可以具有非共享的构造函数仅当它们将采用参数;类可以让它们使用或不带参数。  
  
 每个结构有一个隐式公共构造函数不带参数。 此构造函数初始化为其默认值的结构的所有数据元素。 不能重新定义此行为。  
  
## <a name="instances-and-variables"></a>实例和变量  
 由于结构是值类型，每个结构变量是永久绑定到单个结构实例。 类是引用类型，但对象变量可以在不同时间指不同的类实例。 这一区别在通过以下方式影响你的结构和类的使用情况：  
  
-   **初始化。** 结构变量隐式包含使用元素的结构的无参数构造函数的初始化。 因此，`Dim s As struct1`等效于`Dim s As struct1 = New struct1()`。  
  
-   **为变量赋值。** 当将一个结构变量分配到另一个字符串，或将结构实例传递给过程自变量时，变量的所有元素的当前值复制到新的结构。 当将一个对象变量分配到另一个字符串，或将对象变量传递给过程时，仅引用指针被复制。  
  
-   **分配执行任何操作。** 你可以将值分配[执行任何操作](../../../../visual-basic/language-reference/nothing.md)为结构变量，但此实例将继续与变量相关联。 仍可以调用其方法并访问其数据元素，但分配重新初始化变量的元素。  
  
     相反，如果对象变量设置为`Nothing`、 将其从任何类实例，断开关联和不能通过变量访问任何成员，直到将另一个实例分配给它。  
  
-   **多个实例。** 对象变量可以在不同时间赋给它的不同的类实例，并且多个对象变量就可以在同一时间指同一个类实例。 对类成员的值所做的更改会影响时通过指向同一个实例的另一个变量来访问这些成员。  
  
     结构元素，但是，将独立于其自身实例。 为其值的更改不会反映在任何其他结构变量，即使在其他情况下的相同`Structure`声明。  
  
-   **相等性。** 与的元素的测试，必须执行两个结构相等性测试。 可以使用比较两个对象变量<xref:System.Object.Equals%2A>方法。 <xref:System.Object.Equals%2A>指示两个变量是否指向同一个实例。  
  
## <a name="see-also"></a>另请参阅  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [结构和其他编程元素](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
