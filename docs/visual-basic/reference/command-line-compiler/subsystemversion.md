---
title: "/subsystemversion (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
caps.latest.revision: 9
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
ms.openlocfilehash: efeade3fcde18f02b3a760adc50d3555df6c9ed7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="subsystemversion-visual-basic"></a><span data-ttu-id="1610d-102">/subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1610d-102">/subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="1610d-103">指定在其可以运行生成的可执行文件，由此决定用的可执行文件可以在其运行的 Windows 版本的子系统的最低版本。</span><span class="sxs-lookup"><span data-stu-id="1610d-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="1610d-104">大多数情况下，此选项可确保可执行文件可以利用无法适用于 Windows 的早期版本的特定安全功能。</span><span class="sxs-lookup"><span data-stu-id="1610d-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1610d-105">若要指定子系统本身，请使用[target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)编译器选项。</span><span class="sxs-lookup"><span data-stu-id="1610d-105">To specify the subsystem itself, use the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1610d-106">语法</span><span class="sxs-lookup"><span data-stu-id="1610d-106">Syntax</span></span>  
  
```vb  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1610d-107">参数</span><span class="sxs-lookup"><span data-stu-id="1610d-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="1610d-108">所需的最低版本的子系统，如在主要和次要版本圆点表示法表示。</span><span class="sxs-lookup"><span data-stu-id="1610d-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="1610d-109">例如，您可以指定应用程序不能低于 Windows 7 如果将此选项的值设置为 6.01，如本主题后面的表中所述的操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="1610d-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="1610d-110">您必须指定的值`major`和`minor`为整数。</span><span class="sxs-lookup"><span data-stu-id="1610d-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="1610d-111">的前导零`minor`版本不会更改版本，但尾随零。</span><span class="sxs-lookup"><span data-stu-id="1610d-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="1610d-112">例如，6.1 和 6.01 引用相同的版本，但是 6.10 引用与另一个版本。</span><span class="sxs-lookup"><span data-stu-id="1610d-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="1610d-113">我们建议为一个两位数，以避免混淆表达的次版本。</span><span class="sxs-lookup"><span data-stu-id="1610d-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1610d-114">备注</span><span class="sxs-lookup"><span data-stu-id="1610d-114">Remarks</span></span>  
 <span data-ttu-id="1610d-115">下表列出常见的子系统版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="1610d-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="1610d-116">Windows 版本</span><span class="sxs-lookup"><span data-stu-id="1610d-116">Windows version</span></span>|<span data-ttu-id="1610d-117">子系统版本</span><span class="sxs-lookup"><span data-stu-id="1610d-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="1610d-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="1610d-118">Windows 2000</span></span>|<span data-ttu-id="1610d-119">5.00</span><span class="sxs-lookup"><span data-stu-id="1610d-119">5.00</span></span>|  
|<span data-ttu-id="1610d-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="1610d-120">Windows XP</span></span>|<span data-ttu-id="1610d-121">5.01</span><span class="sxs-lookup"><span data-stu-id="1610d-121">5.01</span></span>|  
|<span data-ttu-id="1610d-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="1610d-122">Windows Server 2003</span></span>|<span data-ttu-id="1610d-123">5.02</span><span class="sxs-lookup"><span data-stu-id="1610d-123">5.02</span></span>|  
|<span data-ttu-id="1610d-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="1610d-124">Windows Vista</span></span>|<span data-ttu-id="1610d-125">6.00</span><span class="sxs-lookup"><span data-stu-id="1610d-125">6.00</span></span>|  
|<span data-ttu-id="1610d-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1610d-126">Windows 7</span></span>|<span data-ttu-id="1610d-127">6.01</span><span class="sxs-lookup"><span data-stu-id="1610d-127">6.01</span></span>|  
|<span data-ttu-id="1610d-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="1610d-128">Windows Server 2008</span></span>|<span data-ttu-id="1610d-129">6.01</span><span class="sxs-lookup"><span data-stu-id="1610d-129">6.01</span></span>|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8_md.md)]|<span data-ttu-id="1610d-130">6.02</span><span class="sxs-lookup"><span data-stu-id="1610d-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="1610d-131">默认值</span><span class="sxs-lookup"><span data-stu-id="1610d-131">Default values</span></span>  
 <span data-ttu-id="1610d-132">默认值为**/subsystemversion**编译器选项取决于下面的列表中的条件︰</span><span class="sxs-lookup"><span data-stu-id="1610d-132">The default value of the **/subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="1610d-133">默认值为 6.02，如果设置了以下列表中的任何编译器选项︰</span><span class="sxs-lookup"><span data-stu-id="1610d-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="1610d-134">/target: appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="1610d-134">/target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="1610d-135">/target: winmdobj</span><span class="sxs-lookup"><span data-stu-id="1610d-135">/target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="1610d-136">/platform:arm</span><span class="sxs-lookup"><span data-stu-id="1610d-136">/platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="1610d-137">默认值是 6.00，如果你使用 MSBuild，您的目标[!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)]，并没有设置任何先前在此列表中已指定的编译器选项。</span><span class="sxs-lookup"><span data-stu-id="1610d-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="1610d-138">如果无前几个条件为 true，则默认值是 4.00。</span><span class="sxs-lookup"><span data-stu-id="1610d-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="1610d-139">设置此选项</span><span class="sxs-lookup"><span data-stu-id="1610d-139">Setting this option</span></span>  
 <span data-ttu-id="1610d-140">若要设置**/subsystemversion**编译器选项在 Visual Studio 中，您必须打开.vbproj 文件，并为指定值`SubsystemVersion`MSBuild XML 中的属性。</span><span class="sxs-lookup"><span data-stu-id="1610d-140">To set the **/subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="1610d-141">不能在 Visual Studio IDE 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1610d-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="1610d-142">有关详细信息，请参阅"默认值本主题前面的或[常用的 MSBuild 项目属性](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties)。</span><span class="sxs-lookup"><span data-stu-id="1610d-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="1610d-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1610d-143">See Also</span></span>  
[<span data-ttu-id="1610d-144">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="1610d-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="1610d-145">MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="1610d-145">MSBuild Properties</span></span>](https://docs.microsoft.com/visualstudio/msbuild/msbuild-properties)

