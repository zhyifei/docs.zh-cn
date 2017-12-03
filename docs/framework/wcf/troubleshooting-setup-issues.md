---
title: "安装问题疑难解答"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 13f6bd17e1295ea72f25710d7ae5e2803c94aad1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="troubleshooting-setup-issues"></a><span data-ttu-id="b1040-102">安装问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="b1040-102">Troubleshooting Setup Issues</span></span>
<span data-ttu-id="b1040-103">本主题说明如何排除 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 安装问题。</span><span class="sxs-lookup"><span data-stu-id="b1040-103">This topic describes how to troubleshoot [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] set up issues.</span></span>  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a><span data-ttu-id="b1040-104">有些 Windows Communication Foundation 注册表项无法通过在 .NET Framework 3.0 上执行 MSI 修复操作来修复</span><span class="sxs-lookup"><span data-stu-id="b1040-104">Some Windows Communication Foundation Registry Keys are not Repaired by Performing an MSI Repair Operation on the .NET Framework 3.0</span></span>  
 <span data-ttu-id="b1040-105">如果您删除下面的任何注册表项：</span><span class="sxs-lookup"><span data-stu-id="b1040-105">If you delete any of the following registry keys:</span></span>  
  
-   <span data-ttu-id="b1040-106">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="b1040-106">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span></span>  
  
-   <span data-ttu-id="b1040-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="b1040-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span></span>  
  
-   <span data-ttu-id="b1040-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="b1040-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span></span>  
  
-   <span data-ttu-id="b1040-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="b1040-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span></span>  
  
-   <span data-ttu-id="b1040-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="b1040-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span></span>  
  
 <span data-ttu-id="b1040-111">不通过使用从启动的.NET Framework 3.0 安装程序运行修复重新创建这些项**添加/删除程序**小程序中的**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="b1040-111">The keys are not re-created if you run repair by using the .NET Framework 3.0 installer launched from the **Add/Remove Programs** applet in **Control Panel**.</span></span> <span data-ttu-id="b1040-112">若要重新正确创建这些项，用户必须卸载并重新安装 .NET Framework 3.0。</span><span class="sxs-lookup"><span data-stu-id="b1040-112">To recreate these keys correctly, the user must uninstall and reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a><span data-ttu-id="b1040-113">在安装 .NET Framework 3.0 软件包过程中 WMI Service Corruption 阻止 Windows Communication Foundation WMI 提供程序的安装</span><span class="sxs-lookup"><span data-stu-id="b1040-113">WMI Service Corruption Blocks Installation of the Windows Communication Foundation WMI provider during installation of .NET Framework 3.0 package</span></span>  
 <span data-ttu-id="b1040-114">WMI Service Corruption 可能阻止 Windows Communication Foundation WMI 提供程序的安装。</span><span class="sxs-lookup"><span data-stu-id="b1040-114">WMI Service Corruption may block the installation of the Windows Communication Foundation WMI provider.</span></span> <span data-ttu-id="b1040-115">在安装过程中，Windows Communication Foundation 安装程序无法使用 mofcomp.exe 组件注册 WCF .mof 文件。</span><span class="sxs-lookup"><span data-stu-id="b1040-115">During installation the Windows Communication Foundation installer is unable to register the WCF .mof file using the mofcomp.exe component.</span></span> <span data-ttu-id="b1040-116">下面列出了几个症状：</span><span class="sxs-lookup"><span data-stu-id="b1040-116">The following is a list of symptoms:</span></span>  
  
1.  <span data-ttu-id="b1040-117">.NET Framework 3.0 安装成功完成，但未注册 WCF WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="b1040-117">.NET Framework 3.0 installation completes successfully, but the WCF WMI provider is not registered.</span></span>  
  
2.  <span data-ttu-id="b1040-118">应用程序事件日志中显示一个错误事件，该事件指示在注册 WCF 的 WMI 提供程序或运行 mofcomp.exe 时出现问题。</span><span class="sxs-lookup"><span data-stu-id="b1040-118">An error event appears in the application event log that references problems registering the WMI provider for WCF, or running mofcomp.exe.</span></span>  
  
