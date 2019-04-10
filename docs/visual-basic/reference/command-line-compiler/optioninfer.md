---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: f1dcc03a67880727893e55c13d65a804586b3f56
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315499"
---
# <a name="-optioninfer"></a><span data-ttu-id="224bd-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="224bd-102">-optioninfer</span></span>
<span data-ttu-id="224bd-103">允许在变量声明中使用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="224bd-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="224bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="224bd-104">Syntax</span></span>  
  
```  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="224bd-105">自变量</span><span class="sxs-lookup"><span data-stu-id="224bd-105">Arguments</span></span>  
  
|<span data-ttu-id="224bd-106">术语</span><span class="sxs-lookup"><span data-stu-id="224bd-106">Term</span></span>|<span data-ttu-id="224bd-107">定义</span><span class="sxs-lookup"><span data-stu-id="224bd-107">Definition</span></span>|  
|---|---|  
|`+` <span data-ttu-id="224bd-108">&#124;</span><span class="sxs-lookup"><span data-stu-id="224bd-108">&#124;</span></span> `-`|<span data-ttu-id="224bd-109">可选。</span><span class="sxs-lookup"><span data-stu-id="224bd-109">Optional.</span></span> <span data-ttu-id="224bd-110">指定 `-optioninfer+` 来启用局部类型推理，或指定 `-optioninfer-` 来阻止它。</span><span class="sxs-lookup"><span data-stu-id="224bd-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="224bd-111">没有指定值的 `-optioninfer` 选项等同于 `-optioninfer+`。</span><span class="sxs-lookup"><span data-stu-id="224bd-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="224bd-112">不存在 `-optioninfer` 切换时，默认值也是 `-optioninfer+`。</span><span class="sxs-lookup"><span data-stu-id="224bd-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="224bd-113">在 Vbc.rsp 响应文件中设置了默认值。</span><span class="sxs-lookup"><span data-stu-id="224bd-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="224bd-114">你可使用 `-noconfig` 选项来保留编译器的内部默认值(而非在 vbc.rsp 中指定的那些值）。</span><span class="sxs-lookup"><span data-stu-id="224bd-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="224bd-115">此选项默认的编译器是 `-optioninfer-`。</span><span class="sxs-lookup"><span data-stu-id="224bd-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="224bd-116">备注</span><span class="sxs-lookup"><span data-stu-id="224bd-116">Remarks</span></span>  
 <span data-ttu-id="224bd-117">如果源代码文件包含[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)，语句将覆盖`-optioninfer`命令行编译器设置。</span><span class="sxs-lookup"><span data-stu-id="224bd-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="224bd-118">若要在 Visual Studio IDE 中设置-optioninfer</span><span class="sxs-lookup"><span data-stu-id="224bd-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="224bd-119">选择的项目中**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="224bd-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="224bd-120">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="224bd-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="224bd-121">上**编译**选项卡上，修改中的值**Option infer**框。</span><span class="sxs-lookup"><span data-stu-id="224bd-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="224bd-122">示例</span><span class="sxs-lookup"><span data-stu-id="224bd-122">Example</span></span>  
 <span data-ttu-id="224bd-123">以下代码在启用局部类型推理的情况下编译 `test.vb`。</span><span class="sxs-lookup"><span data-stu-id="224bd-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="224bd-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="224bd-124">See also</span></span>

- [<span data-ttu-id="224bd-125">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="224bd-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="224bd-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="224bd-126">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="224bd-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="224bd-127">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="224bd-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="224bd-128">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="224bd-129">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="224bd-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="224bd-130">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="224bd-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="224bd-131">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="224bd-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="224bd-132">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="224bd-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="224bd-133">“编译”页, 项目设计器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="224bd-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="224bd-134">/noconfig</span><span class="sxs-lookup"><span data-stu-id="224bd-134">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="224bd-135">从命令行生成</span><span class="sxs-lookup"><span data-stu-id="224bd-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
