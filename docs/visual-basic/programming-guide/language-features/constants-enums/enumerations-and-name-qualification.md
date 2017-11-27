---
title: "枚举和名称限定 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb97d6a8f4b7e81f2b759010214e200ec63ff21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="d39bf-102">枚举和名称限定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d39bf-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="d39bf-103">通常情况下，当引用时枚举的成员，你必须限定枚举名称的成员名称。</span><span class="sxs-lookup"><span data-stu-id="d39bf-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="d39bf-104">例如，若要引用`Sunday`的成员你`Days`枚举，你将使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d39bf-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="d39bf-105">使用导入语句</span><span class="sxs-lookup"><span data-stu-id="d39bf-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="d39bf-106">你可以避免使用完全限定的名加上`Imports`语句与你的代码，如以下示例所示的命名空间声明部分：</span><span class="sxs-lookup"><span data-stu-id="d39bf-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 <span data-ttu-id="d39bf-107">`Imports`语句导入命名空间名称，从被引用的项目和程序集和与语句出现在其中的模块相同的项目。</span><span class="sxs-lookup"><span data-stu-id="d39bf-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="d39bf-108">此语句添加后，您可以参考你的枚举成员，而无需限定，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="d39bf-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 <span data-ttu-id="d39bf-109">通过几组相关常数在枚举中的组织，你可以使用相同的常数名在不同上下文中。</span><span class="sxs-lookup"><span data-stu-id="d39bf-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="d39bf-110">例如，可以使用相同的名称中对工作日常数`Days`和`WorkDays`枚举。</span><span class="sxs-lookup"><span data-stu-id="d39bf-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="d39bf-111">如果你使用`Imports`与枚举一起语句，必须注意以避免不明确的引用。</span><span class="sxs-lookup"><span data-stu-id="d39bf-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="d39bf-112">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="d39bf-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 <span data-ttu-id="d39bf-113">假设`Monday`是的成员`Days`枚举和`Workdays`枚举，此代码生成一个编译器错误。</span><span class="sxs-lookup"><span data-stu-id="d39bf-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="d39bf-114">若要在单个常数引用时，请避免不明确的引用，限定其枚举常量的名称。</span><span class="sxs-lookup"><span data-stu-id="d39bf-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="d39bf-115">下面的代码是指`Saturday`中的常量`Days`和`WorkDays`枚举。</span><span class="sxs-lookup"><span data-stu-id="d39bf-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d39bf-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d39bf-116">See Also</span></span>  
 [<span data-ttu-id="d39bf-117">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="d39bf-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="d39bf-118">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="d39bf-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="d39bf-119">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="d39bf-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="d39bf-120">如何： 循环访问 Visual Basic 中的一个枚举</span><span class="sxs-lookup"><span data-stu-id="d39bf-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="d39bf-121">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="d39bf-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="d39bf-122">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="d39bf-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="d39bf-123">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="d39bf-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="d39bf-124">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="d39bf-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="d39bf-125">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="d39bf-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="d39bf-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="d39bf-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