3.  <span data-ttu-id="b1040-119">用户的 %temp% 目录中名为 dd_wcf_retCA* 的安装日志文件包含对注册 WCF WMI 提供程序失败的引用。</span><span class="sxs-lookup"><span data-stu-id="b1040-119">The setup log file named dd_wcf_retCA* in the user's %temp% directory contains references to failure to register the WCF WMI provider.</span></span>  
  
4.  <span data-ttu-id="b1040-120">事件日志或安装跟踪日志文件中可能会列出以下异常之一：</span><span class="sxs-lookup"><span data-stu-id="b1040-120">An exception such as one the following may be listed in the event log or setup trace log file:</span></span>  
  
     <span data-ttu-id="b1040-121">ServiceModelReg [11:09:59:046]: System.ApplicationException: 使用“E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof”执行 E:\WINDOWS\system32\wbem\mofcomp.exe 发生意外结果 3</span><span class="sxs-lookup"><span data-stu-id="b1040-121">ServiceModelReg [11:09:59:046]: System.ApplicationException: Unexpected result 3 executing E:\WINDOWS\system32\wbem\mofcomp.exe with "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"</span></span>  
  
     <span data-ttu-id="b1040-122">或：</span><span class="sxs-lookup"><span data-stu-id="b1040-122">or:</span></span>  
  
     <span data-ttu-id="b1040-123">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: “System.Management.ManagementPath”的类型初始值设定项引发异常。</span><span class="sxs-lookup"><span data-stu-id="b1040-123">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: The type initializer for 'System.Management.ManagementPath' threw an exception.</span></span> <span data-ttu-id="b1040-124">---> System.Runtime.InteropServices.COMException (0x80040154): 检索 COM 类工厂中 CLSID 为 {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} 的组件时失败，原因是出现以下错误: 80040154。</span><span class="sxs-lookup"><span data-stu-id="b1040-124">---> System.Runtime.InteropServices.COMException (0x80040154): Retrieving the COM class factory for component with CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} failed due to the following error: 80040154.</span></span>  
  
     <span data-ttu-id="b1040-125">或：</span><span class="sxs-lookup"><span data-stu-id="b1040-125">or:</span></span>  
  
     <span data-ttu-id="b1040-126">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: 无法加载文件或程序集“C:\WINDOWS\system32\wbem\mofcomp.exe”或其一个依赖项。</span><span class="sxs-lookup"><span data-stu-id="b1040-126">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Could not load file or assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' or one of its dependencies.</span></span> <span data-ttu-id="b1040-127">系统找不到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="b1040-127">The system cannot find the file specified.</span></span>  
  
     <span data-ttu-id="b1040-128">文件名:“C:\WINDOWS\system32\wbem\mofcomp.exe”</span><span class="sxs-lookup"><span data-stu-id="b1040-128">File name: 'C:\WINDOWS\system32\wbem\mofcomp.exe</span></span>  
  
 <span data-ttu-id="b1040-129">若要解决前面说明的问题，必须按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="b1040-129">The following steps must be followed to resolve the problem described previously.</span></span>  
  
