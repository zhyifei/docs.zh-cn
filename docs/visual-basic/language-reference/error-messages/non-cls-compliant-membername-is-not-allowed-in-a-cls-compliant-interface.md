---
title: "不符合 CLS 符合&lt;membername&gt;符合 cls 的接口中不允许"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2811958df5bd0b023a2ce3b02abf85b5a23c58f6
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="88e2f-102">不符合 CLS 符合&lt;membername&gt;符合 cls 的接口中不允许</span><span class="sxs-lookup"><span data-stu-id="88e2f-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="88e2f-103">属性、 过程或接口中的事件被标记为`<CLSCompliant(True)>`接口本身时被标记为`<CLSCompliant(False)>`或未标记。</span><span class="sxs-lookup"><span data-stu-id="88e2f-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="88e2f-104">接口不能符合[语言独立性和独立于语言的组件](../../../../docs/standard/language-independence-and-language-independent-components.md)(CLS)，其所有成员必须都是合规的。</span><span class="sxs-lookup"><span data-stu-id="88e2f-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="88e2f-105">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="88e2f-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="88e2f-106">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="88e2f-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="88e2f-107">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="88e2f-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="88e2f-108">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="88e2f-108">By default, this message is a warning.</span></span> <span data-ttu-id="88e2f-109">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="88e2f-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="88e2f-110">**错误 ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="88e2f-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88e2f-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="88e2f-111">To correct this error</span></span>  
  
-   <span data-ttu-id="88e2f-112">如果你需要 CLS 遵从性，并且可以控制接口源代码，将标记为接口`<CLSCompliant(True)>`是否符合其所有成员。</span><span class="sxs-lookup"><span data-stu-id="88e2f-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="88e2f-113">如果你需要 CLS 符合性而不能控制接口源代码，或者不将其限制为符合，定义此成员在不同的接口。</span><span class="sxs-lookup"><span data-stu-id="88e2f-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="88e2f-114">如果你需要此成员保留在其当前的接口，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。</span><span class="sxs-lookup"><span data-stu-id="88e2f-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e2f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88e2f-115">See Also</span></span>  
 [<span data-ttu-id="88e2f-116">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="88e2f-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="88e2f-117">\<PAVE 通过 > 编写符合 Cls 的代码</span><span class="sxs-lookup"><span data-stu-id="88e2f-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
