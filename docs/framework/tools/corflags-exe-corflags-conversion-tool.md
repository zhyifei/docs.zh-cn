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
ms.openlocfilehash: d4a5b6d490387f2da441ad95bdf369f700cf2e9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400024"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="29118-102">CorFlags.exe（CorFlags 转换工具）</span><span class="sxs-lookup"><span data-stu-id="29118-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="29118-103">利用 CorFlags 转换工具，你配置可移植可执行映像标头的 CorFlags 部分。</span><span class="sxs-lookup"><span data-stu-id="29118-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="29118-104">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="29118-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="29118-105">若要运行此工具，请使用开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="29118-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="29118-106">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="29118-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="29118-107">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="29118-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29118-108">语法</span><span class="sxs-lookup"><span data-stu-id="29118-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29118-109">参数</span><span class="sxs-lookup"><span data-stu-id="29118-109">Parameters</span></span>  
  
|<span data-ttu-id="29118-110">必选参数</span><span class="sxs-lookup"><span data-stu-id="29118-110">Required parameter</span></span>|<span data-ttu-id="29118-111">描述</span><span class="sxs-lookup"><span data-stu-id="29118-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="29118-112">要为其配置 CorFlags 的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="29118-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="29118-113">选项</span><span class="sxs-lookup"><span data-stu-id="29118-113">Option</span></span>|<span data-ttu-id="29118-114">描述</span><span class="sxs-lookup"><span data-stu-id="29118-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="29118-115">/32BIT[REQ]+</span><span class="sxs-lookup"><span data-stu-id="29118-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="29118-116">设置 32BITREQUIRED 标志。</span><span class="sxs-lookup"><span data-stu-id="29118-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="29118-117">/32BIT[REQ]-</span><span class="sxs-lookup"><span data-stu-id="29118-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="29118-118">清除 32BITREQUIRED 标志。</span><span class="sxs-lookup"><span data-stu-id="29118-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="29118-119">/32BITPREF+</span><span class="sxs-lookup"><span data-stu-id="29118-119">**/32BITPREF+**</span></span>|<span data-ttu-id="29118-120">设置 32BITPREFERRED 标志。</span><span class="sxs-lookup"><span data-stu-id="29118-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="29118-121">该应用程序甚至可以作为 32 位进程在 64 位平台上运行。</span><span class="sxs-lookup"><span data-stu-id="29118-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="29118-122">仅在 EXE 文件中设置此标志。</span><span class="sxs-lookup"><span data-stu-id="29118-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="29118-123">如果在 DLL 上设置此标志，则 DLL 将无法在 64 位进程中加载，并引发 <xref:System.BadImageFormatException> 异常。</span><span class="sxs-lookup"><span data-stu-id="29118-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="29118-124">具有此标志的 EXE 文件可以加载到 64 位进程中。</span><span class="sxs-lookup"><span data-stu-id="29118-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="29118-125">在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中是新增选项。</span><span class="sxs-lookup"><span data-stu-id="29118-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="29118-126">/32BITPREF-</span><span class="sxs-lookup"><span data-stu-id="29118-126">**/32BITPREF-**</span></span>|<span data-ttu-id="29118-127">清除 32BITPREFERRED 标志。</span><span class="sxs-lookup"><span data-stu-id="29118-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="29118-128">在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中是新增选项。</span><span class="sxs-lookup"><span data-stu-id="29118-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="29118-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="29118-129">**/?**</span></span>|<span data-ttu-id="29118-130">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="29118-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="29118-131">/Force</span><span class="sxs-lookup"><span data-stu-id="29118-131">**/Force**</span></span>|<span data-ttu-id="29118-132">强制执行更新，即使程序集具有强名称也是如此。</span><span class="sxs-lookup"><span data-stu-id="29118-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="29118-133">重要提示：如果更新使用强名称的程序集，则必须在执行其代码之前再次对其签名。</span><span class="sxs-lookup"><span data-stu-id="29118-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="29118-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="29118-134">**/help**</span></span>|<span data-ttu-id="29118-135">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="29118-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="29118-136">/ILONLY+</span><span class="sxs-lookup"><span data-stu-id="29118-136">**/ILONLY+**</span></span>|<span data-ttu-id="29118-137">设置 ILONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="29118-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="29118-138">/ILONLY-</span><span class="sxs-lookup"><span data-stu-id="29118-138">**/ILONLY-**</span></span>|<span data-ttu-id="29118-139">清除 ILONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="29118-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="29118-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="29118-140">**/nologo**</span></span>|<span data-ttu-id="29118-141">取消显示 Microsoft 启动版权标志。</span><span class="sxs-lookup"><span data-stu-id="29118-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="29118-142">/RevertCLRHeader</span><span class="sxs-lookup"><span data-stu-id="29118-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="29118-143">将 CLR 标头版本还原到 2.0。</span><span class="sxs-lookup"><span data-stu-id="29118-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="29118-144">/UpgradeCLRHeader</span><span class="sxs-lookup"><span data-stu-id="29118-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="29118-145">将 CLR 标头版本升级到 2.5。</span><span class="sxs-lookup"><span data-stu-id="29118-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="29118-146">注意：程序集必须具有 2.5 版或更高版本的 CLR 标头才能在本机运行。</span><span class="sxs-lookup"><span data-stu-id="29118-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29118-147">备注</span><span class="sxs-lookup"><span data-stu-id="29118-147">Remarks</span></span>  
 <span data-ttu-id="29118-148">如果未指定任何选项，则 CorFlags 转换工具将显示指定程序集的标志。</span><span class="sxs-lookup"><span data-stu-id="29118-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29118-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="29118-149">See Also</span></span>  
 [<span data-ttu-id="29118-150">工具</span><span class="sxs-lookup"><span data-stu-id="29118-150">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="29118-151">64 位应用程序</span><span class="sxs-lookup"><span data-stu-id="29118-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)  
 [<span data-ttu-id="29118-152">命令提示</span><span class="sxs-lookup"><span data-stu-id="29118-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
