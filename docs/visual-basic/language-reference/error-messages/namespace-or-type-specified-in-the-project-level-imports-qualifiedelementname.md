---
title: Namespace 或类型中的项目级导入指定&#39; &lt;qualifiedelementname&gt; &#39;不&#39;t 包含任何公共成员，或者找不到
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: d6d0c931262d892ec3e65888a76f25218b23d868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595808"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="ff384-102">Namespace 或类型中的项目级导入指定&#39; &lt;qualifiedelementname&gt; &#39;不&#39;t 包含任何公共成员，或者找不到</span><span class="sxs-lookup"><span data-stu-id="ff384-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="ff384-103">Namespace 或类型中的项目级导入的指定\<qualifiedelementname > 不包含任何公共成员，或无法找到。</span><span class="sxs-lookup"><span data-stu-id="ff384-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="ff384-104">请确保命名空间或类型定义，并且包含至少一个公共成员。</span><span class="sxs-lookup"><span data-stu-id="ff384-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="ff384-105">请确保该别名名称不包含其他别名。</span><span class="sxs-lookup"><span data-stu-id="ff384-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="ff384-106">一个项目的导入属性所指定的包含的元素不能找到或未定义任何`Public`成员。</span><span class="sxs-lookup"><span data-stu-id="ff384-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="ff384-107">A*包含元素*可以是命名空间、 类、 结构、 模块、 接口或枚举。</span><span class="sxs-lookup"><span data-stu-id="ff384-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="ff384-108">包含的元素包含成员，例如变量、 过程或其他包含的元素。</span><span class="sxs-lookup"><span data-stu-id="ff384-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="ff384-109">导入的目的是允许你访问命名空间或类型成员的代码，而无需限定它们。</span><span class="sxs-lookup"><span data-stu-id="ff384-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="ff384-110">你的项目可能还需要添加对命名空间或类型的引用。</span><span class="sxs-lookup"><span data-stu-id="ff384-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="ff384-111">详细信息，请参阅"导入包含元素"中[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff384-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="ff384-112">如果编译器找不到指定的包含元素，它无法解析使用它的引用。</span><span class="sxs-lookup"><span data-stu-id="ff384-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="ff384-113">如果它找到的元素，但该元素不公开任何`Public`成员，则任何引用都不会成功。</span><span class="sxs-lookup"><span data-stu-id="ff384-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="ff384-114">在任一情况下是没有意义，来导入元素。</span><span class="sxs-lookup"><span data-stu-id="ff384-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="ff384-115">你使用**项目设计器**可指定要导入元素。</span><span class="sxs-lookup"><span data-stu-id="ff384-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="ff384-116">使用**导入命名空间**部分**引用**页。</span><span class="sxs-lookup"><span data-stu-id="ff384-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="ff384-117">你可以到达**项目设计器**通过双击**我的项目**图标**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="ff384-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="ff384-118">**错误 ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="ff384-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff384-119">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ff384-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="ff384-120">打开**项目设计器**并切换到**引用**页。</span><span class="sxs-lookup"><span data-stu-id="ff384-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="ff384-121">在**导入命名空间**部分中，验证是否可从你的项目访问包含的元素。</span><span class="sxs-lookup"><span data-stu-id="ff384-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="ff384-122">验证包含元素公开至少一个`Public`成员。</span><span class="sxs-lookup"><span data-stu-id="ff384-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff384-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff384-123">See Also</span></span>  
 [<span data-ttu-id="ff384-124">项目设计器 ->“引用”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff384-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [<span data-ttu-id="ff384-125">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="ff384-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="ff384-126">Public</span><span class="sxs-lookup"><span data-stu-id="ff384-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="ff384-127">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="ff384-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="ff384-128">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="ff384-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
