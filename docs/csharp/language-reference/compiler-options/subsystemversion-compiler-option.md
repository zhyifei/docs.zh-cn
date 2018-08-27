---
title: -subsystemversion（C# 编译器选项）
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: 25391dd504fb8a2b9458fd9495477258fc23d81a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001388"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="8f6bc-102">-subsystemversion（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="8f6bc-102">-subsystemversion (C# Compiler Options)</span></span>
<span data-ttu-id="8f6bc-103">指定可以运行生成的可执行文件的子系统的最低版本，以此确定可以运行该可执行文件的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="8f6bc-104">大多数情况下，此选项确保该可执行文件可以利用早期 Windows 版本中未提供的特定安全功能。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f6bc-105">若要指定子系统本身，请使用 [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6bc-106">语法</span><span class="sxs-lookup"><span data-stu-id="8f6bc-106">Syntax</span></span>  
  
```console  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f6bc-107">参数</span><span class="sxs-lookup"><span data-stu-id="8f6bc-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="8f6bc-108">所需的子系统最低版本，以主版本和次要版本之间使用点标记的方式表示。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="8f6bc-109">例如，如果将此选项的值设置为 6.01，则可以指定应用程序不能在低于 Windows 7 的操作系统上运行（如本主题后面的表中所述）。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="8f6bc-110">必须将 `major` 和 `minor` 的值指定为整数。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="8f6bc-111">`minor` 版本中的前导零不会更改版本，但尾随零会。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="8f6bc-112">例如，6.1 和 6.01 表示相同的版本，但 6.10 表示另一个版本。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="8f6bc-113">建议次要版本用两位数表示，以免混淆。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f6bc-114">备注</span><span class="sxs-lookup"><span data-stu-id="8f6bc-114">Remarks</span></span>  
 <span data-ttu-id="8f6bc-115">下表列出了常见的 Windows 子系统版本。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="8f6bc-116">Windows 版本</span><span class="sxs-lookup"><span data-stu-id="8f6bc-116">Windows version</span></span>|<span data-ttu-id="8f6bc-117">子系统版本</span><span class="sxs-lookup"><span data-stu-id="8f6bc-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="8f6bc-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="8f6bc-118">Windows 2000</span></span>|<span data-ttu-id="8f6bc-119">5.00</span><span class="sxs-lookup"><span data-stu-id="8f6bc-119">5.00</span></span>|  
|<span data-ttu-id="8f6bc-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="8f6bc-120">Windows XP</span></span>|<span data-ttu-id="8f6bc-121">5.01</span><span class="sxs-lookup"><span data-stu-id="8f6bc-121">5.01</span></span>|  
|<span data-ttu-id="8f6bc-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="8f6bc-122">Windows Server 2003</span></span>|<span data-ttu-id="8f6bc-123">5.02</span><span class="sxs-lookup"><span data-stu-id="8f6bc-123">5.02</span></span>|  
|<span data-ttu-id="8f6bc-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="8f6bc-124">Windows Vista</span></span>|<span data-ttu-id="8f6bc-125">6.00</span><span class="sxs-lookup"><span data-stu-id="8f6bc-125">6.00</span></span>|  
|<span data-ttu-id="8f6bc-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8f6bc-126">Windows 7</span></span>|<span data-ttu-id="8f6bc-127">6.01</span><span class="sxs-lookup"><span data-stu-id="8f6bc-127">6.01</span></span>|  
|<span data-ttu-id="8f6bc-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="8f6bc-128">Windows Server 2008</span></span>|<span data-ttu-id="8f6bc-129">6.01</span><span class="sxs-lookup"><span data-stu-id="8f6bc-129">6.01</span></span>|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="8f6bc-130">6.02</span><span class="sxs-lookup"><span data-stu-id="8f6bc-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="8f6bc-131">默认值</span><span class="sxs-lookup"><span data-stu-id="8f6bc-131">Default values</span></span>  
 <span data-ttu-id="8f6bc-132">-subsystemversion 编译器选项的默认值取决于以下列表中的条件：</span><span class="sxs-lookup"><span data-stu-id="8f6bc-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="8f6bc-133">只要设置了以下列表中的任意编译器选项，则默认值为 6.02：</span><span class="sxs-lookup"><span data-stu-id="8f6bc-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="8f6bc-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="8f6bc-134">-target:appcontainerexe</span></span>](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [<span data-ttu-id="8f6bc-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="8f6bc-135">-target:winmdobj</span></span>](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [<span data-ttu-id="8f6bc-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="8f6bc-136">-platform:arm</span></span>](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   <span data-ttu-id="8f6bc-137">如果使用 MSBuild，面向 [!INCLUDE[net_v45](~/includes/net-v45-md.md)]，并且未设置先前在此列表中指定的任何编译器选项，则默认值为 6.00。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="8f6bc-138">如果前面的条件均不符合，则默认值为 4.00。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="8f6bc-139">设置此选项</span><span class="sxs-lookup"><span data-stu-id="8f6bc-139">Setting this option</span></span>  
 <span data-ttu-id="8f6bc-140">若要在 Visual Studio 中设置 -subsystemversion 编译器选项，必须打开 .csproj 文件，并在 MSBuild XML 中为 `SubsystemVersion` 属性指定一个值。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="8f6bc-141">不能在 Visual Studio IDE 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="8f6bc-142">有关详细信息，请参阅本主题前面的“默认值”或[常用的 MSBuild 项目属性](/visualstudio/msbuild/common-msbuild-project-properties)。</span><span class="sxs-lookup"><span data-stu-id="8f6bc-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6bc-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f6bc-143">See Also</span></span>  
 [<span data-ttu-id="8f6bc-144">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="8f6bc-144">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
