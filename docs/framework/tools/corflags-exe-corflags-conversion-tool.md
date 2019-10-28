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
ms.openlocfilehash: 63e70ae8cd110786ad7d2069088dbfdfde736a28
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846748"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="9a76d-102">CorFlags.exe（CorFlags 转换工具）</span><span class="sxs-lookup"><span data-stu-id="9a76d-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="9a76d-103">利用 CorFlags 转换工具，你配置可移植可执行映像标头的 CorFlags 部分。</span><span class="sxs-lookup"><span data-stu-id="9a76d-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="9a76d-104">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="9a76d-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="9a76d-105">若要运行此工具，请使用 Visual Studio 开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="9a76d-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="9a76d-106">有关详细信息，请参阅[命令提示](developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="9a76d-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="9a76d-107">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="9a76d-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a76d-108">语法</span><span class="sxs-lookup"><span data-stu-id="9a76d-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a76d-109">参数</span><span class="sxs-lookup"><span data-stu-id="9a76d-109">Parameters</span></span>  
  
|<span data-ttu-id="9a76d-110">必选参数</span><span class="sxs-lookup"><span data-stu-id="9a76d-110">Required parameter</span></span>|<span data-ttu-id="9a76d-111">说明</span><span class="sxs-lookup"><span data-stu-id="9a76d-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="9a76d-112">要为其配置 CorFlags 的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="9a76d-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="9a76d-113">选项</span><span class="sxs-lookup"><span data-stu-id="9a76d-113">Option</span></span>|<span data-ttu-id="9a76d-114">说明</span><span class="sxs-lookup"><span data-stu-id="9a76d-114">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="9a76d-115">设置 32BITREQUIRED 标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-115">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="9a76d-116">清除 32BITREQUIRED 标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-116">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="9a76d-117">设置 32BITPREFERRED 标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-117">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="9a76d-118">该应用程序甚至可以作为 32 位进程在 64 位平台上运行。</span><span class="sxs-lookup"><span data-stu-id="9a76d-118">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="9a76d-119">仅在 EXE 文件中设置此标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-119">Set this flag only on EXE files.</span></span> <span data-ttu-id="9a76d-120">如果在 DLL 上设置此标志，则 DLL 将无法在 64 位进程中加载，并引发 <xref:System.BadImageFormatException> 异常。</span><span class="sxs-lookup"><span data-stu-id="9a76d-120">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="9a76d-121">具有此标志的 EXE 文件可以加载到 64 位进程中。</span><span class="sxs-lookup"><span data-stu-id="9a76d-121">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="9a76d-122">.NET Framework 4.5 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="9a76d-122">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="9a76d-123">清除 32BITPREFERRED 标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-123">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="9a76d-124">.NET Framework 4.5 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="9a76d-124">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="9a76d-125">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="9a76d-125">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="9a76d-126">强制执行更新，即使程序集具有强名称也是如此。</span><span class="sxs-lookup"><span data-stu-id="9a76d-126">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="9a76d-127">**重要提示：** 如果更新具有强名称的程序集，则必须在执行其代码之前再次对其签名。</span><span class="sxs-lookup"><span data-stu-id="9a76d-127">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="9a76d-128">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="9a76d-128">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="9a76d-129">设置 ILONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-129">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="9a76d-130">清除 ILONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-130">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="9a76d-131">取消显示 Microsoft 启动版权标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-131">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="9a76d-132">将 CLR 标头版本还原到 2.0。</span><span class="sxs-lookup"><span data-stu-id="9a76d-132">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="9a76d-133">将 CLR 标头版本升级到 2.5。</span><span class="sxs-lookup"><span data-stu-id="9a76d-133">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="9a76d-134">**注意：** 程序集必须具有 2.5 版或更高版本的 CLR 标头才能在本机运行。</span><span class="sxs-lookup"><span data-stu-id="9a76d-134">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a76d-135">备注</span><span class="sxs-lookup"><span data-stu-id="9a76d-135">Remarks</span></span>  
 <span data-ttu-id="9a76d-136">如果未指定任何选项，则 CorFlags 转换工具将显示指定程序集的标志。</span><span class="sxs-lookup"><span data-stu-id="9a76d-136">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a76d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a76d-137">See also</span></span>

- [<span data-ttu-id="9a76d-138">工具</span><span class="sxs-lookup"><span data-stu-id="9a76d-138">Tools</span></span>](index.md)
- [<span data-ttu-id="9a76d-139">64 位应用程序</span><span class="sxs-lookup"><span data-stu-id="9a76d-139">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="9a76d-140">命令提示</span><span class="sxs-lookup"><span data-stu-id="9a76d-140">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
