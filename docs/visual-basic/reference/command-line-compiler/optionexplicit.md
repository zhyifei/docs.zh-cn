---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266724"
---
# <a name="-optionexplicit"></a><span data-ttu-id="216e3-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="216e3-102">-optionexplicit</span></span>
<span data-ttu-id="216e3-103">如果变量在使用之前未被声明，则会导致编译器报告错误。</span><span class="sxs-lookup"><span data-stu-id="216e3-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="216e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="216e3-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="216e3-105">自变量</span><span class="sxs-lookup"><span data-stu-id="216e3-105">Arguments</span></span>  
 <span data-ttu-id="216e3-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="216e3-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="216e3-107">可选。</span><span class="sxs-lookup"><span data-stu-id="216e3-107">Optional.</span></span> <span data-ttu-id="216e3-108">指定 `-optionexplicit+` 可要求显式声明变量。</span><span class="sxs-lookup"><span data-stu-id="216e3-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="216e3-109">`-optionexplicit+` 选项是默认选项，与 `-optionexplicit` 相同。</span><span class="sxs-lookup"><span data-stu-id="216e3-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="216e3-110">`-optionexplicit-` 选项启用变量的隐式声明。</span><span class="sxs-lookup"><span data-stu-id="216e3-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="216e3-111">备注</span><span class="sxs-lookup"><span data-stu-id="216e3-111">Remarks</span></span>  
 <span data-ttu-id="216e3-112">如果源代码文件包含 [Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)，则语句将重写 `-optionexplicit` 命令行编译器设置。</span><span class="sxs-lookup"><span data-stu-id="216e3-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="216e3-113">若要在 Visual Studio IDE 中设置 -optionexplicit</span><span class="sxs-lookup"><span data-stu-id="216e3-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="216e3-114">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="216e3-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="216e3-115">在“项目”菜单上，单击“属性”   。</span><span class="sxs-lookup"><span data-stu-id="216e3-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="216e3-116">单击“编译”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="216e3-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="216e3-117">修改“Option Explicit”框中的值。 </span><span class="sxs-lookup"><span data-stu-id="216e3-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="216e3-118">示例</span><span class="sxs-lookup"><span data-stu-id="216e3-118">Example</span></span>  
 <span data-ttu-id="216e3-119">以下代码在使用 `-optionexplicit-` 时进行编译。</span><span class="sxs-lookup"><span data-stu-id="216e3-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="216e3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="216e3-120">See also</span></span>

- [<span data-ttu-id="216e3-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="216e3-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="216e3-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="216e3-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="216e3-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="216e3-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="216e3-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="216e3-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="216e3-125">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="216e3-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="216e3-126">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="216e3-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="216e3-127">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="216e3-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
