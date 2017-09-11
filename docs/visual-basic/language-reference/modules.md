---
title: "模块 (Visual Basic) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- modules, Visual Basic
ms.assetid: 370bfc90-e8f2-4942-bdec-9897ce605d31
caps.latest.revision: 11
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
ms.openlocfilehash: 808510c83339e1768dba39f119a2e97ac44f0e4a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="modules-visual-basic"></a><span data-ttu-id="509df-102">模块 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="509df-102">Modules (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="509df-103">提供了几个模块，使您能够简化在代码中，包括处理字符串、 执行数学计算、 获取系统信息、 执行文件和目录操作的常见任务，依次类推。</span><span class="sxs-lookup"><span data-stu-id="509df-103"> provides several modules that enable you to simplify common tasks in your code, including manipulating strings, performing mathematical calculations, getting system information, performing file and directory operations, and so on.</span></span> <span data-ttu-id="509df-104">下表列出了提供的模块[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="509df-104">The following table lists the modules provided by [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="509df-105"><xref:Microsoft.VisualBasic.Constants></xref:Microsoft.VisualBasic.Constants></span><span class="sxs-lookup"><span data-stu-id="509df-105"><xref:Microsoft.VisualBasic.Constants></span></span>|<span data-ttu-id="509df-106">包含各种常量。</span><span class="sxs-lookup"><span data-stu-id="509df-106">Contains miscellaneous constants.</span></span> <span data-ttu-id="509df-107">可以在代码中任意位置使用这些常量。</span><span class="sxs-lookup"><span data-stu-id="509df-107">These constants can be used anywhere in your code.</span></span>|  
|<span data-ttu-id="509df-108"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="509df-108"><xref:Microsoft.VisualBasic.ControlChars></span></span>|<span data-ttu-id="509df-109">包含用于打印和显示文本的常量控制字符。</span><span class="sxs-lookup"><span data-stu-id="509df-109">Contains constant control characters for printing and displaying text.</span></span>|  
|<span data-ttu-id="509df-110"><xref:Microsoft.VisualBasic.Conversion></xref:Microsoft.VisualBasic.Conversion></span><span class="sxs-lookup"><span data-stu-id="509df-110"><xref:Microsoft.VisualBasic.Conversion></span></span>|<span data-ttu-id="509df-111">包含编号转换为字符串、 字符串转换为数字和一个数据类型转换为另一种将十进制数字转换为其他基数的成员。</span><span class="sxs-lookup"><span data-stu-id="509df-111">Contains members that convert decimal numbers to other bases, numbers to strings, strings to numbers, and one data type to another.</span></span>|  
|<span data-ttu-id="509df-112"><xref:Microsoft.VisualBasic.DateAndTime></xref:Microsoft.VisualBasic.DateAndTime></span><span class="sxs-lookup"><span data-stu-id="509df-112"><xref:Microsoft.VisualBasic.DateAndTime></span></span>|<span data-ttu-id="509df-113">包含的成员用于获取当前日期或时间、 执行日期计算、 返回日期或时间、 设置日期或时间，或记录的进程的持续时间。</span><span class="sxs-lookup"><span data-stu-id="509df-113">Contains members that get the current date or time, perform date calculations, return a date or time, set the date or time, or time the duration of a process.</span></span>|  
|<span data-ttu-id="509df-114"><xref:Microsoft.VisualBasic.ErrObject></xref:Microsoft.VisualBasic.ErrObject></span><span class="sxs-lookup"><span data-stu-id="509df-114"><xref:Microsoft.VisualBasic.ErrObject></span></span>|<span data-ttu-id="509df-115">包含有关运行时错误和方法，从而引发或更正错误的信息。</span><span class="sxs-lookup"><span data-stu-id="509df-115">Contains information about run-time errors and methods to raise or clear an error.</span></span>|  
|<span data-ttu-id="509df-116"><xref:Microsoft.VisualBasic.FileSystem></xref:Microsoft.VisualBasic.FileSystem></span><span class="sxs-lookup"><span data-stu-id="509df-116"><xref:Microsoft.VisualBasic.FileSystem></span></span>|<span data-ttu-id="509df-117">包含执行文件、 目录或文件夹和系统操作的成员。</span><span class="sxs-lookup"><span data-stu-id="509df-117">Contains members that perform file, directory or folder, and system operations.</span></span>|  
|<span data-ttu-id="509df-118"><xref:Microsoft.VisualBasic.Financial></xref:Microsoft.VisualBasic.Financial></span><span class="sxs-lookup"><span data-stu-id="509df-118"><xref:Microsoft.VisualBasic.Financial></span></span>|<span data-ttu-id="509df-119">包含用于执行财务计算的过程。</span><span class="sxs-lookup"><span data-stu-id="509df-119">Contains procedures that are used to perform financial calculations.</span></span>|  
|<span data-ttu-id="509df-120"><xref:Microsoft.VisualBasic.Globals></xref:Microsoft.VisualBasic.Globals></span><span class="sxs-lookup"><span data-stu-id="509df-120"><xref:Microsoft.VisualBasic.Globals></span></span>|<span data-ttu-id="509df-121">包含有关当前脚本引擎版本信息。</span><span class="sxs-lookup"><span data-stu-id="509df-121">Contains information about the current scripting engine version.</span></span>|  
|<span data-ttu-id="509df-122"><xref:Microsoft.VisualBasic.Information></xref:Microsoft.VisualBasic.Information></span><span class="sxs-lookup"><span data-stu-id="509df-122"><xref:Microsoft.VisualBasic.Information></span></span>|<span data-ttu-id="509df-123">包含的成员，返回、 测试或验证数组的大小、 类型名称等信息。</span><span class="sxs-lookup"><span data-stu-id="509df-123">Contains the members that return, test for, or verify information such as array size, type names, and so on.</span></span>|  
|<span data-ttu-id="509df-124"><xref:Microsoft.VisualBasic.Interaction></xref:Microsoft.VisualBasic.Interaction></span><span class="sxs-lookup"><span data-stu-id="509df-124"><xref:Microsoft.VisualBasic.Interaction></span></span>|<span data-ttu-id="509df-125">包含与对象、 应用程序和系统进行交互的成员。</span><span class="sxs-lookup"><span data-stu-id="509df-125">Contains members interact with objects, applications, and systems.</span></span>|  
|<span data-ttu-id="509df-126"><xref:Microsoft.VisualBasic.Strings></xref:Microsoft.VisualBasic.Strings></span><span class="sxs-lookup"><span data-stu-id="509df-126"><xref:Microsoft.VisualBasic.Strings></span></span>|<span data-ttu-id="509df-127">包含成员执行字符串操作，如重新格式化字符串、 搜索字符串、 获取字符串的长度，依此类推。</span><span class="sxs-lookup"><span data-stu-id="509df-127">Contains members that perform string operations such as reformatting strings, searching a string, getting the length of a string, and so on.</span></span>|  
|<span data-ttu-id="509df-128"><xref:Microsoft.VisualBasic.VBMath></xref:Microsoft.VisualBasic.VBMath></span><span class="sxs-lookup"><span data-stu-id="509df-128"><xref:Microsoft.VisualBasic.VBMath></span></span>|<span data-ttu-id="509df-129">包含成员执行数学运算。</span><span class="sxs-lookup"><span data-stu-id="509df-129">Contains members perform mathematical operations.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="509df-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="509df-130">See Also</span></span>  
 <span data-ttu-id="509df-131">[Visual Basic 语言参考](../../visual-basic/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="509df-131">[Visual Basic Language Reference](../../visual-basic/language-reference/index.md) </span></span>  
<span data-ttu-id="509df-132"> [Visual Basic](../../visual-basic/index.md)</span><span class="sxs-lookup"><span data-stu-id="509df-132"> [Visual Basic](../../visual-basic/index.md)</span></span>
