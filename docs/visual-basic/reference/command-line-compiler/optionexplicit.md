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
ms.openlocfilehash: 54d438541e8840e4394b24b20b4f394ff8cdb820
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788942"
---
# <a name="-optionexplicit"></a><span data-ttu-id="64cca-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="64cca-102">-optionexplicit</span></span>
<span data-ttu-id="64cca-103">如果在使用之前未声明变量，会导致编译器报告错误。</span><span class="sxs-lookup"><span data-stu-id="64cca-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64cca-104">语法</span><span class="sxs-lookup"><span data-stu-id="64cca-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="64cca-105">自变量</span><span class="sxs-lookup"><span data-stu-id="64cca-105">Arguments</span></span>  
 <span data-ttu-id="64cca-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="64cca-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="64cca-107">可选。</span><span class="sxs-lookup"><span data-stu-id="64cca-107">Optional.</span></span> <span data-ttu-id="64cca-108">指定`-optionexplicit+`要求显式声明变量。</span><span class="sxs-lookup"><span data-stu-id="64cca-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="64cca-109">`-optionexplicit+`选项是默认值和相同`-optionexplicit`。</span><span class="sxs-lookup"><span data-stu-id="64cca-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="64cca-110">`-optionexplicit-`选项启用隐式声明变量。</span><span class="sxs-lookup"><span data-stu-id="64cca-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64cca-111">备注</span><span class="sxs-lookup"><span data-stu-id="64cca-111">Remarks</span></span>  
 <span data-ttu-id="64cca-112">如果源代码文件包含[Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)，语句将覆盖`-optionexplicit`命令行编译器设置。</span><span class="sxs-lookup"><span data-stu-id="64cca-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="64cca-113">若要在 Visual Studio IDE 中设置-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="64cca-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="64cca-114">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="64cca-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="64cca-115">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="64cca-115">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="64cca-116">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="64cca-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="64cca-117">修改中的值**Option Explicit**框。</span><span class="sxs-lookup"><span data-stu-id="64cca-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64cca-118">示例</span><span class="sxs-lookup"><span data-stu-id="64cca-118">Example</span></span>  
 <span data-ttu-id="64cca-119">下面的代码编译时`-optionexplicit-`使用。</span><span class="sxs-lookup"><span data-stu-id="64cca-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="64cca-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="64cca-120">See also</span></span>

- [<span data-ttu-id="64cca-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="64cca-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="64cca-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="64cca-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="64cca-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="64cca-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="64cca-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="64cca-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="64cca-125">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="64cca-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="64cca-126">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="64cca-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="64cca-127">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="64cca-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
