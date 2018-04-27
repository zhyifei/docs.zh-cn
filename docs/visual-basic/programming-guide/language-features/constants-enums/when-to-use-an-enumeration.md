---
title: 何时使用枚举 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ab152687f4f9e4ba6bd032ae7c1352f65af715f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="a7ac5-102">何时使用枚举 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7ac5-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="a7ac5-103">枚举提供轻松使用成组的相关的常数。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="a7ac5-104">一个枚举，枚举，或`Enum`，是一组值的符号名称。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="a7ac5-105">枚举将被视为数据类型，并可用于创建使用变量和属性集使用的常数。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="a7ac5-106">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="a7ac5-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="a7ac5-107">当一个过程接受一组有限的变量时，请考虑使用枚举。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="a7ac5-108">枚举可使更清楚且更具可读性的代码，尤其是在使用有意义的名称时。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="a7ac5-109">使用枚举的好处包括：</span><span class="sxs-lookup"><span data-stu-id="a7ac5-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="a7ac5-110">这样可以减少错误引起的转置或键入数字。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="a7ac5-111">便于在以后更改值。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="a7ac5-112">使代码易于阅读，这意味着它很少出现错误的概率到其中。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="a7ac5-113">确保向前兼容性。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-113">Ensures forward compatibility.</span></span> <span data-ttu-id="a7ac5-114">枚举，与你的代码就很难如果有人在将来更改成员名称所对应的值失败。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="a7ac5-115">命名枚举</span><span class="sxs-lookup"><span data-stu-id="a7ac5-115">Naming Enumerations</span></span>  
 <span data-ttu-id="a7ac5-116">用于枚举成员的命名约定。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="a7ac5-117">当 Visual Basic 遇到枚举成员名称时，如果其他引用的类型库包含相同的名称，可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="a7ac5-118">使用标识你的应用程序或组件中的值的唯一前缀。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="a7ac5-119">当引用时枚举的成员，你必须限定枚举名称的成员名称，否则使用`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="a7ac5-120">有关详细信息，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="a7ac5-121">预定义的枚举</span><span class="sxs-lookup"><span data-stu-id="a7ac5-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="a7ac5-122">Visual Basic 提供了大量预定义的枚举，如`FirstDayOfWeek`和`MsgBoxResult`，以便于你的代码。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="a7ac5-123">有关这些列表请参阅[常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ac5-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ac5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7ac5-124">See Also</span></span>  
 [<span data-ttu-id="a7ac5-125">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="a7ac5-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="a7ac5-126">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="a7ac5-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="a7ac5-127">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="a7ac5-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="a7ac5-128">如何： 循环访问 Visual Basic 中的一个枚举</span><span class="sxs-lookup"><span data-stu-id="a7ac5-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="a7ac5-129">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="a7ac5-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="a7ac5-130">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="a7ac5-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="a7ac5-131">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="a7ac5-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
