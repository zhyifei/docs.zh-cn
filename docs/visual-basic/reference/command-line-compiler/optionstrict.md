---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788929"
---
# <a name="-optionstrict"></a><span data-ttu-id="35694-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="35694-102">-optionstrict</span></span>
<span data-ttu-id="35694-103">强制执行严格类型语义来限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="35694-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35694-104">语法</span><span class="sxs-lookup"><span data-stu-id="35694-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="35694-105">自变量</span><span class="sxs-lookup"><span data-stu-id="35694-105">Arguments</span></span>  
 <span data-ttu-id="35694-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="35694-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="35694-107">可选。</span><span class="sxs-lookup"><span data-stu-id="35694-107">Optional.</span></span> <span data-ttu-id="35694-108">`-optionstrict+`选项将限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="35694-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="35694-109">此选项的默认值是`-optionstrict-`。</span><span class="sxs-lookup"><span data-stu-id="35694-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="35694-110">`-optionstrict+`选项等同于`-optionstrict`。</span><span class="sxs-lookup"><span data-stu-id="35694-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="35694-111">可以使用同时用于许可类型语义。</span><span class="sxs-lookup"><span data-stu-id="35694-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="35694-112">必需。</span><span class="sxs-lookup"><span data-stu-id="35694-112">Required.</span></span> <span data-ttu-id="35694-113">当未遵从严格语言语义时发出警告。</span><span class="sxs-lookup"><span data-stu-id="35694-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35694-114">备注</span><span class="sxs-lookup"><span data-stu-id="35694-114">Remarks</span></span>  
 <span data-ttu-id="35694-115">当`-optionstrict+`有效时，是可以隐式进行唯一扩大类型转换。</span><span class="sxs-lookup"><span data-stu-id="35694-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="35694-116">隐式收缩类型转换，例如分配`Decimal`键入指向整数的类型对象的对象，将报告为错误。</span><span class="sxs-lookup"><span data-stu-id="35694-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="35694-117">若要生成的隐式收缩类型转换警告，请使用`-optionstrict:custom`。</span><span class="sxs-lookup"><span data-stu-id="35694-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="35694-118">使用`-nowarn:numberlist`忽略特定警告和`-warnaserror:numberlist`将特定警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="35694-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="35694-119">若要在 Visual Studio IDE 中设置-optionstrict</span><span class="sxs-lookup"><span data-stu-id="35694-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="35694-120">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="35694-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="35694-121">上**项目**菜单上，单击**属性。**</span><span class="sxs-lookup"><span data-stu-id="35694-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="35694-122">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="35694-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="35694-123">修改中的值**Option Strict**框。</span><span class="sxs-lookup"><span data-stu-id="35694-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="35694-124">若要以编程方式设置-optionstrict</span><span class="sxs-lookup"><span data-stu-id="35694-124">To set -optionstrict programmatically</span></span>  
  
- <span data-ttu-id="35694-125">请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="35694-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35694-126">示例</span><span class="sxs-lookup"><span data-stu-id="35694-126">Example</span></span>  
 <span data-ttu-id="35694-127">下面的代码编译`Test.vb`使用严格类型语义。</span><span class="sxs-lookup"><span data-stu-id="35694-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="35694-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="35694-128">See also</span></span>

- [<span data-ttu-id="35694-129">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="35694-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="35694-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="35694-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="35694-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="35694-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="35694-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="35694-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="35694-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="35694-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="35694-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35694-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="35694-135">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="35694-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="35694-136">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="35694-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="35694-137">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="35694-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
