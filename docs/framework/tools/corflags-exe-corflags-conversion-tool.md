---
title: CorFlags.exe（CorFlags 转换工具）
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4228da6efe22091c86de95d846c14f504d51457f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851286"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="a668f-102">CorFlags.exe（CorFlags 转换工具）</span><span class="sxs-lookup"><span data-stu-id="a668f-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="a668f-103">利用 CorFlags 转换工具，你配置可移植可执行映像标头的 CorFlags 部分。</span><span class="sxs-lookup"><span data-stu-id="a668f-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="a668f-104">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="a668f-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="a668f-105">若要运行此工具，请使用 Visual Studio 开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="a668f-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="a668f-106">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="a668f-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="a668f-107">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a668f-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a668f-108">语法</span><span class="sxs-lookup"><span data-stu-id="a668f-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="a668f-109">参数</span><span class="sxs-lookup"><span data-stu-id="a668f-109">Parameters</span></span>  
  
|<span data-ttu-id="a668f-110">必选参数</span><span class="sxs-lookup"><span data-stu-id="a668f-110">Required parameter</span></span>|<span data-ttu-id="a668f-111">说明</span><span class="sxs-lookup"><span data-stu-id="a668f-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="a668f-112">要为其配置 CorFlags 的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="a668f-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="a668f-113">选项</span><span class="sxs-lookup"><span data-stu-id="a668f-113">Option</span></span>|<span data-ttu-id="a668f-114">说明</span><span class="sxs-lookup"><span data-stu-id="a668f-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a668f-115">/32BIT[REQ]+ </span><span class="sxs-lookup"><span data-stu-id="a668f-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="a668f-116">设置 32BITREQUIRED 标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="a668f-117">/32BIT[REQ]- </span><span class="sxs-lookup"><span data-stu-id="a668f-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="a668f-118">清除 32BITREQUIRED 标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="a668f-119">/32BITPREF+ </span><span class="sxs-lookup"><span data-stu-id="a668f-119">**/32BITPREF+**</span></span>|<span data-ttu-id="a668f-120">设置 32BITPREFERRED 标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="a668f-121">该应用程序甚至可以作为 32 位进程在 64 位平台上运行。</span><span class="sxs-lookup"><span data-stu-id="a668f-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="a668f-122">仅在 EXE 文件中设置此标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="a668f-123">如果在 DLL 上设置此标志，则 DLL 将无法在 64 位进程中加载，并引发 <xref:System.BadImageFormatException> 异常。</span><span class="sxs-lookup"><span data-stu-id="a668f-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="a668f-124">具有此标志的 EXE 文件可以加载到 64 位进程中。</span><span class="sxs-lookup"><span data-stu-id="a668f-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="a668f-125">.NET Framework 4.5 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="a668f-125">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="a668f-126">/32BITPREF- </span><span class="sxs-lookup"><span data-stu-id="a668f-126">**/32BITPREF-**</span></span>|<span data-ttu-id="a668f-127">清除 32BITPREFERRED 标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="a668f-128">.NET Framework 4.5 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="a668f-128">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="a668f-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="a668f-129">**/?**</span></span>|<span data-ttu-id="a668f-130">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="a668f-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a668f-131">/Force </span><span class="sxs-lookup"><span data-stu-id="a668f-131">**/Force**</span></span>|<span data-ttu-id="a668f-132">强制执行更新，即使程序集具有强名称也是如此。</span><span class="sxs-lookup"><span data-stu-id="a668f-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="a668f-133">**重要提示：** 如果更新具有强名称的程序集，则必须在执行其代码之前再次对其签名。</span><span class="sxs-lookup"><span data-stu-id="a668f-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="a668f-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="a668f-134">**/help**</span></span>|<span data-ttu-id="a668f-135">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="a668f-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a668f-136">/ILONLY+ </span><span class="sxs-lookup"><span data-stu-id="a668f-136">**/ILONLY+**</span></span>|<span data-ttu-id="a668f-137">设置 ILONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="a668f-138">/ILONLY- </span><span class="sxs-lookup"><span data-stu-id="a668f-138">**/ILONLY-**</span></span>|<span data-ttu-id="a668f-139">清除 ILONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="a668f-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="a668f-140">**/nologo**</span></span>|<span data-ttu-id="a668f-141">取消显示 Microsoft 启动版权标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="a668f-142">/RevertCLRHeader </span><span class="sxs-lookup"><span data-stu-id="a668f-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="a668f-143">将 CLR 标头版本还原到 2.0。</span><span class="sxs-lookup"><span data-stu-id="a668f-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="a668f-144">/UpgradeCLRHeader </span><span class="sxs-lookup"><span data-stu-id="a668f-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="a668f-145">将 CLR 标头版本升级到 2.5。</span><span class="sxs-lookup"><span data-stu-id="a668f-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="a668f-146">**注意：** 程序集必须具有 2.5 版或更高版本的 CLR 标头才能在本机运行。</span><span class="sxs-lookup"><span data-stu-id="a668f-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a668f-147">备注</span><span class="sxs-lookup"><span data-stu-id="a668f-147">Remarks</span></span>  
 <span data-ttu-id="a668f-148">如果未指定任何选项，则 CorFlags 转换工具将显示指定程序集的标志。</span><span class="sxs-lookup"><span data-stu-id="a668f-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a668f-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="a668f-149">See also</span></span>

- [<span data-ttu-id="a668f-150">工具</span><span class="sxs-lookup"><span data-stu-id="a668f-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="a668f-151">64 位应用程序</span><span class="sxs-lookup"><span data-stu-id="a668f-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)
- [<span data-ttu-id="a668f-152">命令提示</span><span class="sxs-lookup"><span data-stu-id="a668f-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