1.  <span data-ttu-id="b1040-130">运行[WMI 诊断实用程序，版本 2.0](http://go.microsoft.com/fwlink/?LinkId=94685)要修复的 WMI 服务。</span><span class="sxs-lookup"><span data-stu-id="b1040-130">Run [the WMI Diagnosis Utility, version 2.0](http://go.microsoft.com/fwlink/?LinkId=94685) to repair the WMI service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="b1040-131">使用此工具，请参阅[WMI 诊断实用程序](http://go.microsoft.com/fwlink/?LinkId=94686)主题。</span><span class="sxs-lookup"><span data-stu-id="b1040-131"> using this tool, see the [WMI Diagnosis Utility](http://go.microsoft.com/fwlink/?LinkId=94686) topic.</span></span>  
  
 <span data-ttu-id="b1040-132">使用修复.NET Framework 3.0 安装**添加/删除程序**小程序位于**控制面板**，或卸载/重新安装.NET Framework 3.0。</span><span class="sxs-lookup"><span data-stu-id="b1040-132">Repair the .NET Framework 3.0 installation by using the **Add/Remove Programs** applet located in **Control Panel**, or uninstall/reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a><span data-ttu-id="b1040-133">在安装 .NET Framework 3.5 后修复 .NET Framework 3.0 会移除 .NET Framework 3.5 在 machine.config 中引入的配置元素</span><span class="sxs-lookup"><span data-stu-id="b1040-133">Repairing .NET Framework 3.0 after .NET Framework 3.5 Installation Removes Configuration Elements Introduced by .NET Framework 3.5 in machine.config</span></span>  
 <span data-ttu-id="b1040-134">如果在安装 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 后修复 .NET Framework 3.0，则会从 machine.config 中移除由 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 引入的配置元素。</span><span class="sxs-lookup"><span data-stu-id="b1040-134">If you do a repair of .NET Framework 3.0 after you installed [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], configuration elements introduced by [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] in machine.config are removed.</span></span> <span data-ttu-id="b1040-135">但是，web.config 保持不变。</span><span class="sxs-lookup"><span data-stu-id="b1040-135">However, the web.config remains intact.</span></span> <span data-ttu-id="b1040-136">解决方法是修复[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]此通过 ARP 或使用之后[工作流服务注册工具 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)与`/c`切换。</span><span class="sxs-lookup"><span data-stu-id="b1040-136">The workaround is to repair [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] after this via ARP, or use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch.</span></span>  
  
 <span data-ttu-id="b1040-137">[工作流服务注册工具 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)可以位于 %windir%\Microsoft.NET\framework\v3.5\ 或 %windir%\Microsoft.NET\framework64\v3.5\\</span><span class="sxs-lookup"><span data-stu-id="b1040-137">[WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5\\</span></span>  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a><span data-ttu-id="b1040-138">安装 .NET Framework 3.5 之后，为 WCF/WF Webhost 正确配置 IIS</span><span class="sxs-lookup"><span data-stu-id="b1040-138">Configure IIS Properly for WCF/WF Webhost after Installing .NET Framework 3.5</span></span>  
 <span data-ttu-id="b1040-139">如果 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 安装无法配置与 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 相关的其他 IIS 配置设置，将会在安装日志中记录错误，然后继续操作。</span><span class="sxs-lookup"><span data-stu-id="b1040-139">When [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installation fails to configure additional [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-related IIS configuration settings, it logs an error in the installation log and continues.</span></span> <span data-ttu-id="b1040-140">对运行 WorkflowServices 应用程序的任何尝试都将失败，因为缺少必需的配置设置。</span><span class="sxs-lookup"><span data-stu-id="b1040-140">Any attempt to run WorkflowServices applications will fail, since the required configuration settings are missing.</span></span> <span data-ttu-id="b1040-141">例如，加载 xoml 或规则服务会失败。</span><span class="sxs-lookup"><span data-stu-id="b1040-141">For example, loading xoml or rules service can fail.</span></span>  
  
 <span data-ttu-id="b1040-142">解决此问题，使用[工作流服务注册工具 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)与`/c`交换机以正确的计算机上配置 IIS 脚本映射。</span><span class="sxs-lookup"><span data-stu-id="b1040-142">To workaround this problem, use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch to properly configure IIS script maps on the machine.</span></span> <span data-ttu-id="b1040-143">[工作流服务注册工具 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)可以位于 %windir%\Microsoft.NET\framework\v3.5\ 或 %windir%\Microsoft.NET\framework64\v3.5\\</span><span class="sxs-lookup"><span data-stu-id="b1040-143">[WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5\\</span></span>  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a><span data-ttu-id="b1040-144">无法从程序集“System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089”加载类型“System.ServiceModel.Activation.HttpModule”</span><span class="sxs-lookup"><span data-stu-id="b1040-144">Could not load type ‘System.ServiceModel.Activation.HttpModule’ from assembly ‘System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089’</span></span>  
 <span data-ttu-id="b1040-145">如果安装了 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]，随后启用了 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] HTTP 激活，则会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="b1040-145">This error occurs if [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] is installed and then [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] HTTP Activation is enabled.</span></span> <span data-ttu-id="b1040-146">若要解决该问题，请在 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 命令提示符下运行下面的命令行：</span><span class="sxs-lookup"><span data-stu-id="b1040-146">To resolve the issue run the following command-line from inside the [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] Command Prompt:</span></span>  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1040-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1040-147">See Also</span></span>  
 [<span data-ttu-id="b1040-148">设置说明</span><span class="sxs-lookup"><span data-stu-id="b1040-148">Set-Up Instructions</span></span>](../../../docs/framework/wcf/samples/set-up-instructions.md)
