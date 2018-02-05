---
title: "按位置和名称传递自变量 (Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="65315-102">按位置和名称传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65315-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="65315-103">当调用`Sub`或`Function`过程中，你可以将参数传递*按位置*— 在过程定义中出现的顺序 — 或将它们传递*按名称*，而无需考虑位置。</span><span class="sxs-lookup"><span data-stu-id="65315-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="65315-104">当你按名称传递自变量时，你指定参数的声明名称后跟冒号和等号 (`:=`) 后, 跟自变量值。</span><span class="sxs-lookup"><span data-stu-id="65315-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="65315-105">你可以提供命名自变量的任何顺序。</span><span class="sxs-lookup"><span data-stu-id="65315-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="65315-106">例如，以下`Sub`过程使用三个参数：</span><span class="sxs-lookup"><span data-stu-id="65315-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="65315-107">在调用此过程时，你可以提供的自变量按位置、 按名称，或通过使用这两者的混合。</span><span class="sxs-lookup"><span data-stu-id="65315-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="65315-108">按位置传递自变量</span><span class="sxs-lookup"><span data-stu-id="65315-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="65315-109">你可以调用`Display`具有其自变量方法按位置传递，并且用逗号分隔，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="65315-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="65315-110">如果省略可选的参数位置自变量列表中，你必须保留它用逗号分隔的位置。</span><span class="sxs-lookup"><span data-stu-id="65315-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="65315-111">下面的示例调用`Display`方法，而`age`自变量：</span><span class="sxs-lookup"><span data-stu-id="65315-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="65315-112">按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="65315-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="65315-113">或者，可以调用`Display`按名称传递自变量也用逗号分隔，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="65315-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="65315-114">在调用了具有多个可选参数的过程时，通过以这种方式的名称传递自变量是特别有用。</span><span class="sxs-lookup"><span data-stu-id="65315-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="65315-115">如果按名称提供自变量，你不需要使用连续的逗号来表示缺少位置自变量。</span><span class="sxs-lookup"><span data-stu-id="65315-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="65315-116">按名称传递自变量还可以更轻松地跟踪的哪些参数将传递和你省略哪些功能。</span><span class="sxs-lookup"><span data-stu-id="65315-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="65315-117">混合自变量按位置和名称</span><span class="sxs-lookup"><span data-stu-id="65315-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="65315-118">你可以提供自变量的位置和名称的单一过程调用中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="65315-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="65315-119">在前面的示例中，没有多余的逗号是保存的省略的位置所需`age`自变量，因为`birth`按名称传递了。</span><span class="sxs-lookup"><span data-stu-id="65315-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="65315-120">在 Visual Basic 的 15.5 之前的版本，当你的混合位置和名称、 位置自变量形式提供参数时都必须放在第一个。</span><span class="sxs-lookup"><span data-stu-id="65315-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="65315-121">后按名称提供自变量，剩下的自变量必须所有传递的名称。</span><span class="sxs-lookup"><span data-stu-id="65315-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="65315-122">例如，以下调用`Display`方法显示编译器错误[BC30241： 名为应自变量](../../../misc/bc30241.md)。</span><span class="sxs-lookup"><span data-stu-id="65315-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="65315-123">从 Visual Basic 15.5 开始，位置自变量可以遵循命名自变量的结束位置自变量是否在正确的位置。</span><span class="sxs-lookup"><span data-stu-id="65315-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="65315-124">如果在 Visual Basic 15.5，调用下编译`Display`方法编译成功，而且不再生成编译器错误[BC30241](../../../misc/bc30241.md)。</span><span class="sxs-lookup"><span data-stu-id="65315-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="65315-125">当你想要使用命名自变量以使代码更具可读性，混合和匹配位置和命名的自变量的任何顺序此能力是特别有用。</span><span class="sxs-lookup"><span data-stu-id="65315-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="65315-126">例如，以下`Person`类构造函数需要的类型的两个自变量`Person`，这两种可以是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="65315-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="65315-127">使用混合命名参数和位置参数有助于明确代码的意图清除时的值`father`和`mother`自变量是`Nothing`:</span><span class="sxs-lookup"><span data-stu-id="65315-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="65315-128">若要执行具有命名自变量的位置自变量，必须将下面的元素添加到 Visual Basic 项目 (\*.vbproj) 文件：</span><span class="sxs-lookup"><span data-stu-id="65315-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="65315-129">提供自变量按名称的限制</span><span class="sxs-lookup"><span data-stu-id="65315-129">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="65315-130">你不能按名称来避免输入所需的参数传递自变量。</span><span class="sxs-lookup"><span data-stu-id="65315-130">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="65315-131">可以省略仅的可选自变量。</span><span class="sxs-lookup"><span data-stu-id="65315-131">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="65315-132">你不能按名称传递参数数组。</span><span class="sxs-lookup"><span data-stu-id="65315-132">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="65315-133">这是因为在调用过程时，你提供的参数数组中，逗号分隔的参数数量不确定，并且编译器不能将多个自变量与单个名称关联。</span><span class="sxs-lookup"><span data-stu-id="65315-133">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65315-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="65315-134">See Also</span></span>  
 [<span data-ttu-id="65315-135">过程</span><span class="sxs-lookup"><span data-stu-id="65315-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="65315-136">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="65315-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="65315-137">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="65315-137">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="65315-138">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="65315-138">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="65315-139">可选参数</span><span class="sxs-lookup"><span data-stu-id="65315-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="65315-140">参数数组</span><span class="sxs-lookup"><span data-stu-id="65315-140">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="65315-141">Optional</span><span class="sxs-lookup"><span data-stu-id="65315-141">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="65315-142">ParamArray</span><span class="sxs-lookup"><span data-stu-id="65315-142">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
