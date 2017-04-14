---
title: "如何：禁用强名称跳过功能 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "强名称跳过功能"
  - "强名称程序集，加载到信任的应用程序域中"
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
caps.latest.revision: 30
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 30
---
# 如何：禁用强名称跳过功能
从 .NET Framework 3.5 Service Pack 1 \(SP1\) 开始，在将程序集载入完全信任 <xref:System.AppDomain> 对象（例如 `MyComputer` 区域的默认 <xref:System.AppDomain>）时，将不验证强名称签名。  这称为强名称跳过功能。  在完全信任环境中，对于已签名的完全信任程序集，无论这些程序集的签名是什么，对 <xref:System.Security.Permissions.StrongNameIdentityPermission> 的要求将总是成功。  唯一的限制是该程序集必须完全受信任，因为该程序集的区域是完全受信任的。  因为在这些情况下强名称不是决定性因素，所以没有理由验证强名称。  跳过对强名称签名的验证可显著提高性能。  
  
 跳过功能适用于未经延迟签名的任何完全信任程序集，以及从由其 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性指定的目录载入到任何完全信任 <xref:System.AppDomain> 中的完全信任程序集。  
  
 可通过设置注册表项值来重写计算机中所有应用程序的跳过功能。  可以使用应用程序配置文件来重写单个应用程序的设置。  如果通过注册表项禁用了单个应用程序的跳过功能，则无法恢复该功能。  
  
 重写跳过功能后，将只验证强名称的正确性，而不检查其 <xref:System.Security.Permissions.StrongNameIdentityPermission>。  如果要确认特定的强名称，必须单独执行该项检查。  
  
> [!IMPORTANT]
>  是否能强制执行强名称验证取决于注册表项，如下面的过程所述。  如果运行应用程序时使用的帐户没有访问该注册表项的访问控制列表 \(ACL\) 权限，该设置将无效。  必须确保配置此注册表项的 ACL 权限，以使所有程序集都能读取此项。  
  
### 对所有应用程序禁用强名称跳过功能  
  
-   在 32 位计算机上的系统注册表中，在 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 项下创建一个名为 `AllowStrongNameBypass` 值为 0 的 DWORD 项。  
  
-   在 64 位计算机上的系统注册表中，在 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 和 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework 项下创建一个名为 `AllowStrongNameBypass` 值为 0 的 DWORD 项。  
  
### 对单个应用程序禁用强名称跳过功能  
  
1.  打开或创建应用程序配置文件。  
  
     有关此文件的更多信息，请参见[配置应用](../../../docs/framework/configure-apps/index.md)中的“应用程序配置文件”一节。  
  
2.  添加下面的项：  
  
    ```  
    <configuration>  
      <runtime>  
         < bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 可通过移除该配置文件设置或将该特性设置为“true”为该应用程序恢复跳过功能。  
  
> [!NOTE]
>  只有在已为计算机启用跳过功能的情况下，才能为应用程序打开和关闭强名称验证。  如果已为计算机关闭跳过功能，则将对所有应用程序验证强名称，并且不能对单个应用程序跳过验证。  
  
## 请参阅  
 [Sn.exe（强名称工具）](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [\<bypassTrustedAppStrongNames\> 元素](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)   
 [创建和使用具有强名称的程序集](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)