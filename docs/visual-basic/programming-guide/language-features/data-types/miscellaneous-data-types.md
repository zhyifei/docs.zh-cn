---
title: 其他数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 490a462859a916d21c816ff96c47d2deeb9312ee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517791"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="39c1b-102">其他数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39c1b-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="39c1b-103">Visual Basic 提供几种数据类型不是针对数字或字符。</span><span class="sxs-lookup"><span data-stu-id="39c1b-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="39c1b-104">相反，它们处理专用数据如是/否值、 日期/时间值和对象地址。</span><span class="sxs-lookup"><span data-stu-id="39c1b-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="39c1b-105">显示 Visual Basic 数据类型的并排比较的表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="39c1b-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="39c1b-106">布尔值类型</span><span class="sxs-lookup"><span data-stu-id="39c1b-106">Boolean Type</span></span>  
 <span data-ttu-id="39c1b-107">[布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)是一个无符号的值，将被解释为任一`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="39c1b-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="39c1b-108">其数据宽度取决于实现的平台。</span><span class="sxs-lookup"><span data-stu-id="39c1b-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="39c1b-109">如果一个变量可以包含仅两个状态如 true/false 的值是/否或开/关，将其声明为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="39c1b-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="39c1b-110">日期类型</span><span class="sxs-lookup"><span data-stu-id="39c1b-110">Date Type</span></span>  
 <span data-ttu-id="39c1b-111">[日期数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)是一个 64 位值，包含日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="39c1b-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="39c1b-112">每个增量表示自 （上午 12:00） 开始后所用时间的 100 纳秒为单位的 1 公历日历中每 1 年月 1 日。</span><span class="sxs-lookup"><span data-stu-id="39c1b-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="39c1b-113">如果一个变量可以包含日期值、 时间值，或同时，将其声明为`Date`。</span><span class="sxs-lookup"><span data-stu-id="39c1b-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="39c1b-114">对象类型</span><span class="sxs-lookup"><span data-stu-id="39c1b-114">Object Type</span></span>  
 <span data-ttu-id="39c1b-115">[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)是指向你的应用程序或通过在其他一些应用程序中的对象实例的 32 位地址。</span><span class="sxs-lookup"><span data-stu-id="39c1b-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="39c1b-116">`Object`变量可以是指你的应用程序识别的任何对象或任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="39c1b-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="39c1b-117">这包括*值类型*，如`Integer`， `Boolean`，和结构实例，并*引用类型*，这是实例创建的对象的类如`String`和<xref:System.Windows.Forms.Form>，以及数组实例。</span><span class="sxs-lookup"><span data-stu-id="39c1b-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="39c1b-118">如果一个变量存储指向你在编译时，不知道类的实例或者它可以指向不同的数据类型的数据，将其声明为`Object`。</span><span class="sxs-lookup"><span data-stu-id="39c1b-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="39c1b-119">利用`Object`数据类型是，可以使用它来存储任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="39c1b-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="39c1b-120">缺点是会产生额外的操作，需要更多的执行时间并提高执行速度慢的应用程序。</span><span class="sxs-lookup"><span data-stu-id="39c1b-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="39c1b-121">如果您使用`Object`对于值类型变量，则会产生*装箱*并*取消装箱*。</span><span class="sxs-lookup"><span data-stu-id="39c1b-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="39c1b-122">如果将其用于引用类型，则会产生*后期绑定*。</span><span class="sxs-lookup"><span data-stu-id="39c1b-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c1b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="39c1b-123">See Also</span></span>  
 [<span data-ttu-id="39c1b-124">类型字符</span><span class="sxs-lookup"><span data-stu-id="39c1b-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="39c1b-125">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="39c1b-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="39c1b-126">数值数据类型</span><span class="sxs-lookup"><span data-stu-id="39c1b-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="39c1b-127">字符数据类型</span><span class="sxs-lookup"><span data-stu-id="39c1b-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="39c1b-128">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="39c1b-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="39c1b-129">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="39c1b-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
