---
title: "何时使用枚举 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3853950382fd4336c569f9d772aea3c1312f2ebc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="05dfc-102">何时使用枚举 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05dfc-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="05dfc-103">枚举提供了使用成组相关的常数的一个简单的办法。</span><span class="sxs-lookup"><span data-stu-id="05dfc-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="05dfc-104">一个枚举，或`Enum`，是一组值的符号名称。</span><span class="sxs-lookup"><span data-stu-id="05dfc-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="05dfc-105">枚举被视为数据类型，并可用于创建具有变量和属性的使用的常数的集。</span><span class="sxs-lookup"><span data-stu-id="05dfc-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="05dfc-106">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="05dfc-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="05dfc-107">当一个过程接受一组有限的变量时，请考虑使用枚举。</span><span class="sxs-lookup"><span data-stu-id="05dfc-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="05dfc-108">枚举可使更清晰且更具可读性的代码，特别是当使用有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="05dfc-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="05dfc-109">使用枚举的好处包括︰</span><span class="sxs-lookup"><span data-stu-id="05dfc-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="05dfc-110">这样可以减少错误引起的转置或键入数字。</span><span class="sxs-lookup"><span data-stu-id="05dfc-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="05dfc-111">便于在以后更改值。</span><span class="sxs-lookup"><span data-stu-id="05dfc-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="05dfc-112">使代码易于阅读，这意味着它不太可能错误的概率到其中。</span><span class="sxs-lookup"><span data-stu-id="05dfc-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="05dfc-113">确保向前兼容性。</span><span class="sxs-lookup"><span data-stu-id="05dfc-113">Ensures forward compatibility.</span></span> <span data-ttu-id="05dfc-114">借助枚举、 您的代码就很难，如果有人在将来更改的成员名称所对应的值失败。</span><span class="sxs-lookup"><span data-stu-id="05dfc-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="05dfc-115">命名的枚举</span><span class="sxs-lookup"><span data-stu-id="05dfc-115">Naming Enumerations</span></span>  
 <span data-ttu-id="05dfc-116">使用枚举成员的命名约定。</span><span class="sxs-lookup"><span data-stu-id="05dfc-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="05dfc-117">当[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]遇到枚举成员名称，如果其他引用的类型库包含相同的名称，可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="05dfc-117">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="05dfc-118">使用唯一的前缀，用于标识您的应用程序或组件中的值。</span><span class="sxs-lookup"><span data-stu-id="05dfc-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="05dfc-119">当引用时枚举的成员，必须限定成员名称为枚举名称，否则使用`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="05dfc-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="05dfc-120">有关详细信息，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="05dfc-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="05dfc-121">预定义的枚举</span><span class="sxs-lookup"><span data-stu-id="05dfc-121">Predefined Enumerations</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="05dfc-122">提供的预定义的枚举数，如`FirstDayOfWeek`和`MsgBoxResul`t，以便于您的代码。</span><span class="sxs-lookup"><span data-stu-id="05dfc-122"> provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResul`t, to facilitate your code.</span></span> <span data-ttu-id="05dfc-123">这些因素的列表，请参阅[常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="05dfc-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05dfc-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05dfc-124">See Also</span></span>  
 <span data-ttu-id="05dfc-125">[如何︰ 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="05dfc-125">[How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="05dfc-126"> [如何︰ 为枚举成员，请参阅](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="05dfc-126"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="05dfc-127"> [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="05dfc-127"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="05dfc-128"> [如何︰ 循环访问在 Visual Basic 中枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="05dfc-128"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="05dfc-129"> [如何︰ 确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="05dfc-129"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="05dfc-130"> [Enum 语句](../../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="05dfc-130"> [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="05dfc-131"> [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="05dfc-131"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
