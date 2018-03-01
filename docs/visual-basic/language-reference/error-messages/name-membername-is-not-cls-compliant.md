---
title: "名称&lt;membername&gt;不符合 CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba0dda520e37b27f9b7ad3c214508ee370162598
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="8c311-102">名称&lt;membername&gt;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="8c311-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="8c311-103">程序集标记为`<CLSCompliant(True)>`但公开了一个具有此名称的名称以下划线开头的成员 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="8c311-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="8c311-104">编程元素可以包含一个或多个下划线，但要符合[语言独立性和独立于语言的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)，它必须不以下划线开头。</span><span class="sxs-lookup"><span data-stu-id="8c311-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="8c311-105">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="8c311-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="8c311-106">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="8c311-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="8c311-107">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="8c311-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="8c311-108">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="8c311-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="8c311-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="8c311-109">By default, this message is a warning.</span></span> <span data-ttu-id="8c311-110">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="8c311-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8c311-111">**错误 ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="8c311-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c311-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8c311-112">To correct this error</span></span>  
  
-   <span data-ttu-id="8c311-113">如果你有控制的源代码，更改成员名称，以便它不以下划线开头。</span><span class="sxs-lookup"><span data-stu-id="8c311-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="8c311-114">如果你需要的成员名称保持不变，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。</span><span class="sxs-lookup"><span data-stu-id="8c311-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="8c311-115">你仍然可以将标记该程序集作为`<CLSCompliant(True)>`。</span><span class="sxs-lookup"><span data-stu-id="8c311-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c311-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c311-116">See Also</span></span>  
 [<span data-ttu-id="8c311-117">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="8c311-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="8c311-118">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="8c311-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  

