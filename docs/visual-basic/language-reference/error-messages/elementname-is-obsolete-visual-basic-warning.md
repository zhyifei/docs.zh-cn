---
title: "&lt;elementname&gt;是已过时 （Visual Basic 警告） |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
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
ms.openlocfilehash: 77708f052f7aec7a5da2b24605ba3bd794f83979
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a><span data-ttu-id="c3f56-102">&lt;elementname&gt;是已过时 （Visual Basic 警告）</span><span class="sxs-lookup"><span data-stu-id="c3f56-102">&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="c3f56-103">语句试图访问的编程元素，它已标记有<xref:System.ObsoleteAttribute>特性，指令会将其视为一条警告。</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="c3f56-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="c3f56-104">您可以将标记为不再使用通过将应用<xref:System.ObsoleteAttribute>于它。</xref:System.ObsoleteAttribute>所有编程元素</span><span class="sxs-lookup"><span data-stu-id="c3f56-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="c3f56-105">如果执行此操作，则可以设置该属性的<xref:System.ObsoleteAttribute.IsError%2A>属性设置为任何一个`True`或`False`。</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="c3f56-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="c3f56-106">如果设置为 `True`，则编译器将尝试使用该元素的操作视为错误。</span><span class="sxs-lookup"><span data-stu-id="c3f56-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="c3f56-107">如果设置为 `False`，或将其默认为 `False`，则编译器会在有操作尝试使用该元素时发出警告。</span><span class="sxs-lookup"><span data-stu-id="c3f56-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="c3f56-108">默认情况下，此消息是一个警告，因为<xref:System.ObsoleteAttribute.IsError%2A>属性<xref:System.ObsoleteAttribute>是`False`。</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="c3f56-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="c3f56-109">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="c3f56-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c3f56-110">**错误 ID:** BC40008</span><span class="sxs-lookup"><span data-stu-id="c3f56-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c3f56-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c3f56-111">To correct this error</span></span>  
  
-   <span data-ttu-id="c3f56-112">确保源代码引用的元素名称拼写正确。</span><span class="sxs-lookup"><span data-stu-id="c3f56-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f56-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3f56-113">See Also</span></span>  
 [<span data-ttu-id="c3f56-114">属性概述</span><span class="sxs-lookup"><span data-stu-id="c3f56-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

