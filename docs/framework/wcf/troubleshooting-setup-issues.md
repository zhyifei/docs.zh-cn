---
title: 安装问题疑难解答
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 2cd9ced4f0780b1a6f63e4a5833e20ac91870121
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121585"
---
# <a name="troubleshoot-setup-issues"></a>排除设置问题

本文介绍如何解决 Windows 通信基础 （WCF） 设置问题。  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>有些 Windows Communication Foundation 注册表项无法通过在 .NET Framework 3.0 上执行 MSI 修复操作来修复  
 如果您删除下面的任何注册表项：  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 如果使用从**控制面板**中的 **"添加/删除程序**"小程序启动的 .NET 框架 3.0 安装程序运行修复，则不会重新创建密钥。 若要重新正确创建这些项，用户必须卸载并重新安装 .NET Framework 3.0。  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>在安装 .NET Framework 3.0 软件包过程中 WMI Service Corruption 阻止 Windows Communication Foundation WMI 提供程序的安装  
 WMI Service Corruption 可能阻止 Windows Communication Foundation WMI 提供程序的安装。 在安装过程中，Windows Communication Foundation 安装程序无法使用 mofcomp.exe 组件注册 WCF .mof 文件。 下面列出了几个症状：  
  
1. .NET Framework 3.0 安装成功完成，但未注册 WCF WMI 提供程序。  
  
2. 应用程序事件日志中显示一个错误事件，该事件指示在注册 WCF 的 WMI 提供程序或运行 mofcomp.exe 时出现问题。  
  
3. 用户的 %temp% 目录中名为 dd_wcf_retCA* 的安装日志文件包含对注册 WCF WMI 提供程序失败的引用。  
  
4. 事件日志或安装跟踪日志文件中可能会列出以下异常之一：  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: 使用“E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof”执行 E:\WINDOWS\system32\wbem\mofcomp.exe 发生意外结果 3  
  
     或：  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: “System.Management.ManagementPath”的类型初始值设定项引发异常。 --->系统.Runtime.InteropServices.COMexception （0x80040154）：检索 CLSID [CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA] 的组件的 COM 类工厂，由于以下错误：80040154。  
  
     或：  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: 无法加载文件或程序集“C:\WINDOWS\system32\wbem\mofcomp.exe”或其一个依赖项。 系统找不到指定的文件。  
  
     文件名:“C:\WINDOWS\system32\wbem\mofcomp.exe”  
  
 若要解决前面说明的问题，必须按照以下步骤操作。  
  
1. 运行[WMI 诊断实用程序](https://www.microsoft.com/download/details.aspx?id=7684)以修复 WMI 服务。 有关使用此工具的详细信息，请参阅[WMI 诊断实用程序](https://docs.microsoft.com/previous-versions/tn-archive/ff404265(v%3dmsdn.10))。  
  
 使用**位于控制面板**中的 **"添加/删除程序**"小程序，或卸载/重新安装 .NET 框架 3.0 来修复 .NET 框架 3.0 安装。  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>在安装 .NET Framework 3.5 后修复 .NET Framework 3.0 会移除 .NET Framework 3.5 在 machine.config 中引入的配置元素  
 如果在安装 .NET 框架 3.5 后对 .NET 框架 3.0 进行了修复，则将删除机器中的 .NET Framework 3.5 引入的配置元素。 但是，web.config 保持不变。 解决方法是通过 ARP 在此之后修复 .NET 框架 3.5，或使用随`/c`交换机执行[工作流服务注册工具 （WFServicesReg.exe）。](workflow-service-registration-tool-wfservicesreg-exe.md)  
  
 [工作流服务注册工具 （WFServicesReg.exe）](workflow-service-registration-tool-wfservicesreg-exe.md)可在 %windir%\Microsoft.NET_framework_v3.5] 或 %windir%_Microsoft.NET_framework64_v3.5] 找到。  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>安装 .NET Framework 3.5 之后，为 WCF/WF Webhost 正确配置 IIS  
 当 .NET Framework 3.5 安装无法配置其他与 WCF 相关的 IIS 配置设置时，它将记录安装日志中的错误并继续。 对运行 WorkflowServices 应用程序的任何尝试都将失败，因为缺少必需的配置设置。 例如，加载 xoml 或规则服务会失败。  
  
 要解决此问题，请使用带有`/c`交换机的[工作流服务注册工具 （WFServicesReg.exe）](workflow-service-registration-tool-wfservicesreg-exe.md)在计算机上正确配置 IIS 脚本映射。 [工作流服务注册工具 （WFServicesReg.exe）](workflow-service-registration-tool-wfservicesreg-exe.md)可在 %windir%\Microsoft.NET_framework_v3.5] 或 %windir%_Microsoft.NET_framework64_v3.5] 找到。  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>无法加载程序集"System.ServiceModel，激活.httpModule"从程序集"System.ServiceModel，版本 3.0.0.0，区域性_中性，公共密钥令牌_b77a5c561934e089"  
 如果安装了 .NET 框架 4，然后启用了 WCF HTTP 激活，则会发生此错误。 要解决此问题，请将以下命令行从可视化工作室的开发人员命令提示符中运行：  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>请参阅

- [设置说明](./samples/set-up-instructions.md)
