---
title: Namespace 或导入 &#39; 中指定的类型&lt;qualifiedelementname&gt;&#39; 没有 &#39; 不包含任何公共成员，或无法找到
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cd9fa5d5182b2cf2d7fc4623bc8e9aa02bf85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="b6cd0-102">Namespace 或导入 &#39; 中指定的类型&lt;qualifiedelementname&gt;&#39; 没有 &#39; 不包含任何公共成员，或无法找到</span><span class="sxs-lookup"><span data-stu-id="b6cd0-102">Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="b6cd0-103">Namespace 或类型中的导入的指定\<qualifiedelementname > 不包含任何公共成员，或无法找到。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="b6cd0-104">请确保命名空间或类型定义，并且包含至少一个公共成员。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="b6cd0-105">请确保该别名名称不包含其他别名。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="b6cd0-106">`Imports`语句指定的包含的元素不能找到或未定义任何`Public`成员。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="b6cd0-107">A*包含元素*可以是命名空间、 类、 结构、 模块、 接口或枚举。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="b6cd0-108">包含的元素包含成员，例如变量、 过程或其他包含的元素。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="b6cd0-109">导入的目的是允许你访问命名空间或类型成员的代码，而无需限定它们。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="b6cd0-110">你的项目可能还需要添加对命名空间或类型的引用。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="b6cd0-111">详细信息，请参阅"导入包含元素"中[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="b6cd0-112">如果编译器找不到指定的包含元素，它无法解析使用它的引用。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="b6cd0-113">如果它找到的元素，但该元素不公开任何`Public`成员，则任何引用都不会成功。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="b6cd0-114">在任一情况下是没有意义，来导入元素。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="b6cd0-115">请记住，如果你导入包含元素，并为其分配导入别名，则无法使用该导入别名来导入另一个元素。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="b6cd0-116">下面的代码生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-116">The following code generates a compiler error.</span></span>  
  
 <span data-ttu-id="b6cd0-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span><span class="sxs-lookup"><span data-stu-id="b6cd0-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span></span>  
  
 <span data-ttu-id="b6cd0-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span><span class="sxs-lookup"><span data-stu-id="b6cd0-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span></span>  
  
 <span data-ttu-id="b6cd0-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span><span class="sxs-lookup"><span data-stu-id="b6cd0-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span></span>  
  
 <span data-ttu-id="b6cd0-120">**错误 ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="b6cd0-120">**Error ID:** BC40056</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6cd0-121">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b6cd0-121">To correct this error</span></span>  
  
1.  <span data-ttu-id="b6cd0-122">验证包含的元素可从你的项目中访问。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-122">Verify that the containing element is accessible from your project.</span></span>  
  
2.  <span data-ttu-id="b6cd0-123">验证包含的元素的规范不包括从另一个导入任何导入别名。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-123">Verify that the specification of the containing element does not include any import alias from another import.</span></span>  
  
3.  <span data-ttu-id="b6cd0-124">验证包含元素公开至少一个`Public`成员。</span><span class="sxs-lookup"><span data-stu-id="b6cd0-124">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cd0-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6cd0-125">See Also</span></span>  
 [<span data-ttu-id="b6cd0-126">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="b6cd0-126">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="b6cd0-127">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="b6cd0-127">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="b6cd0-128">Public</span><span class="sxs-lookup"><span data-stu-id="b6cd0-128">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="b6cd0-129">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="b6cd0-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="b6cd0-130">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="b6cd0-130">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
