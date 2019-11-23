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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005225"
---
# <a name="-removeintchecks"></a><span data-ttu-id="84ec2-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="84ec2-102">-removeintchecks</span></span>
<span data-ttu-id="84ec2-103">启用或禁用对整数操作的溢出错误检查。</span><span class="sxs-lookup"><span data-stu-id="84ec2-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ec2-104">语法</span><span class="sxs-lookup"><span data-stu-id="84ec2-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="84ec2-105">参数</span><span class="sxs-lookup"><span data-stu-id="84ec2-105">Arguments</span></span>  
  
|<span data-ttu-id="84ec2-106">术语</span><span class="sxs-lookup"><span data-stu-id="84ec2-106">Term</span></span>|<span data-ttu-id="84ec2-107">Definition</span><span class="sxs-lookup"><span data-stu-id="84ec2-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="84ec2-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="84ec2-108">`+` &#124; `-`</span></span>|<span data-ttu-id="84ec2-109">可选。</span><span class="sxs-lookup"><span data-stu-id="84ec2-109">Optional.</span></span> <span data-ttu-id="84ec2-110">`-removeintchecks-` 选项导致编译器检查所有整数计算是否存在溢出错误。</span><span class="sxs-lookup"><span data-stu-id="84ec2-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="84ec2-111">默认值为 `-removeintchecks-`。</span><span class="sxs-lookup"><span data-stu-id="84ec2-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="84ec2-112">指定 `-removeintchecks` 或 `-removeintchecks+` 可防止错误检查并可以更快地进行整数计算。</span><span class="sxs-lookup"><span data-stu-id="84ec2-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="84ec2-113">但是，如果不进行错误检查，且数据类型容量溢出，则可能会存储不正确的结果，而不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="84ec2-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="84ec2-114">在 Visual Studio 集成开发环境中设置-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="84ec2-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="84ec2-115">1. 在**解决方案资源管理器**中选择了一个项目。</span><span class="sxs-lookup"><span data-stu-id="84ec2-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="84ec2-116">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="84ec2-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="84ec2-117">2. 单击 "**编译**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="84ec2-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="84ec2-118">3. 单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="84ec2-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="84ec2-119">4. 修改 "**删除整数溢出检查**" 框的值。</span><span class="sxs-lookup"><span data-stu-id="84ec2-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="84ec2-120">示例</span><span class="sxs-lookup"><span data-stu-id="84ec2-120">Example</span></span>  
 <span data-ttu-id="84ec2-121">下面的代码编译 `Test.vb` 并关闭整数溢出错误检查。</span><span class="sxs-lookup"><span data-stu-id="84ec2-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="84ec2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84ec2-122">See also</span></span>

- [<span data-ttu-id="84ec2-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="84ec2-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="84ec2-124">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="84ec2-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
