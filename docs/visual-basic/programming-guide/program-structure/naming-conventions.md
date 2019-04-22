---
title: Visual Basic 命名约定
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 46f59403feced4baafef4662065cb7daedbeaa7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837073"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="eb772-102">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="eb772-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="eb772-103">当在 Visual Basic 应用程序中命名元素时，该名称的第一个字符必须是字母字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="eb772-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="eb772-104">但请注意，以下划线开头的名称不符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)。</span><span class="sxs-lookup"><span data-stu-id="eb772-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="eb772-105">以下建议适用于命名。</span><span class="sxs-lookup"><span data-stu-id="eb772-105">The following suggestions apply to naming.</span></span>  
  
-   <span data-ttu-id="eb772-106">在开始使用一个大写字母，名称中每个单独的分词`FindLastRecord`和`RedrawMyForm`。</span><span class="sxs-lookup"><span data-stu-id="eb772-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
-   <span data-ttu-id="eb772-107">开始函数和方法名称以动词，如`InitNameArray`或`CloseDialog`。</span><span class="sxs-lookup"><span data-stu-id="eb772-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
-   <span data-ttu-id="eb772-108">开始类、 结构、 模块和属性名称使用名词，如`EmployeeName`或`CarAccessory`。</span><span class="sxs-lookup"><span data-stu-id="eb772-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
-   <span data-ttu-id="eb772-109">开始接口名称以前缀"I"后, 跟名词或名词短语，如`IComponent`，或使用形容词描述接口的行为，如`IPersistable`。</span><span class="sxs-lookup"><span data-stu-id="eb772-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="eb772-110">不使用下划线字符，并且请慎用缩写词，因为缩写可能会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="eb772-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
-   <span data-ttu-id="eb772-111">名词描述类型的事件，随后开始事件处理程序名称"`EventHandler`"后缀，如下所示:"`MouseEventHandler`"。</span><span class="sxs-lookup"><span data-stu-id="eb772-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
-   <span data-ttu-id="eb772-112">在事件参数类的名称，包括"`EventArgs`"后缀。</span><span class="sxs-lookup"><span data-stu-id="eb772-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
-   <span data-ttu-id="eb772-113">如果"before"或"after"事件的概念，请在现在时或过去时，使用后缀，如"`ControlAdd`"或"`ControlAdded`"。</span><span class="sxs-lookup"><span data-stu-id="eb772-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
-   <span data-ttu-id="eb772-114">有关长或经常使用术语，使用缩写保留名称长度合理的例如，"HTML"，而不是"超文本标记语言"。</span><span class="sxs-lookup"><span data-stu-id="eb772-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="eb772-115">一般情况下，变量名称多于 32 个字符难以读取到较低分辨率的监视器上。</span><span class="sxs-lookup"><span data-stu-id="eb772-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="eb772-116">此外，请确保你的缩写词是在整个应用程序保持一致。</span><span class="sxs-lookup"><span data-stu-id="eb772-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="eb772-117">在项目中"HTML"和"超文本标记语言"之间随机切换可能会导致混淆。</span><span class="sxs-lookup"><span data-stu-id="eb772-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
-   <span data-ttu-id="eb772-118">避免使用内层作用域的外部作用域中的名称相同的名称。</span><span class="sxs-lookup"><span data-stu-id="eb772-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="eb772-119">如果访问错误变量时，会导致错误。</span><span class="sxs-lookup"><span data-stu-id="eb772-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="eb772-120">如果变量和具有相同名称的关键字之间发生冲突，则必须标识关键字的前面添加相应的类型库。</span><span class="sxs-lookup"><span data-stu-id="eb772-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="eb772-121">例如，如果有一个名为变量`Date`，可以使用内部函数`Date`只是在调用函数<xref:System.DateTime.Date%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="eb772-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb772-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb772-122">See also</span></span>

- [<span data-ttu-id="eb772-123">代码中用作元素名称的关键字</span><span class="sxs-lookup"><span data-stu-id="eb772-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [<span data-ttu-id="eb772-124">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="eb772-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="eb772-125">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="eb772-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="eb772-126">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="eb772-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="eb772-127">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="eb772-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
