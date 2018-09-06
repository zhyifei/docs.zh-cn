---
title: 枚举和名称限定 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: cd07c883c576e917cf1aa5072505854bc906eb3f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857584"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="91aff-102">枚举和名称限定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91aff-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="91aff-103">通常情况下，在引用枚举成员，必须限定为枚举名称的成员名称。</span><span class="sxs-lookup"><span data-stu-id="91aff-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="91aff-104">例如，若要引用`Sunday`的成员在`Days`枚举，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="91aff-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="91aff-105">使用 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="91aff-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="91aff-106">您可以通过避免使用完全限定的名称添加`Imports`语句向你的代码，如以下示例所示的命名空间声明部分：</span><span class="sxs-lookup"><span data-stu-id="91aff-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 <span data-ttu-id="91aff-107">`Imports`语句导入的命名空间名称，从引用的项目和程序集和与该语句将出现的模块相同的项目。</span><span class="sxs-lookup"><span data-stu-id="91aff-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="91aff-108">一旦添加此语句，也可以引用到枚举成员，而无需限定，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="91aff-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 <span data-ttu-id="91aff-109">通过组织在枚举中的相关常量集，可以使用不同的上下文中相同的常量名称。</span><span class="sxs-lookup"><span data-stu-id="91aff-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="91aff-110">例如，可以使用相同的名称为在工作日的常数`Days`和`WorkDays`枚举。</span><span class="sxs-lookup"><span data-stu-id="91aff-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="91aff-111">如果使用`Imports`与枚举一起语句，您必须小心，避免不明确的引用。</span><span class="sxs-lookup"><span data-stu-id="91aff-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="91aff-112">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="91aff-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 <span data-ttu-id="91aff-113">假设`Monday`是两个成员`Days`枚举和`Workdays`枚举，此代码将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="91aff-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="91aff-114">若要避免不明确的引用，当涉及到单个常量时，有资格使用其枚举常量的名称。</span><span class="sxs-lookup"><span data-stu-id="91aff-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="91aff-115">下面的代码是指`Saturday`中的常量`Days`和`WorkDays`枚举。</span><span class="sxs-lookup"><span data-stu-id="91aff-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="91aff-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="91aff-116">See Also</span></span>  
 [<span data-ttu-id="91aff-117">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="91aff-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="91aff-118">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="91aff-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="91aff-119">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="91aff-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="91aff-120">如何： 循环访问在 Visual Basic 中枚举</span><span class="sxs-lookup"><span data-stu-id="91aff-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="91aff-121">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="91aff-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="91aff-122">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="91aff-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="91aff-123">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="91aff-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="91aff-124">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="91aff-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="91aff-125">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="91aff-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="91aff-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="91aff-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
