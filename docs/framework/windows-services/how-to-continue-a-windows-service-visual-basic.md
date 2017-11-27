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
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="2ef8b-102">如何：继续 Windows 服务 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="2ef8b-103">此示例使用<xref:System.ServiceProcess.ServiceController>要继续在本地计算机上的 IIS 管理服务组件。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ef8b-104">示例</span><span class="sxs-lookup"><span data-stu-id="2ef8b-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="2ef8b-105">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="2ef8b-106">代码段选择器，在位于**Windows 操作系统 > Windows 服务**。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="2ef8b-107">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ef8b-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="2ef8b-108">Compiling the Code</span></span>  
 <span data-ttu-id="2ef8b-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="2ef8b-109">This example requires:</span></span>  
  
-   <span data-ttu-id="2ef8b-110">对 System.serviceprocess.dll 的项目引用。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="2ef8b-111">对 <xref:System.ServiceProcess> 命名空间成员的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="2ef8b-112">如果未在代码中完全限定成员名称，则添加 `Imports` 语句。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="2ef8b-113">有关详细信息，请参阅 [Imports 语句（.NET 命名空间和类型）](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2ef8b-114">可靠编程</span><span class="sxs-lookup"><span data-stu-id="2ef8b-114">Robust Programming</span></span>  
 <span data-ttu-id="2ef8b-115"><xref:System.ServiceProcess.ServiceController.MachineName%2A>属性<xref:System.ServiceProcess.ServiceController>类是默认情况下的在本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="2ef8b-116">若要引用另一台计算机上的 Windows 服务，更改<xref:System.ServiceProcess.ServiceController.MachineName%2A>属性设置为该计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="2ef8b-117">不能调用<xref:System.ServiceProcess.ServiceController.Continue%2A>服务的服务控制器状态之前上方法<xref:System.ServiceProcess.ServiceControllerStatus.Paused>。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="2ef8b-118">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="2ef8b-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="2ef8b-119">无法恢复该服务。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-119">The service cannot be resumed.</span></span> <span data-ttu-id="2ef8b-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-120">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="2ef8b-121">访问 API 时出错。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="2ef8b-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2ef8b-123">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="2ef8b-123">.NET Framework Security</span></span>  
 <span data-ttu-id="2ef8b-124">控制的服务的计算机上可能会限制通过<xref:System.ServiceProcess.ServiceControllerPermissionAccess>枚举来设置权限<xref:System.ServiceProcess.ServiceControllerPermission>类。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="2ef8b-125">服务信息的访问权限可能会限制通过<xref:System.Security.Permissions.PermissionState>枚举来设置权限<xref:System.Security.Permissions.SecurityPermission>类。</span><span class="sxs-lookup"><span data-stu-id="2ef8b-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef8b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ef8b-126">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [<span data-ttu-id="2ef8b-127">如何： 暂停 Windows 服务 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
