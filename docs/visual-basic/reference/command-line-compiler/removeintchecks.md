---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a><span data-ttu-id="8daf9-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="8daf9-102">/removeintchecks</span></span>
<span data-ttu-id="8daf9-103">启用溢出错误检查对整数运算打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="8daf9-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8daf9-104">语法</span><span class="sxs-lookup"><span data-stu-id="8daf9-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8daf9-105">参数</span><span class="sxs-lookup"><span data-stu-id="8daf9-105">Arguments</span></span>  
  
|<span data-ttu-id="8daf9-106">术语</span><span class="sxs-lookup"><span data-stu-id="8daf9-106">Term</span></span>|<span data-ttu-id="8daf9-107">定义</span><span class="sxs-lookup"><span data-stu-id="8daf9-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="8daf9-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8daf9-108">`+` &#124; `-`</span></span>|<span data-ttu-id="8daf9-109">可选。</span><span class="sxs-lookup"><span data-stu-id="8daf9-109">Optional.</span></span> <span data-ttu-id="8daf9-110">`/removeintchecks-`选项使编译器以检查所用的溢出错误的所有整数计算。</span><span class="sxs-lookup"><span data-stu-id="8daf9-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="8daf9-111">默认值为 `/removeintchecks-`。</span><span class="sxs-lookup"><span data-stu-id="8daf9-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="8daf9-112">指定`/removeintchecks`或`/removeintchecks+`禁止错误检查，可以使整数计算速度更快。</span><span class="sxs-lookup"><span data-stu-id="8daf9-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="8daf9-113">但是，如果没有错误检查，而如果数据类型容量被超出，可能不会生成错误存储不正确的结果。</span><span class="sxs-lookup"><span data-stu-id="8daf9-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="8daf9-114">在 Visual Studio 中设置 /removeintchecks 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="8daf9-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8daf9-115">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="8daf9-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8daf9-116">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="8daf9-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="8daf9-117">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="8daf9-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="8daf9-118">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="8daf9-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="8daf9-119">3.单击 **“高级”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="8daf9-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="8daf9-120">4.修改的值**删除整数溢出检查**框。</span><span class="sxs-lookup"><span data-stu-id="8daf9-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8daf9-121">示例</span><span class="sxs-lookup"><span data-stu-id="8daf9-121">Example</span></span>  
 <span data-ttu-id="8daf9-122">下面的代码编译`Test.vb`和将禁用整数溢出错误检查。</span><span class="sxs-lookup"><span data-stu-id="8daf9-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8daf9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8daf9-123">See Also</span></span>  
 [<span data-ttu-id="8daf9-124">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="8daf9-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8daf9-125">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="8daf9-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
