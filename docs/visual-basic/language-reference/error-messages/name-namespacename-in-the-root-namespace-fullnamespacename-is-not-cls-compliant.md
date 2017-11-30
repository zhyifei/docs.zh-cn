---
title: "名称&lt;namespacename&gt;根命名空间中&lt;fullnamespacename&gt;不符合 CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords: BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7342c7e85cce6c0e5892c4ad1826907dc03ed808
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="faad4-102">名称&lt;namespacename&gt;根命名空间中&lt;fullnamespacename&gt;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="faad4-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="faad4-103">程序集标记为`<CLSCompliant(True)>`，但根命名空间名称的元素以下划线开头 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="faad4-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="faad4-104">编程元素可以包含一个或多个下划线，但要符合[语言独立性和独立于语言的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，它必须不以下划线开头。</span><span class="sxs-lookup"><span data-stu-id="faad4-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="faad4-105">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="faad4-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="faad4-106">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="faad4-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="faad4-107">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="faad4-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="faad4-108">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="faad4-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="faad4-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="faad4-109">By default, this message is a warning.</span></span> <span data-ttu-id="faad4-110">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="faad4-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="faad4-111">**错误 ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="faad4-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="faad4-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="faad4-112">To correct this error</span></span>  
  
-   <span data-ttu-id="faad4-113">如果你需要 CLS 符合性，更改根命名空间名称，以便其元素以下划线开头。</span><span class="sxs-lookup"><span data-stu-id="faad4-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="faad4-114">如果你需要命名空间名称保持不变，然后删除<xref:System.CLSCompliantAttribute>从程序集或将其标记为`<CLSCompliant(False)>`。</span><span class="sxs-lookup"><span data-stu-id="faad4-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faad4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faad4-115">See Also</span></span>  
 [<span data-ttu-id="faad4-116">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="faad4-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="faad4-117">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="faad4-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="faad4-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="faad4-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [<span data-ttu-id="faad4-119">“项目设计器”->“应用程序”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="faad4-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [<span data-ttu-id="faad4-120">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="faad4-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="faad4-121">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="faad4-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="faad4-122">\<PAVE 通过 > 编写符合 Cls 的代码</span><span class="sxs-lookup"><span data-stu-id="faad4-122">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
