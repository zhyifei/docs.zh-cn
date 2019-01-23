---
title: 非 CLS 兼容&lt;membername&gt;符合 cls 的接口中不允许出现
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: c837065d2d448fc2523cfbd18efac962445f8bf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627689"
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="0e75d-102">非 CLS 兼容&lt;membername&gt;符合 cls 的接口中不允许出现</span><span class="sxs-lookup"><span data-stu-id="0e75d-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="0e75d-103">属性、 过程或接口中的事件标记为`<CLSCompliant(True)>`时是接口本身标记为`<CLSCompliant(False)>`或未标记。</span><span class="sxs-lookup"><span data-stu-id="0e75d-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="0e75d-104">接口不能符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)，其所有成员都必须合规。</span><span class="sxs-lookup"><span data-stu-id="0e75d-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="0e75d-105">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="0e75d-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="0e75d-106">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="0e75d-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="0e75d-107">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="0e75d-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="0e75d-108">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="0e75d-108">By default, this message is a warning.</span></span> <span data-ttu-id="0e75d-109">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="0e75d-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0e75d-110">**错误 ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="0e75d-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0e75d-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0e75d-111">To correct this error</span></span>  
  
-   <span data-ttu-id="0e75d-112">如果你需要 CLS 符合性以及对接口的源代码控制，将标记该接口作为`<CLSCompliant(True)>`如果是符合的所有成员。</span><span class="sxs-lookup"><span data-stu-id="0e75d-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="0e75d-113">如果你需要 CLS 符合性，并且不能控制接口源代码，或者它不会不限制为符合规范，定义此成员内使用不同的接口。</span><span class="sxs-lookup"><span data-stu-id="0e75d-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="0e75d-114">如果你需要此成员保持其当前的界面中，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。</span><span class="sxs-lookup"><span data-stu-id="0e75d-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e75d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e75d-115">See also</span></span>
- [<span data-ttu-id="0e75d-116">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="0e75d-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

