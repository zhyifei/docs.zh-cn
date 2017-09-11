---
title: "其他数据类型 (Visual Basic 中) |Microsoft 文档"
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
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
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
ms.openlocfilehash: ed7b61a5ec57ff85347f2c257e321ab9ec425274
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="50199-102">其他数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50199-102">Miscellaneous Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="50199-103">提供几个不是针对数字或字符的数据类型。</span><span class="sxs-lookup"><span data-stu-id="50199-103"> supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="50199-104">相反，它们处理专用数据如是/否值、 日期/时间值和对象地址。</span><span class="sxs-lookup"><span data-stu-id="50199-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="50199-105">显示通过并行进行比较的表为[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]数据类型，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="50199-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="50199-106">布尔值类型</span><span class="sxs-lookup"><span data-stu-id="50199-106">Boolean Type</span></span>  
 <span data-ttu-id="50199-107">[布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)是解释为无符号的值`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="50199-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="50199-108">其数据宽度取决于实现的平台。</span><span class="sxs-lookup"><span data-stu-id="50199-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="50199-109">如果一个变量可以包含如 true/false 时，只有两种状态值是/否，或打开/关闭，将其声明为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="50199-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="50199-110">日期类型</span><span class="sxs-lookup"><span data-stu-id="50199-110">Date Type</span></span>  
 <span data-ttu-id="50199-111">[Date 数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)是包含日期和时间信息的 64 位值。</span><span class="sxs-lookup"><span data-stu-id="50199-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="50199-112">每个增量之初 (12:00 AM) 表示已用时间的 100 纳的秒的 1 公历日历中每 1 年月 1 日。</span><span class="sxs-lookup"><span data-stu-id="50199-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="50199-113">如果日期值和 / 或时间值，可以包含一个变量，将其声明为`Date`。</span><span class="sxs-lookup"><span data-stu-id="50199-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="50199-114">对象类型</span><span class="sxs-lookup"><span data-stu-id="50199-114">Object Type</span></span>  
 <span data-ttu-id="50199-115">[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)是指向对象实例在您的应用程序或其他一些应用程序中的 32 位地址。</span><span class="sxs-lookup"><span data-stu-id="50199-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="50199-116">`Object`变量可引用的应用程序识别，任何对象或对任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="50199-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="50199-117">这包括这两个*值类型*，如`Integer`， `Boolean`，以及结构的实例，并*引用类型*，后者是如从类创建的对象的实例`String`和<xref:System.Windows.Forms.Form>，以及数组实例。</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="50199-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="50199-118">如果一个变量存储在编译时，不知道您的类的实例的指针，或者它可以指向各种数据类型的数据，将其声明为`Object`。</span><span class="sxs-lookup"><span data-stu-id="50199-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="50199-119">利用`Object`数据类型是，可以使用它来存储任何数据类型的数据。</span><span class="sxs-lookup"><span data-stu-id="50199-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="50199-120">其缺点在于，您会产生额外的操作，需要更多的执行时间，使得应用程序执行速度慢。</span><span class="sxs-lookup"><span data-stu-id="50199-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="50199-121">如果您使用`Object`对于值类型变量，则会导致*装箱*和*取消装箱*。</span><span class="sxs-lookup"><span data-stu-id="50199-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="50199-122">如果您将它用于引用类型，则会引发*后期绑定*。</span><span class="sxs-lookup"><span data-stu-id="50199-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50199-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50199-123">See Also</span></span>  
 <span data-ttu-id="50199-124">[类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="50199-124">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
<span data-ttu-id="50199-125"> [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="50199-125"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="50199-126"> [数值数据类型](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="50199-126"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="50199-127"> [字符数据类型](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="50199-127"> [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span></span>  
<span data-ttu-id="50199-128"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="50199-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="50199-129"> [早期绑定和后期绑定](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="50199-129"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
