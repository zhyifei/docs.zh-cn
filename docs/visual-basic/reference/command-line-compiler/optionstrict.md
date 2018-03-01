---
title: /optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 692681b21c243432ec8e7160bcc1eaa4e718d64d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="optionstrict"></a><span data-ttu-id="66da2-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="66da2-102">/optionstrict</span></span>
<span data-ttu-id="66da2-103">强制执行严格类型语义来限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="66da2-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66da2-104">语法</span><span class="sxs-lookup"><span data-stu-id="66da2-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="66da2-105">自变量</span><span class="sxs-lookup"><span data-stu-id="66da2-105">Arguments</span></span>  
 <span data-ttu-id="66da2-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="66da2-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="66da2-107">可选。</span><span class="sxs-lookup"><span data-stu-id="66da2-107">Optional.</span></span> <span data-ttu-id="66da2-108">`/optionstrict+`选项将限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="66da2-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="66da2-109">此选项的默认值是`/optionstrict-`。</span><span class="sxs-lookup"><span data-stu-id="66da2-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="66da2-110">`/optionstrict+`选项等同于`/optionstrict`。</span><span class="sxs-lookup"><span data-stu-id="66da2-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="66da2-111">你可以使用这两许可类型语义。</span><span class="sxs-lookup"><span data-stu-id="66da2-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="66da2-112">必须的。</span><span class="sxs-lookup"><span data-stu-id="66da2-112">Required.</span></span> <span data-ttu-id="66da2-113">未遵从严格语言语义时发出警告。</span><span class="sxs-lookup"><span data-stu-id="66da2-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66da2-114">备注</span><span class="sxs-lookup"><span data-stu-id="66da2-114">Remarks</span></span>  
 <span data-ttu-id="66da2-115">当`/optionstrict+`实际上，是可以隐式进行唯一扩大类型转换。</span><span class="sxs-lookup"><span data-stu-id="66da2-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="66da2-116">隐式收缩类型转换，如分配`Decimal`键入指向整数的类型对象的对象，报告为错误。</span><span class="sxs-lookup"><span data-stu-id="66da2-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="66da2-117">若要生成的隐式收缩类型转换的警告，请使用`/optionstrict:custom`。</span><span class="sxs-lookup"><span data-stu-id="66da2-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="66da2-118">使用`/nowarn:numberlist`以忽略特定警告和`/warnaserror:numberlist`特定警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="66da2-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="66da2-119">在 Visual Studio IDE 中设置 /optionstrict</span><span class="sxs-lookup"><span data-stu-id="66da2-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="66da2-120">在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="66da2-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="66da2-121">上**项目**菜单上，单击**属性。**</span><span class="sxs-lookup"><span data-stu-id="66da2-121">On the **Project** menu, click **Properties.**</span></span>   
  
2.  <span data-ttu-id="66da2-122">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="66da2-122">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="66da2-123">修改中的值**Option Strict**框。</span><span class="sxs-lookup"><span data-stu-id="66da2-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="66da2-124">以编程方式设置 /optionstrict</span><span class="sxs-lookup"><span data-stu-id="66da2-124">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="66da2-125">请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="66da2-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66da2-126">示例</span><span class="sxs-lookup"><span data-stu-id="66da2-126">Example</span></span>  
 <span data-ttu-id="66da2-127">下面的代码编译`Test.vb`使用严格类型语义。</span><span class="sxs-lookup"><span data-stu-id="66da2-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="66da2-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="66da2-128">See Also</span></span>  
 [<span data-ttu-id="66da2-129">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="66da2-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="66da2-130">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="66da2-130">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="66da2-131">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="66da2-131">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="66da2-132">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="66da2-132">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="66da2-133">/nowarn</span><span class="sxs-lookup"><span data-stu-id="66da2-133">/nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [<span data-ttu-id="66da2-134">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66da2-134">/warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [<span data-ttu-id="66da2-135">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="66da2-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="66da2-136">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="66da2-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="66da2-137">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="66da2-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
