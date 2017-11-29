---
title: "ServiceModel 注册工具 (ServiceModelReg.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7032fd6005d5eccf27e0ca34cd89c050260d6e4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="87003-102">ServiceModel 注册工具 (ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="87003-102">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="87003-103">利用此命令行工具可以管理 WCF 和 WF 组件在单一计算机上的注册。</span><span class="sxs-lookup"><span data-stu-id="87003-103">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="87003-104">在正常情况下，不应使用此工具，因为 WCF 和WF 组件在安装时配置。</span><span class="sxs-lookup"><span data-stu-id="87003-104">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="87003-105">但如果您遇到服务激活方面的问题，可以尝试使用此工具注册组件。</span><span class="sxs-lookup"><span data-stu-id="87003-105">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87003-106">语法</span><span class="sxs-lookup"><span data-stu-id="87003-106">Syntax</span></span>  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="87003-107">备注</span><span class="sxs-lookup"><span data-stu-id="87003-107">Remarks</span></span>  
 <span data-ttu-id="87003-108">可在以下位置中找到此工具：</span><span class="sxs-lookup"><span data-stu-id="87003-108">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="87003-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="87003-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87003-110">在上运行 ServiceModel 注册工具时[!INCLUDE[wv](../../../includes/wv-md.md)]、 **Windows 功能**对话框可能不会反映出**Windows Communication Foundation HTTP 激活**选项下**Microsoft.NET Framework 3.0**已开启。</span><span class="sxs-lookup"><span data-stu-id="87003-110">When the ServiceModel Registration Tool is run on [!INCLUDE[wv](../../../includes/wv-md.md)], the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="87003-111">**Windows 功能**对话框可以通过单击访问**启动**，然后单击**运行**，然后键入**OptionalFeatures**。</span><span class="sxs-lookup"><span data-stu-id="87003-111">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="87003-112">下表介绍可用于 ServiceModelReg.exe 的选项。</span><span class="sxs-lookup"><span data-stu-id="87003-112">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="87003-113">选项</span><span class="sxs-lookup"><span data-stu-id="87003-113">Option</span></span>|<span data-ttu-id="87003-114">描述</span><span class="sxs-lookup"><span data-stu-id="87003-114">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="87003-115">安装所有 WCF 和 WF 组件。</span><span class="sxs-lookup"><span data-stu-id="87003-115">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="87003-116">卸载所有 WCF 和 WF 组件。</span><span class="sxs-lookup"><span data-stu-id="87003-116">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="87003-117">修复所有 WCF 和 WF 组件。</span><span class="sxs-lookup"><span data-stu-id="87003-117">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="87003-118">安装使用 –c 指定的 WCF 和 WF 组件。</span><span class="sxs-lookup"><span data-stu-id="87003-118">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="87003-119">卸载使用 –c 指定的 WCF 和 WF 组件。</span><span class="sxs-lookup"><span data-stu-id="87003-119">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="87003-120">安装或卸载组件：</span><span class="sxs-lookup"><span data-stu-id="87003-120">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="87003-121">-httpnamespace – HTTP Namespace 保留</span><span class="sxs-lookup"><span data-stu-id="87003-121">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="87003-122">-tcpportsharing – TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="87003-122">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="87003-123">-tcpactivation-TCP 激活服务 （.NET 4 客户端配置文件不支持）</span><span class="sxs-lookup"><span data-stu-id="87003-123">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="87003-124">-namedpipeactivation-命名管道激活服务 （.NET 4 客户端配置文件不支持</span><span class="sxs-lookup"><span data-stu-id="87003-124">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="87003-125">-msmqactivation-MSMQ 激活服务 （.NET 4 客户端配置文件不支持</span><span class="sxs-lookup"><span data-stu-id="87003-125">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="87003-126">-etw – ETW 事件跟踪清单 (Windows Vista 或更高版本)</span><span class="sxs-lookup"><span data-stu-id="87003-126">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="87003-127">安静模式（仅显示错误日志记录）</span><span class="sxs-lookup"><span data-stu-id="87003-127">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="87003-128">详细模式。</span><span class="sxs-lookup"><span data-stu-id="87003-128">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="87003-129">取消版权和标题消息。</span><span class="sxs-lookup"><span data-stu-id="87003-129">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="87003-130">显示帮助文本</span><span class="sxs-lookup"><span data-stu-id="87003-130">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="87003-131">修复 FileLoadException 错误</span><span class="sxs-lookup"><span data-stu-id="87003-131">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="87003-132">如果计算机上安装了以前版本的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]，当您运行 ServiceModelReg 工具注册新安装时，可能会收到 `FileLoadFoundException` 错误。</span><span class="sxs-lookup"><span data-stu-id="87003-132">If you installed previous versions of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="87003-133">即使从以前的安装中手动移除了文件（但保留 machine.config 设置不变），也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="87003-133">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="87003-134">错误消息类似于以下内容。</span><span class="sxs-lookup"><span data-stu-id="87003-134">The error message is similar to the following.</span></span>  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="87003-135">从错误消息中，您应注意到早期的客户技术预览 (CTP) 版本安装了 System.ServiceModel 2.0.0.0 版程序集。</span><span class="sxs-lookup"><span data-stu-id="87003-135">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="87003-136">而已发布 System.ServiceModel 程序集的当前版本为 3.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="87003-136">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="87003-137">因此，当您想要在安装过 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 早期 CTP 版本（但未完全卸载）的计算机上安装 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 的正式版本时，会遇到此问题。</span><span class="sxs-lookup"><span data-stu-id="87003-137">Therefore, this issue is encountered when you want to install the official [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] release on a machine where an early CTP release of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="87003-138">ServiceModelReg.exe 无法清除以前的版本项，也无法注册新的版本项。</span><span class="sxs-lookup"><span data-stu-id="87003-138">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="87003-139">唯一的解决方法是手动编辑 machine.config。可在以下位置找到此文件。</span><span class="sxs-lookup"><span data-stu-id="87003-139">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="87003-140">如果在 64 位计算机上运行 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]，您还应编辑位于此位置的相同文件。</span><span class="sxs-lookup"><span data-stu-id="87003-140">If you are running [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="87003-141">在引用此文件中找到的任何 XML 节点"System.ServiceModel，Version = 2.0.0.0"，删除这些节点及任何子节点。</span><span class="sxs-lookup"><span data-stu-id="87003-141">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="87003-142">保存文件并重新运行 ServiceModelReg.exe 可解决此问题。</span><span class="sxs-lookup"><span data-stu-id="87003-142">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="87003-143">示例</span><span class="sxs-lookup"><span data-stu-id="87003-143">Examples</span></span>  
 <span data-ttu-id="87003-144">下面的示例演示如何使用 ServiceModelReg.exe 工具的最常用选项。</span><span class="sxs-lookup"><span data-stu-id="87003-144">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
```  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
