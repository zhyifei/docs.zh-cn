---
title: "如何︰ 声明常量 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
dev_langs:
- VB
helpviewer_keywords:
- Integer data type, declaring constants
- Single data type, declaring constants
- Const statement [Visual Basic], declaring constants
- procedures, declaration
- data types [Visual Basic], constants
- Long data type, declaring constants
- Visual Basic code, declaring variables and constants
- Double data type, declaring constants
- Boolean data type, declaring constants
- modules, declaring constants
- Byte data type, declaring constants
- constants, declaring
- Date data type, declaring constants
- String data type, declaring constants
- declaring constants, const keyword
- Currency data type, declaring constants and variants
- module-level constants and variables
- Object data type, declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: b7fc499336c2b5db3b4d2fe9c0cd11799ea0ad77
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="437d9-102">如何：声明常量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="437d9-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="437d9-103">您使用`Const`语句声明一个常量，并将其值设置。</span><span class="sxs-lookup"><span data-stu-id="437d9-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="437d9-104">通过声明一个常量，您将有意义的名称分配给一个值。</span><span class="sxs-lookup"><span data-stu-id="437d9-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="437d9-105">一旦声明为一个常量，不能修改或分配一个新值。</span><span class="sxs-lookup"><span data-stu-id="437d9-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="437d9-106">声明是固定的过程中或在模块、 类或结构的声明部分。</span><span class="sxs-lookup"><span data-stu-id="437d9-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="437d9-107">类或结构级常量`Private`默认情况下，但也可能声明为`Public`， `Friend`， `Protected`，或`Protected Friend`为相应的代码访问级别。</span><span class="sxs-lookup"><span data-stu-id="437d9-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="437d9-108">常量必须具有有效的符号名称 （都具有相同规则与用于创建变量的名称） 和构成的数值或字符串常量及操作 （但不包括函数调用） 表达式。</span><span class="sxs-lookup"><span data-stu-id="437d9-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="437d9-109">若要声明常量</span><span class="sxs-lookup"><span data-stu-id="437d9-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="437d9-110">编写一个包含访问说明符的声明`Const`关键字和一个表达式，如下面的示例中所示︰</span><span class="sxs-lookup"><span data-stu-id="437d9-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     <span data-ttu-id="437d9-111">[!code-vb[VbEnumsTask #&8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="437d9-111">[!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span></span>  
  
     <span data-ttu-id="437d9-112">当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`和[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，您必须通过指定数据类型显式声明一个常量 (`Boolean`， `Byte`， `Char`， `DateTime`， `Decimal`， `Double`， `Integer`， `Long`， `Short`， `Single`，或`String`)。</span><span class="sxs-lookup"><span data-stu-id="437d9-112">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="437d9-113">当`Option Infer`是`On`或`Option Strict`是`Off`，您可以声明变量，而无需指定数据类型为`As`子句。</span><span class="sxs-lookup"><span data-stu-id="437d9-113">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="437d9-114">编译器确定的常量表达式的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="437d9-114">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="437d9-115">有关详细信息，请参阅[常量和文本数据类型](constant-and-literal-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="437d9-115">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="437d9-116">若要声明一个常量，它具有显式声明的数据类型</span><span class="sxs-lookup"><span data-stu-id="437d9-116">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="437d9-117">编写一个包含的声明`As`关键字和显式数据类型，如下面的示例中所示︰</span><span class="sxs-lookup"><span data-stu-id="437d9-117">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     <span data-ttu-id="437d9-118">[!code-vb[VbEnumsTask #&9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="437d9-118">[!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span></span>  
  
     <span data-ttu-id="437d9-119">尽管您的代码的可读性更高，如果您声明单个常量每行，您可以在单独的行，声明多个常量。</span><span class="sxs-lookup"><span data-stu-id="437d9-119">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="437d9-120">如果您在单独的行声明多个常数，它们必须都具有相同的访问级别 (`Public`， `Private`， `Friend`， `Protected`，或`Protected Friend`)。</span><span class="sxs-lookup"><span data-stu-id="437d9-120">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="437d9-121">若要在单独的行声明多个常数</span><span class="sxs-lookup"><span data-stu-id="437d9-121">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="437d9-122">分隔声明用逗号和空格，如以下示例所示︰</span><span class="sxs-lookup"><span data-stu-id="437d9-122">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="437d9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="437d9-123">See Also</span></span>  
 <span data-ttu-id="437d9-124">[Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="437d9-124">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="437d9-125"> [常量和 Literal 数据类型](constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="437d9-125"> [Constant and Literal Data Types](constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="437d9-126"> [常量概述](constants-overview.md)
 [如何︰ 声明常量](how-to-declare-a-constant.md)
 [用户定义的常量](user-defined-constants.md)
 [常量和 Literal 数据类型](constant-and-literal-data-types.md)
 [How to︰ 相关的常量值组合在一起](how-to-group-related-constant-values-together.md)
 [枚举概述](enumerations-overview.md)
 [如何︰ 声明枚举](how-to-declare-enumerations.md)
 [如何︰ 为枚举成员，请参阅](how-to-refer-to-an-enumeration-member.md)
 [枚举和名称限定](enumerations-and-name-qualification.md)
 [如何︰ 循环访问枚举](how-to-iterate-through-an-enumeration.md)
 [如何︰ 确定字符串枚举值相关联](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [何时使用枚举](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="437d9-126"> [Constants Overview](constants-overview.md)
 [How to: Declare A Constant](how-to-declare-a-constant.md)
 [User-Defined Constants](user-defined-constants.md)
 [Constant and Literal Data Types](constant-and-literal-data-types.md)
 [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md)
 [Enumerations Overview](enumerations-overview.md)
 [How to: Declare Enumerations](how-to-declare-enumerations.md)
 [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md)
 [Enumerations and Name Qualification](enumerations-and-name-qualification.md)
 [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md)
 [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 <span data-ttu-id="437d9-127">[枚举概述](enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="437d9-127">[Enumerations Overview](enumerations-overview.md) </span></span>  
<span data-ttu-id="437d9-128"> [常量概述](constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="437d9-128"> [Constants Overview](constants-overview.md) </span></span>  
<span data-ttu-id="437d9-129"> [如何︰ 声明枚举](how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="437d9-129"> [How to: Declare an Enumeration](how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="437d9-130"> [枚举和名称限定](enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="437d9-130"> [Enumerations and Name Qualification](enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="437d9-131"> [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="437d9-131"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="437d9-132"> [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="437d9-132"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

