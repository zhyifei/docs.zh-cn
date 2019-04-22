---
title: 名称 <membername> 不符合 CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 06b20b4f61741f2174654d749df55c3c4348c547
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824619"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="cbafa-102">名称\<成员名称 > 不符合 cls 的</span><span class="sxs-lookup"><span data-stu-id="cbafa-102">Name \<membername> is not CLS-compliant</span></span>
<span data-ttu-id="cbafa-103">程序集标记为`<CLSCompliant(True)>`公开的成员名称以下划线开头的名称，但 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="cbafa-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="cbafa-104">编程元素可以包含一个或多个下划线，但要符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)，它必须不以下划线开头。</span><span class="sxs-lookup"><span data-stu-id="cbafa-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="cbafa-105">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="cbafa-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="cbafa-106">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="cbafa-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="cbafa-107">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="cbafa-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="cbafa-108">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="cbafa-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="cbafa-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="cbafa-109">By default, this message is a warning.</span></span> <span data-ttu-id="cbafa-110">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="cbafa-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="cbafa-111">**错误 ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="cbafa-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cbafa-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="cbafa-112">To correct this error</span></span>  
  
-   <span data-ttu-id="cbafa-113">如果必须对源代码控制，更改成员名称，以便它不以下划线开头。</span><span class="sxs-lookup"><span data-stu-id="cbafa-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="cbafa-114">如果你需要成员名称保持不变，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。</span><span class="sxs-lookup"><span data-stu-id="cbafa-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="cbafa-115">仍然可以将标记为程序集`<CLSCompliant(True)>`。</span><span class="sxs-lookup"><span data-stu-id="cbafa-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbafa-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbafa-116">See also</span></span>

- [<span data-ttu-id="cbafa-117">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="cbafa-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="cbafa-118">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="cbafa-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
