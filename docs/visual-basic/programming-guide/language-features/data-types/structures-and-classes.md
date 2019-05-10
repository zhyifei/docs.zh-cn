---
title: 结构和类 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: b947109f99d94b0ecb1d798835c311f2374e96fc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601038"
---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="90b19-102">结构和类 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90b19-102">Structures and Classes (Visual Basic)</span></span>
<span data-ttu-id="90b19-103">Visual Basic 统一的结构和类，因此这两个实体支持的大多数功能相同的语法。</span><span class="sxs-lookup"><span data-stu-id="90b19-103">Visual Basic unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="90b19-104">但是，也有重要区别结构和类。</span><span class="sxs-lookup"><span data-stu-id="90b19-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="90b19-105">类具有的优点是引用类型，传递一个引用是传递的所有数据的结构变量比效率更高。</span><span class="sxs-lookup"><span data-stu-id="90b19-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="90b19-106">但是，结构不需要全局堆上的内存的分配。</span><span class="sxs-lookup"><span data-stu-id="90b19-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="90b19-107">由于不能继承自一个结构，结构仅应该用于不需要进行扩展的对象。</span><span class="sxs-lookup"><span data-stu-id="90b19-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="90b19-108">当你想要创建的对象具有小型实例大小，并考虑类和结构的性能特征，请使用结构。</span><span class="sxs-lookup"><span data-stu-id="90b19-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="90b19-109">相似之处</span><span class="sxs-lookup"><span data-stu-id="90b19-109">Similarities</span></span>  
 <span data-ttu-id="90b19-110">结构和类是在以下方面类似：</span><span class="sxs-lookup"><span data-stu-id="90b19-110">Structures and classes are similar in the following respects:</span></span>  
  
- <span data-ttu-id="90b19-111">两者都*容器*类型，这意味着它们包含其他类型作为成员。</span><span class="sxs-lookup"><span data-stu-id="90b19-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
- <span data-ttu-id="90b19-112">都具有成员，它们可以包括构造函数、 方法、 属性、 字段、 常量、 枚举、 事件和事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="90b19-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="90b19-113">但是，不要混淆的已声明这些成员*元素*的结构。</span><span class="sxs-lookup"><span data-stu-id="90b19-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
- <span data-ttu-id="90b19-114">这两者的成员可以分别有不同的访问级别。</span><span class="sxs-lookup"><span data-stu-id="90b19-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="90b19-115">例如，可以声明一个成员`Public`和另一个`Private`。</span><span class="sxs-lookup"><span data-stu-id="90b19-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
- <span data-ttu-id="90b19-116">同时可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="90b19-116">Both can implement interfaces.</span></span>  
  
- <span data-ttu-id="90b19-117">使用或不带参数，都可以具有共享构造函数。</span><span class="sxs-lookup"><span data-stu-id="90b19-117">Both can have shared constructors, with or without parameters.</span></span>  
  
- <span data-ttu-id="90b19-118">两者都可以公开*默认属性*，前提是该属性带有至少一个参数。</span><span class="sxs-lookup"><span data-stu-id="90b19-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
- <span data-ttu-id="90b19-119">同时可以声明和引发事件，并且两者都可以声明委托。</span><span class="sxs-lookup"><span data-stu-id="90b19-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="90b19-120">差异</span><span class="sxs-lookup"><span data-stu-id="90b19-120">Differences</span></span>  
 <span data-ttu-id="90b19-121">结构和类在以下方面有所不同：</span><span class="sxs-lookup"><span data-stu-id="90b19-121">Structures and classes differ in the following particulars:</span></span>  
  
