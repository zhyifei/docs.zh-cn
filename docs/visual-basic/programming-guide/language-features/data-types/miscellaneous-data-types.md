---
title: 其他数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 9261a02f3dc286dc37b3073158ccc0c151030fe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647331"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="ff7a8-102">其他数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff7a8-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="ff7a8-103">Visual Basic 提供不是针对数字或字符的几种数据类型。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="ff7a8-104">相反，它们处理专用数据如是/否值、 日期/时间值和对象地址。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="ff7a8-105">显示 Visual Basic 数据类型的并排显示比较的表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="ff7a8-106">布尔值类型</span><span class="sxs-lookup"><span data-stu-id="ff7a8-106">Boolean Type</span></span>  
 <span data-ttu-id="ff7a8-107">[布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)是解释为无符号的值`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="ff7a8-108">其数据宽度取决于实现的平台。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="ff7a8-109">如果变量可以包含如 true/false，只有两种状态值是/否，或打开/关闭，将其声明为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="ff7a8-110">日期类型</span><span class="sxs-lookup"><span data-stu-id="ff7a8-110">Date Type</span></span>  
 <span data-ttu-id="ff7a8-111">[日期数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)是包含日期和时间信息的 64 位值。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="ff7a8-112">每个增量表示 (12:00 AM) 中的开始后所用时间的 100 纳秒的 1 公历日历中每 1 年月 1 日。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="ff7a8-113">如果日期值和 / 或时间值，可以包含一个变量，将其声明为`Date`。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="ff7a8-114">对象类型</span><span class="sxs-lookup"><span data-stu-id="ff7a8-114">Object Type</span></span>  
 <span data-ttu-id="ff7a8-115">[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)是指向对象实例在你的应用程序或某个其他应用程序中的 32 位地址。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="ff7a8-116">`Object`变量可以引用你的应用程序识别的任何对象或任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="ff7a8-117">同时包含这*值类型*，如`Integer`， `Boolean`，和结构实例和*引用类型*，这是实例创建的对象从类如`String`和<xref:System.Windows.Forms.Form>，以及数组实例。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="ff7a8-118">如果变量存储指向你不知道在编译时，类的实例或者它可以指向各种数据类型的数据，将其声明为`Object`。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="ff7a8-119">利用`Object`数据类型是，可以使用它来存储任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="ff7a8-120">其缺点在于，会产生额外的操作需要更多的执行时间，使得你的应用程序执行速度减慢。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="ff7a8-121">如果你使用`Object`变量为值类型，你会产生*装箱*和*取消装箱*。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="ff7a8-122">如果你使用它为引用类型，则会引发*后期绑定*。</span><span class="sxs-lookup"><span data-stu-id="ff7a8-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff7a8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff7a8-123">See Also</span></span>  
 [<span data-ttu-id="ff7a8-124">类型字符</span><span class="sxs-lookup"><span data-stu-id="ff7a8-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="ff7a8-125">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="ff7a8-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="ff7a8-126">数值数据类型</span><span class="sxs-lookup"><span data-stu-id="ff7a8-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="ff7a8-127">字符数据类型</span><span class="sxs-lookup"><span data-stu-id="ff7a8-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="ff7a8-128">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="ff7a8-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="ff7a8-129">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="ff7a8-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
