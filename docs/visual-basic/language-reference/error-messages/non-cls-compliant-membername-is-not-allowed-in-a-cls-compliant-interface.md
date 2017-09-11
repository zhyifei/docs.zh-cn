---
title: "不符合 CLS 符合&lt;membername&gt;符合 cls 的接口中不允许 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
dev_langs:
- VB
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
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
ms.openlocfilehash: 27e83344c68d73c992d2395ab5d1bfcdb67520b0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="799e6-102">不符合 CLS 符合&lt;membername&gt;不允许在符合 cls 的接口</span><span class="sxs-lookup"><span data-stu-id="799e6-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="799e6-103">属性、 过程或在接口中的事件被标记为`<CLSCompliant(True)>`接口本身时被标记为`<CLSCompliant(False)>`或未标记。</span><span class="sxs-lookup"><span data-stu-id="799e6-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="799e6-104">接口不能为符合[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，其所有成员都必须都是符合。</span><span class="sxs-lookup"><span data-stu-id="799e6-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="799e6-105">当您将应用<xref:System.CLSCompliantAttribute>编程元素中，设置该属性的`isCompliant`至任一参数`True`或`False`来指示符合或不符合性。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="799e6-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="799e6-106">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="799e6-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="799e6-107">如果不适用<xref:System.CLSCompliantAttribute>到元素，它被视为不符合要求。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="799e6-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="799e6-108">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="799e6-108">By default, this message is a warning.</span></span> <span data-ttu-id="799e6-109">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="799e6-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="799e6-110">**错误 ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="799e6-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="799e6-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="799e6-111">To correct this error</span></span>  
  
-   <span data-ttu-id="799e6-112">如果你需要 CLS 遵从性，并可以控制接口源代码，将接口标记为`<CLSCompliant(True)>`是否符合其所有成员。</span><span class="sxs-lookup"><span data-stu-id="799e6-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="799e6-113">如果你需要 CLS 遵从性，并不能控制接口源代码，或者如果它不符合以使其符合，定义此成员内使用不同的接口。</span><span class="sxs-lookup"><span data-stu-id="799e6-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="799e6-114">如果您需要此成员保留在其当前的接口，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="799e6-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799e6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="799e6-115">See Also</span></span>  
 <span data-ttu-id="799e6-116">[Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="799e6-116">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="799e6-117"> [\<PAVE 通过&1;> 编写符合 Cls 的代码](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="799e6-117"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
