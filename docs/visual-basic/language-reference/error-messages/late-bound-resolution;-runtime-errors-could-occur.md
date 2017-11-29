---
title: "后期绑定解决方案；可能会发生运行时错误"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords: BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d01164914b484ef689654f048a8743f3c2eb669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="0331a-102">后期绑定解决方案；可能会发生运行时错误</span><span class="sxs-lookup"><span data-stu-id="0331a-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="0331a-103">一个对象分配给变量声明为[Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="0331a-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="0331a-104">当你声明一个变量，作为`Object`，编译器必须执行*后期绑定*，这将导致在运行时产生额外的操作。</span><span class="sxs-lookup"><span data-stu-id="0331a-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="0331a-105">它还使应用程序易于发生潜在的运行时错误。</span><span class="sxs-lookup"><span data-stu-id="0331a-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="0331a-106">例如，如果你将分配<xref:System.Windows.Forms.Form>到`Object`变量，然后尝试访问<xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType>属性，则运行时会引发<xref:System.MemberAccessException>因为<xref:System.Windows.Forms.Form>类不公开`NameTable`属性。</span><span class="sxs-lookup"><span data-stu-id="0331a-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="0331a-107">如果声明为特定类型的变量，编译器可以执行*早期绑定*在编译时。</span><span class="sxs-lookup"><span data-stu-id="0331a-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="0331a-108">这会导致提高性能，受控访问权限的特定类型的成员，并且更好地提高代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="0331a-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="0331a-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="0331a-109">By default, this message is a warning.</span></span> <span data-ttu-id="0331a-110">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="0331a-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0331a-111">**错误 ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="0331a-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0331a-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0331a-112">To correct this error</span></span>  
  
-   <span data-ttu-id="0331a-113">如果可能，将特定类型的变量声明。</span><span class="sxs-lookup"><span data-stu-id="0331a-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0331a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0331a-114">See Also</span></span>  
 [<span data-ttu-id="0331a-115">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="0331a-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="0331a-116">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="0331a-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
