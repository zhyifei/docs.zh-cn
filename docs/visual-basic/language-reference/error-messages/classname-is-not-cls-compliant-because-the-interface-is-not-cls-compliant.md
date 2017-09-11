---
title: "&lt;classname&gt;由于不符合 cls 的接口&lt;interfacename&gt;其实现不符合 cls 的 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
dev_langs:
- VB
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
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
ms.openlocfilehash: d2819bf2dc76291cbaf7ca9215608a11b1a98b3a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a><span data-ttu-id="74741-102">&lt;classname&gt;由于不符合 cls 的接口&lt;interfacename&gt;其实现不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="74741-102">&#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant</span></span>
<span data-ttu-id="74741-103">当某一类或接口派生自或实现标记为 `<CLSCompliant(True)>` 的类型时，该类或接口将被标记为 `<CLSCompliant(False)>` 。</span><span class="sxs-lookup"><span data-stu-id="74741-103">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="74741-104">为类或接口，以符合[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，整个继承层次结构都必须是符合。</span><span class="sxs-lookup"><span data-stu-id="74741-104">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="74741-105">这意味着从它继承的每一个类型，不管是直接还是间接继承，都必须符合。</span><span class="sxs-lookup"><span data-stu-id="74741-105">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="74741-106">同样，如果一个类实现一个或多个接口，则其整个继承层次结构都必须符合。</span><span class="sxs-lookup"><span data-stu-id="74741-106">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>  
  
 <span data-ttu-id="74741-107">当您将应用<xref:System.CLSCompliantAttribute>编程元素中，设置该属性的`isCompliant`至任一参数`True`或`False`来指示符合或不符合性。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="74741-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="74741-108">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="74741-108">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="74741-109">如果不适用<xref:System.CLSCompliantAttribute>到元素，它被视为不符合要求。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="74741-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="74741-110">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="74741-110">By default, this message is a warning.</span></span> <span data-ttu-id="74741-111">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="74741-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="74741-112">**错误 ID:** BC40029</span><span class="sxs-lookup"><span data-stu-id="74741-112">**Error ID:** BC40029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="74741-113">更正此错误</span><span class="sxs-lookup"><span data-stu-id="74741-113">To correct this error</span></span>  
  
-   <span data-ttu-id="74741-114">如果你需要 CLS 符合性，请在不同的继承层次结构或实现方案中定义此类型。</span><span class="sxs-lookup"><span data-stu-id="74741-114">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>  
  
-   <span data-ttu-id="74741-115">如果您要求此类型保留其当前的继承层次结构或实现方案中，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="74741-115">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74741-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74741-116">See Also</span></span>  
 [<span data-ttu-id="74741-117">\<PAVE 通过&1;> 编写符合 Cls 的代码</span><span class="sxs-lookup"><span data-stu-id="74741-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
