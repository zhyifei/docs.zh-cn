---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822721"
---
# <a name="-removeintchecks"></a><span data-ttu-id="e3434-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="e3434-102">-removeintchecks</span></span>
<span data-ttu-id="e3434-103">将溢出错误检查对整数运算打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="e3434-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3434-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3434-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e3434-105">自变量</span><span class="sxs-lookup"><span data-stu-id="e3434-105">Arguments</span></span>  
  
|<span data-ttu-id="e3434-106">术语</span><span class="sxs-lookup"><span data-stu-id="e3434-106">Term</span></span>|<span data-ttu-id="e3434-107">定义</span><span class="sxs-lookup"><span data-stu-id="e3434-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="e3434-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e3434-108">`+` &#124; `-`</span></span>|<span data-ttu-id="e3434-109">可选。</span><span class="sxs-lookup"><span data-stu-id="e3434-109">Optional.</span></span> <span data-ttu-id="e3434-110">`-removeintchecks-`选项导致编译器检查所有整数计算中的溢出错误。</span><span class="sxs-lookup"><span data-stu-id="e3434-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="e3434-111">默认值为 `-removeintchecks-`。</span><span class="sxs-lookup"><span data-stu-id="e3434-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="e3434-112">指定`-removeintchecks`或`-removeintchecks+`可以防止错误检查，并使整数计算速度更快。</span><span class="sxs-lookup"><span data-stu-id="e3434-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="e3434-113">但是，不进行错误检查，如果出现溢出数据类型的容量，可能不会生成错误存储不正确的结果。</span><span class="sxs-lookup"><span data-stu-id="e3434-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="e3434-114">在 Visual Studio 集成的开发环境中设置-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="e3434-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e3434-115">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="e3434-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e3434-116">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="e3434-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e3434-117">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="e3434-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e3434-118">3.单击“高级”按钮。</span><span class="sxs-lookup"><span data-stu-id="e3434-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="e3434-119">4.修改的值**整数溢出检查**框。</span><span class="sxs-lookup"><span data-stu-id="e3434-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e3434-120">示例</span><span class="sxs-lookup"><span data-stu-id="e3434-120">Example</span></span>  
 <span data-ttu-id="e3434-121">下面的代码编译`Test.vb`和将禁用整数溢出错误检查。</span><span class="sxs-lookup"><span data-stu-id="e3434-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3434-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3434-122">See also</span></span>

- [<span data-ttu-id="e3434-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="e3434-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e3434-124">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="e3434-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
