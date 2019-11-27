---
title: 其他数据类型
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: cc6262b5bb305bb839917e222d831fa3340a1b14
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346337"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="cce34-102">其他数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cce34-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="cce34-103">Visual Basic 提供了多种数据类型，这些数据类型不是面向数字或字符。</span><span class="sxs-lookup"><span data-stu-id="cce34-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="cce34-104">而是处理专用数据，如 "是/否" 值、日期/时间值和对象地址。</span><span class="sxs-lookup"><span data-stu-id="cce34-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="cce34-105">有关显示 Visual Basic 数据类型的并行比较的表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cce34-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="cce34-106">布尔类型</span><span class="sxs-lookup"><span data-stu-id="cce34-106">Boolean Type</span></span>  
 <span data-ttu-id="cce34-107">[Boolean 数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)是一种无符号值，被解释为 `True` 或 `False`。</span><span class="sxs-lookup"><span data-stu-id="cce34-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="cce34-108">其数据宽度取决于实现平台。</span><span class="sxs-lookup"><span data-stu-id="cce34-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="cce34-109">如果变量只能包含两个状态值，如 true/false、yes/no 或 on/off，则将其声明为 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="cce34-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="cce34-110">日期类型</span><span class="sxs-lookup"><span data-stu-id="cce34-110">Date Type</span></span>  
 <span data-ttu-id="cce34-111">[日期数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)是包含日期和时间信息的64位值。</span><span class="sxs-lookup"><span data-stu-id="cce34-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="cce34-112">每个增量表示从公历第1年1月1日开始（12:00 AM）起所用时间的100毫微秒。</span><span class="sxs-lookup"><span data-stu-id="cce34-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="cce34-113">如果变量可以包含日期值和/或时间值，则将其声明为 `Date`。</span><span class="sxs-lookup"><span data-stu-id="cce34-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="cce34-114">“对象类型”</span><span class="sxs-lookup"><span data-stu-id="cce34-114">Object Type</span></span>  
 <span data-ttu-id="cce34-115">[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)是一个32位地址，它指向应用程序或其他应用程序中的对象实例。</span><span class="sxs-lookup"><span data-stu-id="cce34-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="cce34-116">`Object` 变量可以引用应用程序识别的任何对象，或引用任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="cce34-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="cce34-117">这包括*值类型*（例如 `Integer`、`Boolean`和结构实例）和*引用类型*（即从 `String` 和 <xref:System.Windows.Forms.Form>等类创建的对象的实例）以及数组实例。</span><span class="sxs-lookup"><span data-stu-id="cce34-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="cce34-118">如果变量存储指向在编译时不知道的类的实例的指针，或者如果该变量可以指向各种数据类型的数据，则将其声明为 `Object`。</span><span class="sxs-lookup"><span data-stu-id="cce34-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="cce34-119">`Object` 数据类型的优点在于，您可以使用它来存储任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="cce34-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="cce34-120">缺点是您会产生额外的操作，这些操作需要更长的执行时间，并使应用程序的运行速度更慢。</span><span class="sxs-lookup"><span data-stu-id="cce34-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="cce34-121">如果对值类型使用 `Object` 变量，则会产生*装箱*和*取消装箱*。</span><span class="sxs-lookup"><span data-stu-id="cce34-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="cce34-122">如果将其用于引用类型，则会产生*后期绑定*。</span><span class="sxs-lookup"><span data-stu-id="cce34-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce34-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cce34-123">See also</span></span>

- [<span data-ttu-id="cce34-124">类型字符</span><span class="sxs-lookup"><span data-stu-id="cce34-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="cce34-125">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="cce34-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="cce34-126">数值数据类型</span><span class="sxs-lookup"><span data-stu-id="cce34-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="cce34-127">字符数据类型</span><span class="sxs-lookup"><span data-stu-id="cce34-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [<span data-ttu-id="cce34-128">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="cce34-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="cce34-129">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="cce34-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
