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
ms.openlocfilehash: ce45e4df7f74cd68bde0fb2adba10197a11edb1b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394309"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="93e9b-102">如何：声明常量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93e9b-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="93e9b-103">您使用`Const`语句声明一个常量，并将其值设置。</span><span class="sxs-lookup"><span data-stu-id="93e9b-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="93e9b-104">通过声明一个常量，您将有意义的名称分配给一个值。</span><span class="sxs-lookup"><span data-stu-id="93e9b-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="93e9b-105">一旦声明一个常量，不能修改或分配一个新值。</span><span class="sxs-lookup"><span data-stu-id="93e9b-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="93e9b-106">声明是固定的过程中或在模块、 类或结构的声明部分。</span><span class="sxs-lookup"><span data-stu-id="93e9b-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="93e9b-107">类或结构级别的常数`Private`默认情况下，但也可能作为声明`Public`， `Friend`， `Protected`，或`Protected Friend`的适当级别的代码访问。</span><span class="sxs-lookup"><span data-stu-id="93e9b-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="93e9b-108">常量必须具有有效的符号名称 （规则是与用于创建变量的名称相同） 和的数值或字符串常量和运算符 （但不包括函数调用） 组成的表达式。</span><span class="sxs-lookup"><span data-stu-id="93e9b-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="93e9b-109">若要声明常量</span><span class="sxs-lookup"><span data-stu-id="93e9b-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="93e9b-110">编写包含访问说明符声明`Const`关键字和一个表达式，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="93e9b-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     <span data-ttu-id="93e9b-111">当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`并[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，您必须通过指定数据类型显式声明常量 (`Boolean`， `Byte`， `Char`， `DateTime`， `Decimal`， `Double`， `Integer`， `Long`， `Short`， `Single`，或`String`)。</span><span class="sxs-lookup"><span data-stu-id="93e9b-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="93e9b-112">当`Option Infer`是`On`或`Option Strict`是`Off`，你可以声明变量，而无需指定数据类型为`As`子句。</span><span class="sxs-lookup"><span data-stu-id="93e9b-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="93e9b-113">编译器确定的常量表达式的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="93e9b-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="93e9b-114">有关详细信息，请参阅[常量和文本数据类型](constant-and-literal-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="93e9b-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="93e9b-115">若要声明一个常量，它具有显式声明的数据类型</span><span class="sxs-lookup"><span data-stu-id="93e9b-115">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="93e9b-116">编写的声明，包括`As`关键字和显式数据类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="93e9b-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     <span data-ttu-id="93e9b-117">虽然你的代码是声明单个常量每行更具可读性，可以在单个行上声明多个常量。</span><span class="sxs-lookup"><span data-stu-id="93e9b-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="93e9b-118">如果在单个行上声明多个常量，它们必须都具有相同的访问级别 (`Public`， `Private`， `Friend`， `Protected`，或`Protected Friend`)。</span><span class="sxs-lookup"><span data-stu-id="93e9b-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="93e9b-119">若要在单个行上声明多个常量</span><span class="sxs-lookup"><span data-stu-id="93e9b-119">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="93e9b-120">单独使用一个逗号和空格，如以下示例所示的声明：</span><span class="sxs-lookup"><span data-stu-id="93e9b-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="93e9b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="93e9b-121">See Also</span></span>  
 [<span data-ttu-id="93e9b-122">Const 语句</span><span class="sxs-lookup"><span data-stu-id="93e9b-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="93e9b-123">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="93e9b-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)  
 <span data-ttu-id="93e9b-124">[常量概述](constants-overview.md)[如何： 声明常量](how-to-declare-a-constant.md)[用户定义的常量](user-defined-constants.md)[常量和 Literal 数据类型](constant-and-literal-data-types.md)[如何： 组相关的常量值组合在一起](how-to-group-related-constant-values-together.md)[枚举概述](enumerations-overview.md)[如何： 声明枚举](how-to-declare-enumerations.md)[如何： 为枚举成员，请参阅](how-to-refer-to-an-enumeration-member.md)[枚举和名称限定](enumerations-and-name-qualification.md)[如何： 循环访问枚举](how-to-iterate-through-an-enumeration.md)[如何： 确定与枚举值关联的字符串](how-to-determine-the-string-associated-with-an-enumeration-value.md)[何时使用枚举](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="93e9b-124">[Constants Overview](constants-overview.md) [How to: Declare A Constant](how-to-declare-a-constant.md) [User-Defined Constants](user-defined-constants.md) [Constant and Literal Data Types](constant-and-literal-data-types.md) [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md) [Enumerations Overview](enumerations-overview.md) [How to: Declare Enumerations](how-to-declare-enumerations.md) [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md) [Enumerations and Name Qualification](enumerations-and-name-qualification.md) [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md) [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md) [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 [<span data-ttu-id="93e9b-125">枚举概述</span><span class="sxs-lookup"><span data-stu-id="93e9b-125">Enumerations Overview</span></span>](enumerations-overview.md)  
 [<span data-ttu-id="93e9b-126">常量概述</span><span class="sxs-lookup"><span data-stu-id="93e9b-126">Constants Overview</span></span>](constants-overview.md)  
 [<span data-ttu-id="93e9b-127">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="93e9b-127">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)  
 [<span data-ttu-id="93e9b-128">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="93e9b-128">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)  
 [<span data-ttu-id="93e9b-129">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="93e9b-129">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="93e9b-130">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="93e9b-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
