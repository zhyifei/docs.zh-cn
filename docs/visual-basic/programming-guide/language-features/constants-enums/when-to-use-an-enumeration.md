---
title: 何时使用枚举 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: ff2d8c324aee8bbccef050c020e5392368b05b1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907304"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="d8e5b-102">何时使用枚举 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8e5b-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="d8e5b-103">枚举提供了使用相关常量集的简单方法。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="d8e5b-104">一个枚举，或`Enum`，是一组值的符号名称。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="d8e5b-105">枚举被视为数据类型，并可用于创建用变量和属性使用的常数的集。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="d8e5b-106">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="d8e5b-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="d8e5b-107">当一个过程接受一组有限的变量时，请考虑使用一个枚举。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="d8e5b-108">枚举可使更明确且更具可读性的代码，尤其是在使用有意义的名称时。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="d8e5b-109">使用枚举的优点包括：</span><span class="sxs-lookup"><span data-stu-id="d8e5b-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="d8e5b-110">这样可以减少错误引起的转置或键入数字。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="d8e5b-111">便于将来更改值。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="d8e5b-112">使代码易于阅读，这意味着它不太可能的错误将蔓延到其中。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="d8e5b-113">可确保向前兼容性。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-113">Ensures forward compatibility.</span></span> <span data-ttu-id="d8e5b-114">借助枚举、 你的代码是不太可能会失败，如果有人在将来更改的成员名称与对应的值。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="d8e5b-115">命名枚举</span><span class="sxs-lookup"><span data-stu-id="d8e5b-115">Naming Enumerations</span></span>  
 <span data-ttu-id="d8e5b-116">枚举成员使用的命名约定。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="d8e5b-117">当 Visual Basic 遇到的枚举成员名称时，如果其他引用的类型库包含相同的名称可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="d8e5b-118">使用唯一的前缀，用于标识您的应用程序或组件中的值。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="d8e5b-119">当引用枚举成员，必须限定为枚举名称的成员名称，否则使用`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="d8e5b-120">有关详细信息，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="d8e5b-121">预定义的枚举</span><span class="sxs-lookup"><span data-stu-id="d8e5b-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="d8e5b-122">Visual Basic 提供了大量预定义的枚举，如`FirstDayOfWeek`和`MsgBoxResult`，以便于您的代码。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="d8e5b-123">有关这些列表请参阅[常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="d8e5b-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e5b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8e5b-124">See also</span></span>

- [<span data-ttu-id="d8e5b-125">如何：声明枚举</span><span class="sxs-lookup"><span data-stu-id="d8e5b-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="d8e5b-126">如何：为枚举成员，请参阅</span><span class="sxs-lookup"><span data-stu-id="d8e5b-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="d8e5b-127">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="d8e5b-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="d8e5b-128">如何：循环访问在 Visual Basic 中枚举</span><span class="sxs-lookup"><span data-stu-id="d8e5b-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="d8e5b-129">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="d8e5b-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="d8e5b-130">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="d8e5b-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="d8e5b-131">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="d8e5b-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
