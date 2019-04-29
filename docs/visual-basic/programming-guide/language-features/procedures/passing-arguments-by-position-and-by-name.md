---
title: 按位置和名称传递自变量 (Visual Basic)
ms.date: 02/01/2018
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
ms.openlocfilehash: b872eda97d1e349ad781b12810e4b166d6e46fe1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791880"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="421b6-102">按位置和名称传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="421b6-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="421b6-103">当您调用`Sub`或`Function`过程中，您可以将参数传递*按位置*— 过程的定义中出现的顺序，或将它们传递*按名称*，而无需考虑位置。</span><span class="sxs-lookup"><span data-stu-id="421b6-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="421b6-104">如果按名称传递参数，指定自变量的声明名称后, 跟一个冒号和等号 (`:=`) 后, 跟参数值。</span><span class="sxs-lookup"><span data-stu-id="421b6-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="421b6-105">你可以提供按任意顺序的命名的参数。</span><span class="sxs-lookup"><span data-stu-id="421b6-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="421b6-106">例如，以下`Sub`过程使用三个参数：</span><span class="sxs-lookup"><span data-stu-id="421b6-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="421b6-107">在调用此过程时，可以提供的参数按位置、 名称，或通过使用这两者的混合。</span><span class="sxs-lookup"><span data-stu-id="421b6-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="421b6-108">按位置传递参数</span><span class="sxs-lookup"><span data-stu-id="421b6-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="421b6-109">您可以调用`Display`方法及其参数按位置传递，并且用逗号分隔，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="421b6-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="421b6-110">如果省略位置自变量列表中的可选自变量，必须保留它以一个逗号后的位置。</span><span class="sxs-lookup"><span data-stu-id="421b6-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="421b6-111">下面的示例调用`Display`方法，而`age`参数：</span><span class="sxs-lookup"><span data-stu-id="421b6-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="421b6-112">按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="421b6-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="421b6-113">或者，可以调用`Display`使用按名称传递参数，还以逗号分隔，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="421b6-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="421b6-114">按这种方式中的名称传递自变量时，尤其是调用具有多个可选参数的过程。</span><span class="sxs-lookup"><span data-stu-id="421b6-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="421b6-115">如果按名称提供实参，你无需使用连续的逗号来表示缺少位置自变量。</span><span class="sxs-lookup"><span data-stu-id="421b6-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="421b6-116">按名称传递自变量还可以更轻松地跟踪的传递以及哪些省略的参数。</span><span class="sxs-lookup"><span data-stu-id="421b6-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="421b6-117">混合参数按位置和名称</span><span class="sxs-lookup"><span data-stu-id="421b6-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="421b6-118">下面的示例中所示，可以提供参数按位置和通过在单个过程调用中，名称：</span><span class="sxs-lookup"><span data-stu-id="421b6-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="421b6-119">在前面的示例中，没有多余的逗号，才可保存的位置的省略`age`自变量，因为`birth`按名称传递了。</span><span class="sxs-lookup"><span data-stu-id="421b6-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="421b6-120">在 Visual basic 15.5 之前的版本，在你的混合位置和名称、 位置自变量形式提供参数时都必须放在第一个。</span><span class="sxs-lookup"><span data-stu-id="421b6-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="421b6-121">按名称提供参数后, 剩下的自变量必须所有传递的名称。</span><span class="sxs-lookup"><span data-stu-id="421b6-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="421b6-122">例如，以下调用到`Display`方法会显示编译器错误[BC30241:需要命名参数](../../../misc/bc30241.md)。</span><span class="sxs-lookup"><span data-stu-id="421b6-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="421b6-123">从 Visual Basic 15.5 开始，位置自变量可以按照命名的自变量的结束位置自变量是否在正确的位置。</span><span class="sxs-lookup"><span data-stu-id="421b6-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="421b6-124">如果在 Visual Basic 15.5 中，以前调用下编译`Display`方法已成功编译并不再生成编译器错误[BC30241](../../../misc/bc30241.md)。</span><span class="sxs-lookup"><span data-stu-id="421b6-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="421b6-125">当你想要使用命名的参数以使代码更具可读性时，此能力混合和匹配命名参数和位置参数按任意顺序是特别有用。</span><span class="sxs-lookup"><span data-stu-id="421b6-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="421b6-126">例如，以下`Person`类构造函数需要两个参数的类型`Person`，这两种可能`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="421b6-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="421b6-127">使用混合命名参数和位置参数有助于使代码意图清除时的值`father`并`mother`自变量是`Nothing`:</span><span class="sxs-lookup"><span data-stu-id="421b6-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="421b6-128">若要执行使用命名参数的位置参数，必须将以下元素添加到 Visual Basic 项目 (\*.vbproj) 文件：</span><span class="sxs-lookup"><span data-stu-id="421b6-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="421b6-129">有关详细信息请参阅[设置的 Visual Basic 语言版本](../../../language-reference/configure-language-version.md)。</span><span class="sxs-lookup"><span data-stu-id="421b6-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="421b6-130">通过名称提供参数的限制</span><span class="sxs-lookup"><span data-stu-id="421b6-130">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="421b6-131">不能按名称来避免输入所需的参数传递参数。</span><span class="sxs-lookup"><span data-stu-id="421b6-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="421b6-132">可以省略仅的可选参数。</span><span class="sxs-lookup"><span data-stu-id="421b6-132">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="421b6-133">不能按名称传递参数数组。</span><span class="sxs-lookup"><span data-stu-id="421b6-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="421b6-134">这是因为时调用该过程，你会提供以逗号分隔参数数组的参数数量不确定，编译器不能将多个自变量关联与单个名称。</span><span class="sxs-lookup"><span data-stu-id="421b6-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421b6-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="421b6-135">See also</span></span>

- [<span data-ttu-id="421b6-136">过程</span><span class="sxs-lookup"><span data-stu-id="421b6-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="421b6-137">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="421b6-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="421b6-138">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="421b6-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="421b6-139">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="421b6-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="421b6-140">可选参数</span><span class="sxs-lookup"><span data-stu-id="421b6-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="421b6-141">参数数组</span><span class="sxs-lookup"><span data-stu-id="421b6-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="421b6-142">Optional</span><span class="sxs-lookup"><span data-stu-id="421b6-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="421b6-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="421b6-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