- <span data-ttu-id="90b19-122">结构是否*值类型*; 类是*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="90b19-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="90b19-123">结构类型的变量包含结构的数据，而不是那样包含对将数据作为类类型的引用。</span><span class="sxs-lookup"><span data-stu-id="90b19-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
- <span data-ttu-id="90b19-124">结构使用堆栈分配;类使用堆分配。</span><span class="sxs-lookup"><span data-stu-id="90b19-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
- <span data-ttu-id="90b19-125">结构的所有元素都都`Public`默认情况下; 类变量和都常量`Private`默认情况下，而其他类成员都是`Public`默认情况下。</span><span class="sxs-lookup"><span data-stu-id="90b19-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="90b19-126">此行为对于类成员提供了与默认值的 Visual Basic 6.0 系统的兼容性。</span><span class="sxs-lookup"><span data-stu-id="90b19-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
- <span data-ttu-id="90b19-127">一种结构必须具有至少一个非共享变量或非共享、 非自定义事件的元素;一个类可以是完全为空。</span><span class="sxs-lookup"><span data-stu-id="90b19-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
- <span data-ttu-id="90b19-128">结构元素不能声明为`Protected`; 可以类成员。</span><span class="sxs-lookup"><span data-stu-id="90b19-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
- <span data-ttu-id="90b19-129">结构过程可以处理事件，仅当[共享](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub`过程中，并仅通过的方式[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md); 任何类的过程可以处理事件，使用任一[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)关键字或`AddHandler`语句。</span><span class="sxs-lookup"><span data-stu-id="90b19-129">A structure procedure can handle events only if it is a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="90b19-130">有关详细信息，请参阅[事件](../../../../visual-basic/programming-guide/language-features/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="90b19-130">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
- <span data-ttu-id="90b19-131">结构变量声明不能指定初始值设定项或数组; 的初始大小类的变量声明可以。</span><span class="sxs-lookup"><span data-stu-id="90b19-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
- <span data-ttu-id="90b19-132">结构隐式继承自<xref:System.ValueType?displayProperty=nameWithType>类，并从任何其他类型; 不能继承类可以继承自任何类或类以外<xref:System.ValueType?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="90b19-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=nameWithType> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="90b19-133">结构是不可继承;类是。</span><span class="sxs-lookup"><span data-stu-id="90b19-133">Structures are not inheritable; classes are.</span></span>  
  
- <span data-ttu-id="90b19-134">永远不会终止结构，因此公共语言运行时 (CLR) 永远不会调用<xref:System.Object.Finalize%2A>任何结构; 方法由垃圾回收器 (GC)，它调用终止类<xref:System.Object.Finalize%2A>上检测到有任何活动的引用时的类剩余。</span><span class="sxs-lookup"><span data-stu-id="90b19-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
- <span data-ttu-id="90b19-135">结构不需要构造函数;类一样。</span><span class="sxs-lookup"><span data-stu-id="90b19-135">A structure does not require a constructor; a class does.</span></span>  
  
- <span data-ttu-id="90b19-136">结构可以具有非共享的构造函数仅当它们采用参数;类可以让它们使用或不带参数。</span><span class="sxs-lookup"><span data-stu-id="90b19-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="90b19-137">每个结构具有不带参数的隐式公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="90b19-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="90b19-138">此构造函数初始化结构的所有数据元素为其默认值。</span><span class="sxs-lookup"><span data-stu-id="90b19-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="90b19-139">不能重新定义此行为。</span><span class="sxs-lookup"><span data-stu-id="90b19-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="90b19-140">实例和变量</span><span class="sxs-lookup"><span data-stu-id="90b19-140">Instances and Variables</span></span>  
 <span data-ttu-id="90b19-141">由于结构是值类型，每个结构变量是永久绑定到单个结构实例。</span><span class="sxs-lookup"><span data-stu-id="90b19-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="90b19-142">类是引用类型，但对象变量可以在不同时间指不同的类实例。</span><span class="sxs-lookup"><span data-stu-id="90b19-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="90b19-143">这一区别在通过以下方式影响你的结构和类的使用情况：</span><span class="sxs-lookup"><span data-stu-id="90b19-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
- <span data-ttu-id="90b19-144">**初始化。**</span><span class="sxs-lookup"><span data-stu-id="90b19-144">**Initialization.**</span></span> <span data-ttu-id="90b19-145">结构变量隐式包含使用该结构的无参数构造函数的元素的初始化。</span><span class="sxs-lookup"><span data-stu-id="90b19-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="90b19-146">因此，`Dim s As struct1`等效于`Dim s As struct1 = New struct1()`。</span><span class="sxs-lookup"><span data-stu-id="90b19-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
- <span data-ttu-id="90b19-147">**分配变量。**</span><span class="sxs-lookup"><span data-stu-id="90b19-147">**Assigning Variables.**</span></span> <span data-ttu-id="90b19-148">当您将一个结构变量分配到另一个，或将结构实例传递给过程自变量时，变量的所有元素的当前值复制到新结构。</span><span class="sxs-lookup"><span data-stu-id="90b19-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="90b19-149">当将一个对象变量分配给另一个，或将对象变量传递给过程时，复制仅引用指针。</span><span class="sxs-lookup"><span data-stu-id="90b19-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
- <span data-ttu-id="90b19-150">**分配执行任何操作。**</span><span class="sxs-lookup"><span data-stu-id="90b19-150">**Assigning Nothing.**</span></span> <span data-ttu-id="90b19-151">可以分配值[Nothing](../../../../visual-basic/language-reference/nothing.md)为结构变量，但该实例将继续与变量相关联。</span><span class="sxs-lookup"><span data-stu-id="90b19-151">You can assign the value [Nothing](../../../../visual-basic/language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="90b19-152">仍可以调用其方法和访问其数据元素，但变量元素被重新初始化由赋值。</span><span class="sxs-lookup"><span data-stu-id="90b19-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="90b19-153">相反，如果对象变量设置为`Nothing`、 取消关联任何类的实例，并不能通过变量访问任何成员，直到将另一个实例分配给它。</span><span class="sxs-lookup"><span data-stu-id="90b19-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
- <span data-ttu-id="90b19-154">**多个实例。**</span><span class="sxs-lookup"><span data-stu-id="90b19-154">**Multiple Instances.**</span></span> <span data-ttu-id="90b19-155">对象变量可以在不同的时间，赋给它的另一个类实例，并且多个对象变量可以在同一时间引用相同的类实例。</span><span class="sxs-lookup"><span data-stu-id="90b19-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="90b19-156">对类成员的值所做的更改会影响时通过指向同一个实例的另一个变量来访问这些成员。</span><span class="sxs-lookup"><span data-stu-id="90b19-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="90b19-157">结构元素，但是，是独立于其自身实例。</span><span class="sxs-lookup"><span data-stu-id="90b19-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="90b19-158">为其值的更改未反映在任何其他结构变量，即使在相同的其他实例中`Structure`声明。</span><span class="sxs-lookup"><span data-stu-id="90b19-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
- <span data-ttu-id="90b19-159">**相等。**</span><span class="sxs-lookup"><span data-stu-id="90b19-159">**Equality.**</span></span> <span data-ttu-id="90b19-160">逐个元素测试，必须执行两个结构相等性测试。</span><span class="sxs-lookup"><span data-stu-id="90b19-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="90b19-161">可以使用比较两个对象变量<xref:System.Object.Equals%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="90b19-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="90b19-162"><xref:System.Object.Equals%2A> 指示两个变量是否指向同一个实例。</span><span class="sxs-lookup"><span data-stu-id="90b19-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b19-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="90b19-163">See also</span></span>

- [<span data-ttu-id="90b19-164">数据类型</span><span class="sxs-lookup"><span data-stu-id="90b19-164">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="90b19-165">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="90b19-165">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="90b19-166">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="90b19-166">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="90b19-167">结构</span><span class="sxs-lookup"><span data-stu-id="90b19-167">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="90b19-168">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="90b19-168">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="90b19-169">结构和其他编程元素</span><span class="sxs-lookup"><span data-stu-id="90b19-169">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="90b19-170">对象和类</span><span class="sxs-lookup"><span data-stu-id="90b19-170">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
