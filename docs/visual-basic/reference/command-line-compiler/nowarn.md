---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005399"
---
# <a name="-nowarn"></a><span data-ttu-id="62b3d-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="62b3d-102">-nowarn</span></span>
<span data-ttu-id="62b3d-103">禁止编译器生成警告的能力。</span><span class="sxs-lookup"><span data-stu-id="62b3d-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="62b3d-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="62b3d-105">参数</span><span class="sxs-lookup"><span data-stu-id="62b3d-105">Arguments</span></span>  
  
|<span data-ttu-id="62b3d-106">术语</span><span class="sxs-lookup"><span data-stu-id="62b3d-106">Term</span></span>|<span data-ttu-id="62b3d-107">定义</span><span class="sxs-lookup"><span data-stu-id="62b3d-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="62b3d-108">可选。</span><span class="sxs-lookup"><span data-stu-id="62b3d-108">Optional.</span></span> <span data-ttu-id="62b3d-109">编译器应禁止显示的警告 ID 号的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="62b3d-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="62b3d-110">如果未指定警告 Id，将禁止显示所有警告。</span><span class="sxs-lookup"><span data-stu-id="62b3d-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62b3d-111">备注</span><span class="sxs-lookup"><span data-stu-id="62b3d-111">Remarks</span></span>  
 <span data-ttu-id="62b3d-112">@No__t-0 选项导致编译器不会生成警告。</span><span class="sxs-lookup"><span data-stu-id="62b3d-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="62b3d-113">若要禁止显示单个警告，请将警告 ID 提供给后面跟在冒号后面的 `-nowarn` 选项。</span><span class="sxs-lookup"><span data-stu-id="62b3d-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="62b3d-114">用逗号分隔多个警告编号。</span><span class="sxs-lookup"><span data-stu-id="62b3d-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="62b3d-115">只需指定警告标识符的数值部分。</span><span class="sxs-lookup"><span data-stu-id="62b3d-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="62b3d-116">例如，如果要禁止显示 BC42024，则对未使用的局部变量指定警告，指定 `-nowarn:42024`。</span><span class="sxs-lookup"><span data-stu-id="62b3d-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="62b3d-117">有关警告 ID 号的详细信息，请参阅[在 Visual Basic 中配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="62b3d-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="62b3d-118">在 Visual Studio 集成开发环境中设置-nowarn</span><span class="sxs-lookup"><span data-stu-id="62b3d-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="62b3d-119">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="62b3d-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="62b3d-120">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="62b3d-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="62b3d-121">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="62b3d-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="62b3d-122">3.选中 "**禁用所有警告**" 复选框以禁用所有警告。</span><span class="sxs-lookup"><span data-stu-id="62b3d-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="62b3d-123">- 或 -</span><span class="sxs-lookup"><span data-stu-id="62b3d-123">- or -</span></span><br />     <span data-ttu-id="62b3d-124">若要禁用特定警告，请在警告旁边的下拉列表中单击 "**无**"。</span><span class="sxs-lookup"><span data-stu-id="62b3d-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="62b3d-125">示例</span><span class="sxs-lookup"><span data-stu-id="62b3d-125">Example</span></span>  
 <span data-ttu-id="62b3d-126">下面的代码编译 `T2.vb`，并且不显示任何警告。</span><span class="sxs-lookup"><span data-stu-id="62b3d-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="62b3d-127">示例</span><span class="sxs-lookup"><span data-stu-id="62b3d-127">Example</span></span>  
 <span data-ttu-id="62b3d-128">下面的代码编译 `T2.vb`，并且不显示未使用的局部变量（42024）的警告。</span><span class="sxs-lookup"><span data-stu-id="62b3d-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="62b3d-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="62b3d-129">See also</span></span>

- [<span data-ttu-id="62b3d-130">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="62b3d-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="62b3d-131">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="62b3d-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="62b3d-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62b3d-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
