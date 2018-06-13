---
title: 确定对象类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a9852998abeae67b2a0e9dc3ffc85318ce5045da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648289"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="1966a-102">确定对象类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1966a-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="1966a-103">一般的对象变量 (即，变量声明为`Object`) 可以包含来自任何类的对象。</span><span class="sxs-lookup"><span data-stu-id="1966a-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="1966a-104">使用类型的变量时`Object`，可能需要采取不同的基于对象的类; 例如，某些对象可能不支持特定属性或方法。</span><span class="sxs-lookup"><span data-stu-id="1966a-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="1966a-105">Visual Basic 提供以下两种方法确定哪种类型的对象存储在一个对象变量：`TypeName`函数和`TypeOf...Is`运算符。</span><span class="sxs-lookup"><span data-stu-id="1966a-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="1966a-106">E，TypeOf...是</span><span class="sxs-lookup"><span data-stu-id="1966a-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="1966a-107">`TypeName`函数返回一个字符串，并是最佳选择，当你需要存储或显示类对象的名称，如下面的代码段中所示：</span><span class="sxs-lookup"><span data-stu-id="1966a-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 <span data-ttu-id="1966a-108">`TypeOf...Is`运算符是用于测试的对象类型的最佳选择，因为它是比等效的字符串比较使用快得多`TypeName`。</span><span class="sxs-lookup"><span data-stu-id="1966a-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="1966a-109">下面的代码片段使用`TypeOf...Is`内`If...Then...Else`语句：</span><span class="sxs-lookup"><span data-stu-id="1966a-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 <span data-ttu-id="1966a-110">需要注意的一点是因为此处。</span><span class="sxs-lookup"><span data-stu-id="1966a-110">A word of caution is due here.</span></span> <span data-ttu-id="1966a-111">`TypeOf...Is`运算符返回`True`如果一个对象的特定类型，或从特定类型派生。</span><span class="sxs-lookup"><span data-stu-id="1966a-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="1966a-112">几乎所有操作都使用 Visual Basic 涉及对象，其中包括一些通常不被视为对象，如字符串和整数的元素。</span><span class="sxs-lookup"><span data-stu-id="1966a-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="1966a-113">这些对象派生自和继承方法从<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="1966a-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="1966a-114">当传递`Integer`和计算与`Object`、`TypeOf...Is`运算符返回`True`。</span><span class="sxs-lookup"><span data-stu-id="1966a-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="1966a-115">下面的示例报告参数`InParam`既是`Object`和`Integer`:</span><span class="sxs-lookup"><span data-stu-id="1966a-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 <span data-ttu-id="1966a-116">下面的示例使用这两个`TypeOf...Is`和`TypeName`来确定对象中传递给它的类型`Ctrl`自变量。</span><span class="sxs-lookup"><span data-stu-id="1966a-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="1966a-117">`TestObject`过程调用`ShowType`与三种不同的控件。</span><span class="sxs-lookup"><span data-stu-id="1966a-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="1966a-118">运行示例</span><span class="sxs-lookup"><span data-stu-id="1966a-118">To run the example</span></span>  
  
1.  <span data-ttu-id="1966a-119">创建新的 Windows 应用程序项目并添加<xref:System.Windows.Forms.Button>控件，<xref:System.Windows.Forms.CheckBox>控件，和一个<xref:System.Windows.Forms.RadioButton>到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="1966a-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="1966a-120">从你的窗体上的按钮，调用`TestObject`过程。</span><span class="sxs-lookup"><span data-stu-id="1966a-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="1966a-121">向窗体中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="1966a-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1966a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1966a-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [<span data-ttu-id="1966a-123">使用字符串名调用属性或方法</span><span class="sxs-lookup"><span data-stu-id="1966a-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [<span data-ttu-id="1966a-124">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="1966a-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="1966a-125">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="1966a-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="1966a-126">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="1966a-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="1966a-127">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="1966a-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
