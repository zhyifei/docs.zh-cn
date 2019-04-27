---
title: 如何：声明常量 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: 95bfa3da5499c518dad0c235b539784fee2bb522
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61975970"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="9a1c8-102">如何：声明常量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a1c8-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="9a1c8-103">您使用`Const`语句声明一个常量，并将其值设置。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="9a1c8-104">通过声明一个常量，您将有意义的名称分配给一个值。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="9a1c8-105">一旦声明一个常量，不能修改或分配一个新值。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="9a1c8-106">声明是固定的过程中或在模块、 类或结构的声明部分。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="9a1c8-107">类或结构级别的常数`Private`默认情况下，但也可能作为声明`Public`， `Friend`， `Protected`，或`Protected Friend`的适当级别的代码访问。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="9a1c8-108">常量必须具有有效的符号名称 （规则是与用于创建变量的名称相同） 和的数值或字符串常量和运算符 （但不包括函数调用） 组成的表达式。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="9a1c8-109">若要声明常量</span><span class="sxs-lookup"><span data-stu-id="9a1c8-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="9a1c8-110">编写包含访问说明符声明`Const`关键字和一个表达式，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="9a1c8-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     <span data-ttu-id="9a1c8-111">当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`并[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，您必须通过指定数据类型显式声明常量 (`Boolean`， `Byte`， `Char`， `DateTime`， `Decimal`， `Double`， `Integer`， `Long`， `Short`， `Single`，或`String`)。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="9a1c8-112">当`Option Infer`是`On`或`Option Strict`是`Off`，你可以声明变量，而无需指定数据类型为`As`子句。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="9a1c8-113">编译器确定的常量表达式的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="9a1c8-114">有关详细信息，请参阅[常量和文本数据类型](constant-and-literal-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="9a1c8-115">若要声明一个常量，它具有显式声明的数据类型</span><span class="sxs-lookup"><span data-stu-id="9a1c8-115">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="9a1c8-116">编写的声明，包括`As`关键字和显式数据类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="9a1c8-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     <span data-ttu-id="9a1c8-117">虽然你的代码是声明单个常量每行更具可读性，可以在单个行上声明多个常量。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="9a1c8-118">如果在单个行上声明多个常量，它们必须都具有相同的访问级别 (`Public`， `Private`， `Friend`， `Protected`，或`Protected Friend`)。</span><span class="sxs-lookup"><span data-stu-id="9a1c8-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="9a1c8-119">若要在单个行上声明多个常量</span><span class="sxs-lookup"><span data-stu-id="9a1c8-119">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="9a1c8-120">单独使用一个逗号和空格，如以下示例所示的声明：</span><span class="sxs-lookup"><span data-stu-id="9a1c8-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9a1c8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a1c8-121">See also</span></span>

- [<span data-ttu-id="9a1c8-122">Const 语句</span><span class="sxs-lookup"><span data-stu-id="9a1c8-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="9a1c8-123">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="9a1c8-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="9a1c8-124">常量概述</span><span class="sxs-lookup"><span data-stu-id="9a1c8-124">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="9a1c8-125">如何：声明常量</span><span class="sxs-lookup"><span data-stu-id="9a1c8-125">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="9a1c8-126">用户定义的常量</span><span class="sxs-lookup"><span data-stu-id="9a1c8-126">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="9a1c8-127">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="9a1c8-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="9a1c8-128">如何：相关的常量值组合在一起</span><span class="sxs-lookup"><span data-stu-id="9a1c8-128">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)
- [<span data-ttu-id="9a1c8-129">枚举概述</span><span class="sxs-lookup"><span data-stu-id="9a1c8-129">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="9a1c8-130">如何：声明枚举</span><span class="sxs-lookup"><span data-stu-id="9a1c8-130">How to: Declare Enumerations</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="9a1c8-131">如何：为枚举成员，请参阅</span><span class="sxs-lookup"><span data-stu-id="9a1c8-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="9a1c8-132">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="9a1c8-132">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="9a1c8-133">如何：循环访问枚举</span><span class="sxs-lookup"><span data-stu-id="9a1c8-133">How to: Iterate Through An Enumeration</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="9a1c8-134">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="9a1c8-134">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="9a1c8-135">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="9a1c8-135">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

- [<span data-ttu-id="9a1c8-136">枚举概述</span><span class="sxs-lookup"><span data-stu-id="9a1c8-136">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="9a1c8-137">常量概述</span><span class="sxs-lookup"><span data-stu-id="9a1c8-137">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="9a1c8-138">如何：声明枚举</span><span class="sxs-lookup"><span data-stu-id="9a1c8-138">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="9a1c8-139">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="9a1c8-139">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="9a1c8-140">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="9a1c8-140">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="9a1c8-141">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="9a1c8-141">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
