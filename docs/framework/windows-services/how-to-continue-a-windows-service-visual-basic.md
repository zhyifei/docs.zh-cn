---
title: "如何：继续 Windows 服务 (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 28dbbf2376416a340ad7853c026b2f763f695dcb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>如何：继续 Windows 服务 (Visual Basic)
此示例使用<xref:System.ServiceProcess.ServiceController>要继续在本地计算机上的 IIS 管理服务组件。  
  
## <a name="example"></a>示例  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 此代码示例也可作为 IntelliSense 代码片段。 代码段选择器，在位于**Windows 操作系统 > Windows 服务**。 有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System.serviceprocess.dll 的项目引用。  
  
-   对 <xref:System.ServiceProcess> 命名空间成员的访问权限。 如果未在代码中完全限定成员名称，则添加 `Imports` 语句。 有关详细信息，请参阅 [Imports 语句（.NET 命名空间和类型）](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。  
  
## <a name="robust-programming"></a>可靠编程  
 <xref:System.ServiceProcess.ServiceController.MachineName%2A>属性<xref:System.ServiceProcess.ServiceController>类是默认情况下的在本地计算机。 若要引用另一台计算机上的 Windows 服务，更改<xref:System.ServiceProcess.ServiceController.MachineName%2A>属性设置为该计算机的名称。  
  
 不能调用<xref:System.ServiceProcess.ServiceController.Continue%2A>服务的服务控制器状态之前上方法<xref:System.ServiceProcess.ServiceControllerStatus.Paused>。  
  
 以下情况可能会导致异常：  
  
-   无法恢复该服务。 (<xref:System.InvalidOperationException>)  
  
-   访问 API 时出错。 (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 控制的服务的计算机上可能会限制通过<xref:System.ServiceProcess.ServiceControllerPermissionAccess>枚举来设置权限<xref:System.ServiceProcess.ServiceControllerPermission>类。  
  
 服务信息的访问权限可能会限制通过<xref:System.Security.Permissions.PermissionState>枚举来设置权限<xref:System.Security.Permissions.SecurityPermission>类。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [如何： 暂停 Windows 服务 (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
