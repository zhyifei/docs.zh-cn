---
title: "/nowarn |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 308bf24c2a397a75f36b97062dde7380b90c8994
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="nowarn"></a><span data-ttu-id="2cb61-102">/nowarn</span><span class="sxs-lookup"><span data-stu-id="2cb61-102">/nowarn</span></span>
<span data-ttu-id="2cb61-103">禁止编译器生成警告的能力。</span><span class="sxs-lookup"><span data-stu-id="2cb61-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb61-104">语法</span><span class="sxs-lookup"><span data-stu-id="2cb61-104">Syntax</span></span>  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2cb61-105">参数</span><span class="sxs-lookup"><span data-stu-id="2cb61-105">Arguments</span></span>  
  
|<span data-ttu-id="2cb61-106">术语</span><span class="sxs-lookup"><span data-stu-id="2cb61-106">Term</span></span>|<span data-ttu-id="2cb61-107">定义</span><span class="sxs-lookup"><span data-stu-id="2cb61-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="2cb61-108">可选。</span><span class="sxs-lookup"><span data-stu-id="2cb61-108">Optional.</span></span> <span data-ttu-id="2cb61-109">应该禁止显示编译器警告 ID 号的以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="2cb61-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="2cb61-110">如果未指定 Id 的警告，则会抑制所有警告。</span><span class="sxs-lookup"><span data-stu-id="2cb61-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cb61-111">备注</span><span class="sxs-lookup"><span data-stu-id="2cb61-111">Remarks</span></span>  
 <span data-ttu-id="2cb61-112">`/nowarn`选项将使编译器不生成警告。</span><span class="sxs-lookup"><span data-stu-id="2cb61-112">The `/nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="2cb61-113">若要禁止显示个别警告，请提供警告 ID`/nowarn`冒号之后的选项。</span><span class="sxs-lookup"><span data-stu-id="2cb61-113">To suppress an individual warning, supply the warning ID to the `/nowarn` option following the colon.</span></span> <span data-ttu-id="2cb61-114">用逗号分隔多个警告编号。</span><span class="sxs-lookup"><span data-stu-id="2cb61-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="2cb61-115">您需要指定只有警告标识符的数值部分。</span><span class="sxs-lookup"><span data-stu-id="2cb61-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="2cb61-116">例如，如果您想要禁止显示 BC42024，未使用的局部变量，该警告指定`/nowarn:42024`。</span><span class="sxs-lookup"><span data-stu-id="2cb61-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `/nowarn:42024`.</span></span>  
  
 <span data-ttu-id="2cb61-117">警告 ID 号的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="2cb61-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="2cb61-118">在 Visual Studio 中设置 /nowarn 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="2cb61-118">To set /nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2cb61-119">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="2cb61-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2cb61-120">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2cb61-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="2cb61-121">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="2cb61-121">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="2cb61-122">2.单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="2cb61-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2cb61-123">3.选择**禁用所有警告**复选框以都禁用所有警告。</span><span class="sxs-lookup"><span data-stu-id="2cb61-123">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="2cb61-124">- 或 -</span><span class="sxs-lookup"><span data-stu-id="2cb61-124">- or -</span></span><br />     <span data-ttu-id="2cb61-125">若要禁用特定警告，请单击**无**警告旁边的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="2cb61-125">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2cb61-126">示例</span><span class="sxs-lookup"><span data-stu-id="2cb61-126">Example</span></span>  
 <span data-ttu-id="2cb61-127">下面的代码编译`T2.vb`并且不显示任何警告。</span><span class="sxs-lookup"><span data-stu-id="2cb61-127">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="2cb61-128">示例</span><span class="sxs-lookup"><span data-stu-id="2cb61-128">Example</span></span>  
 <span data-ttu-id="2cb61-129">下面的代码编译`T2.vb`并且不显示未使用的局部变量 (42024) 的警告。</span><span class="sxs-lookup"><span data-stu-id="2cb61-129">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cb61-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cb61-130">See Also</span></span>  
 <span data-ttu-id="2cb61-131">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2cb61-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2cb61-132"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="2cb61-132"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="2cb61-133"> [在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="2cb61-133"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
