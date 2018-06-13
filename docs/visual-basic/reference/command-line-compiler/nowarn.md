---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 338b4672d215968275c30d37a2f8061e764aed8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653437"
---
# <a name="-nowarn"></a><span data-ttu-id="4e892-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="4e892-102">-nowarn</span></span>
<span data-ttu-id="4e892-103">禁止编译器生成警告的能力。</span><span class="sxs-lookup"><span data-stu-id="4e892-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e892-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e892-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4e892-105">自变量</span><span class="sxs-lookup"><span data-stu-id="4e892-105">Arguments</span></span>  
  
|<span data-ttu-id="4e892-106">术语</span><span class="sxs-lookup"><span data-stu-id="4e892-106">Term</span></span>|<span data-ttu-id="4e892-107">定义</span><span class="sxs-lookup"><span data-stu-id="4e892-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="4e892-108">可选。</span><span class="sxs-lookup"><span data-stu-id="4e892-108">Optional.</span></span> <span data-ttu-id="4e892-109">应禁止显示编译器警告 ID 号的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="4e892-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="4e892-110">如果未指定警告 Id，则取消所有警告。</span><span class="sxs-lookup"><span data-stu-id="4e892-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e892-111">备注</span><span class="sxs-lookup"><span data-stu-id="4e892-111">Remarks</span></span>  
 <span data-ttu-id="4e892-112">`-nowarn`选项使编译器不会生成警告。</span><span class="sxs-lookup"><span data-stu-id="4e892-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="4e892-113">若要禁止显示个别警告，提供到的警告 ID`-nowarn`冒号之后的选项。</span><span class="sxs-lookup"><span data-stu-id="4e892-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="4e892-114">用逗号分隔多个警告编号。</span><span class="sxs-lookup"><span data-stu-id="4e892-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="4e892-115">你需要指定只有警告标识符数字部分。</span><span class="sxs-lookup"><span data-stu-id="4e892-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="4e892-116">例如，如果你想要禁止显示 BC42024，对于未使用的本地变量，警告指定`-nowarn:42024`。</span><span class="sxs-lookup"><span data-stu-id="4e892-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="4e892-117">警告 ID 号的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="4e892-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="4e892-118">在 Visual Studio 集成的开发环境中设置-nowarn</span><span class="sxs-lookup"><span data-stu-id="4e892-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4e892-119">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="4e892-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4e892-120">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="4e892-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="4e892-121">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4e892-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4e892-122">3.选择**禁用所有警告**复选框以都禁用所有警告。</span><span class="sxs-lookup"><span data-stu-id="4e892-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="4e892-123">- 或 -</span><span class="sxs-lookup"><span data-stu-id="4e892-123">- or -</span></span><br />     <span data-ttu-id="4e892-124">若要禁用特定警告，请单击**无**对此警告旁边的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="4e892-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4e892-125">示例</span><span class="sxs-lookup"><span data-stu-id="4e892-125">Example</span></span>  
 <span data-ttu-id="4e892-126">下面的代码编译`T2.vb`并且不显示任何警告。</span><span class="sxs-lookup"><span data-stu-id="4e892-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="4e892-127">示例</span><span class="sxs-lookup"><span data-stu-id="4e892-127">Example</span></span>  
 <span data-ttu-id="4e892-128">下面的代码编译`T2.vb`并且不显示为未使用的局部变量 (42024) 的警告。</span><span class="sxs-lookup"><span data-stu-id="4e892-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e892-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e892-129">See Also</span></span>  
 [<span data-ttu-id="4e892-130">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="4e892-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4e892-131">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="4e892-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="4e892-132">在 Visual Basic 中配置警告</span><span class="sxs-lookup"><span data-stu-id="4e892-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
