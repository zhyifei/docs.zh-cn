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
ms.openlocfilehash: 469e22aef9d746fc55e04ba884d17d60d8baa85a
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583078"
---
# <a name="-optionstrict"></a><span data-ttu-id="bf899-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="bf899-102">-optionstrict</span></span>

<span data-ttu-id="bf899-103">强制执行严格类型语义，限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="bf899-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf899-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf899-104">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="bf899-105">自变量</span><span class="sxs-lookup"><span data-stu-id="bf899-105">Arguments</span></span>

<span data-ttu-id="bf899-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bf899-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="bf899-107">可选。</span><span class="sxs-lookup"><span data-stu-id="bf899-107">Optional.</span></span> <span data-ttu-id="bf899-108">`-optionstrict+` 选项限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="bf899-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="bf899-109">此选项的默认值为 `-optionstrict-`。</span><span class="sxs-lookup"><span data-stu-id="bf899-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="bf899-110">`-optionstrict+` 选项与 `-optionstrict` 相同。</span><span class="sxs-lookup"><span data-stu-id="bf899-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="bf899-111">两者均可用于宽松类型语义。</span><span class="sxs-lookup"><span data-stu-id="bf899-111">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="bf899-112">必需。</span><span class="sxs-lookup"><span data-stu-id="bf899-112">Required.</span></span> <span data-ttu-id="bf899-113">不遵从严格语言语义时发出警告。</span><span class="sxs-lookup"><span data-stu-id="bf899-113">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf899-114">备注</span><span class="sxs-lookup"><span data-stu-id="bf899-114">Remarks</span></span>

<span data-ttu-id="bf899-115">`-optionstrict+` 生效时，仅可隐式生成扩大类型转换。</span><span class="sxs-lookup"><span data-stu-id="bf899-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="bf899-116">隐式收缩类型转换将被报告为错误，例如将 `Decimal` 类型对象分配给整数类型对象。</span><span class="sxs-lookup"><span data-stu-id="bf899-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="bf899-117">若要针对隐式收缩类型转换生成警告，请使用 `-optionstrict:custom`。</span><span class="sxs-lookup"><span data-stu-id="bf899-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="bf899-118">使用 `-nowarn:numberlist` 可忽略特定警告，使用 `-warnaserror:numberlist` 可将特定警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="bf899-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="bf899-119">在 Visual Studio IDE 中设置 -optionstrict</span><span class="sxs-lookup"><span data-stu-id="bf899-119">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="bf899-120">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="bf899-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bf899-121">在“项目”菜单上，单击“属性”   。</span><span class="sxs-lookup"><span data-stu-id="bf899-121">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="bf899-122">单击“编译”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="bf899-122">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="bf899-123">修改“Option Strict”框中的值。 </span><span class="sxs-lookup"><span data-stu-id="bf899-123">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="bf899-124">以编程方式设置 -optionstrict</span><span class="sxs-lookup"><span data-stu-id="bf899-124">To set -optionstrict programmatically</span></span>

<span data-ttu-id="bf899-125">请参阅 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="bf899-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="bf899-126">示例</span><span class="sxs-lookup"><span data-stu-id="bf899-126">Example</span></span>

<span data-ttu-id="bf899-127">下面的代码使用严格类型语义编译 `Test.vb`。</span><span class="sxs-lookup"><span data-stu-id="bf899-127">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="bf899-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf899-128">See also</span></span>

- [<span data-ttu-id="bf899-129">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="bf899-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bf899-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="bf899-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="bf899-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="bf899-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="bf899-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="bf899-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="bf899-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="bf899-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="bf899-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf899-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="bf899-135">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="bf899-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="bf899-136">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="bf899-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="bf899-137">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="bf899-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
