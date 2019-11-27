---
title: 如何：声明枚举
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354049"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="d7023-102">如何：声明枚举 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7023-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="d7023-103">在类或模块的声明部分中，使用 `Enum` 语句创建枚举。</span><span class="sxs-lookup"><span data-stu-id="d7023-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="d7023-104">不能在方法中声明枚举。</span><span class="sxs-lookup"><span data-stu-id="d7023-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="d7023-105">若要指定适当的访问级别，请使用 `Private`、`Protected`、`Friend`或 `Public`。</span><span class="sxs-lookup"><span data-stu-id="d7023-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="d7023-106">`Enum` 类型具有名称、基础类型和字段集，每个字段都表示一个常量。</span><span class="sxs-lookup"><span data-stu-id="d7023-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="d7023-107">该名称必须是有效的 Visual Basic .NET 限定符。</span><span class="sxs-lookup"><span data-stu-id="d7023-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="d7023-108">基础类型必须是整数类型之一-`Byte`、`Short`、`Long` 或 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="d7023-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="d7023-109">默认值为 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="d7023-109">`Integer` is the default.</span></span> <span data-ttu-id="d7023-110">枚举总是强类型化的，并且不能与整数类型互换。</span><span class="sxs-lookup"><span data-stu-id="d7023-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="d7023-111">枚举的值不能为浮点值。</span><span class="sxs-lookup"><span data-stu-id="d7023-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="d7023-112">如果为枚举分配了 `Option Strict On`的浮点值，则会产生编译器错误。</span><span class="sxs-lookup"><span data-stu-id="d7023-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="d7023-113">如果 `Off``Option Strict`，则该值会自动转换为 `Enum` 类型。</span><span class="sxs-lookup"><span data-stu-id="d7023-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="d7023-114">有关名称的信息，以及如何使用 `Imports` 语句使名称限定不必要，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="d7023-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="d7023-115">声明枚举</span><span class="sxs-lookup"><span data-stu-id="d7023-115">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="d7023-116">编写包含代码访问级别、`Enum` 关键字和有效名称的声明，如下面的示例所示，其中每个都声明了不同的 `Enum`。</span><span class="sxs-lookup"><span data-stu-id="d7023-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="d7023-117">定义枚举中的常量。</span><span class="sxs-lookup"><span data-stu-id="d7023-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="d7023-118">默认情况下，枚举中的第一个常量被初始化为 `0`，后面的常量被初始化为比上一个常数大1的值。</span><span class="sxs-lookup"><span data-stu-id="d7023-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="d7023-119">例如，下面的枚举 `Days`包含一个名为 `Sunday` 的常量，该常量的值为 `0`、一个名为 `Monday`、值为 `1`、一个名为 `Tuesday`、值为 `2`的常量等。</span><span class="sxs-lookup"><span data-stu-id="d7023-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="d7023-120">可以使用赋值语句将值显式分配给枚举中的常量。</span><span class="sxs-lookup"><span data-stu-id="d7023-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="d7023-121">可以分配任何整数值，包括负数。</span><span class="sxs-lookup"><span data-stu-id="d7023-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="d7023-122">例如，您可能希望值小于零的常量表示错误条件。</span><span class="sxs-lookup"><span data-stu-id="d7023-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="d7023-123">在以下枚举中，会将值显式赋给常量 `Invalid` `–1`，并为常量 `Sunday` 分配值 `0`。</span><span class="sxs-lookup"><span data-stu-id="d7023-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="d7023-124">由于它是枚举中的第一个常数，因此 `Saturday` 也初始化为 `0`值。</span><span class="sxs-lookup"><span data-stu-id="d7023-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="d7023-125">`1` `Monday` 的值（一个大于 `Sunday`的值）;`Tuesday` 的值 `2`等。</span><span class="sxs-lookup"><span data-stu-id="d7023-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="d7023-126">将枚举声明为显式类型</span><span class="sxs-lookup"><span data-stu-id="d7023-126">To declare an enumeration as an explicit type</span></span>  
  
- <span data-ttu-id="d7023-127">使用 `As` 子句指定枚举的类型，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="d7023-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d7023-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7023-128">See also</span></span>

- [<span data-ttu-id="d7023-129">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="d7023-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="d7023-130">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="d7023-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="d7023-131">如何：在 Visual Basic 中循环访问枚举</span><span class="sxs-lookup"><span data-stu-id="d7023-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="d7023-132">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="d7023-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="d7023-133">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="d7023-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="d7023-134">常量概述</span><span class="sxs-lookup"><span data-stu-id="d7023-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="d7023-135">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="d7023-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="d7023-136">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="d7023-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
