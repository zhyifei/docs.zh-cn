---
title: "UI 自动化安全性概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
caps.latest.revision: "23"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: ee3847164ecdc9b9868d806b5a1394ffca0bbd31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="6c40e-102">UI 自动化安全性概述</span><span class="sxs-lookup"><span data-stu-id="6c40e-102">UI Automation Security Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="6c40e-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="6c40e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6c40e-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="6c40e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6c40e-105">此概述介绍了的安全模式 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 中 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)]的安全模式。</span><span class="sxs-lookup"><span data-stu-id="6c40e-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span></span>  
  
<a name="User_Account_Control"></a>   
## <a name="user-account-control"></a><span data-ttu-id="6c40e-106">用户帐户控制</span><span class="sxs-lookup"><span data-stu-id="6c40e-106">User Account Control</span></span>  
 <span data-ttu-id="6c40e-107">安全性是 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 的主要焦点，其中创新是指用户以标准用户（非管理员）身份运行的能力，无需阻止运行需要更高特权的应用程序和服务。</span><span class="sxs-lookup"><span data-stu-id="6c40e-107">Security is a major focus of [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>  
  
 <span data-ttu-id="6c40e-108">在 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]中，大多数应用程序都提供有标准令牌或管理令牌。</span><span class="sxs-lookup"><span data-stu-id="6c40e-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="6c40e-109">如果无法将应用程序标识为管理应用程序，则默认情况下会作为标准应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="6c40e-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="6c40e-110">用户必须同意 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 提示的运行提升的应用程序才能启动标识为管理的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c40e-110">Before an application identified as administrative can be launched, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="6c40e-111">即使用户是本地“Administrators”组的成员，也会在默认情况下显示同意提示，这是因为管理员以标准用户身份运行，直到需要管理凭据的应用程序或系统组件请求授予运行权限。</span><span class="sxs-lookup"><span data-stu-id="6c40e-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>  
  
<a name="Tasks_Requiring_Higher_Privileges"></a>   
## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="6c40e-112">需要更高特权的任务</span><span class="sxs-lookup"><span data-stu-id="6c40e-112">Tasks Requiring Higher Privileges</span></span>  
 <span data-ttu-id="6c40e-113">当用户尝试执行需要管理特权的任务时， [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 会显示一个对话框，询问用户是否同意继续。</span><span class="sxs-lookup"><span data-stu-id="6c40e-113">When a user attempts to perform a task that requires administrative privileges, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="6c40e-114">此对话框受到跨进程通信保护，因此恶意软件不能模拟用户输入。</span><span class="sxs-lookup"><span data-stu-id="6c40e-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="6c40e-115">同样，其他进程通常无法访问桌面登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="6c40e-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>  
  
 <span data-ttu-id="6c40e-116">UI 自动化客户端必须与其他进程通信，其中某些进程可能正在以更高特权级别运行。</span><span class="sxs-lookup"><span data-stu-id="6c40e-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="6c40e-117">客户端还可能需要访问对其他进程通常不可视的系统对话框。</span><span class="sxs-lookup"><span data-stu-id="6c40e-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="6c40e-118">因此， [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 客户端必须受到系统信任并且必须使用特殊特权运行。</span><span class="sxs-lookup"><span data-stu-id="6c40e-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>  
  
 <span data-ttu-id="6c40e-119">要获得信任以便与以更高特权级别运行的应用程序通信，必须签名应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c40e-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>  
  
<a name="Manifest_Files"></a>   
## <a name="manifest-files"></a><span data-ttu-id="6c40e-120">清单文件</span><span class="sxs-lookup"><span data-stu-id="6c40e-120">Manifest Files</span></span>  
 <span data-ttu-id="6c40e-121">要想获取对受保护系统 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]的访问权限，必须使用包含特殊属性的清单文件生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c40e-121">To gain access to the protected system [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], applications must be built with a manifest file that includes a special attribute in the manifest file.</span></span> <span data-ttu-id="6c40e-122">`uiAccess` 属性包含在 `requestedExecutionLevel` 标记中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c40e-122">This `uiAccess` attribute is included in the `requestedExecutionLevel` tag, as follows:</span></span>  
  
 `<trustInfo xmlns="urn:0073chemas-microsoft-com:asm.v3">`  
  
 `<security>`  
  
 `<requestedPrivileges>`  
  
 `<requestedExecutionLevel`  
  
 `level="highestAvailable"`  
  
 `UIAccess="true" />`  
  
 `</requestedPrivileges>`  
  
 `</security>`  
  
 `</trustInfo>`  
  
 <span data-ttu-id="6c40e-123">此代码中的 `level` 属性值只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="6c40e-123">The value of the `level` attribute in this code is an example only.</span></span>  
  
 <span data-ttu-id="6c40e-124">默认情况下，`UIAccess` 为“false”；即，如果省略该属性或如果没有程序集清单，则应用程序将无法获取对受保护的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c40e-124">`UIAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="6c40e-125">有关 [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] 安全性、签名应用程序和创建程序集清单的详细信息，请参阅  [MSDN](http://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp)上的“最小特权环境中应用程序开发人员的最佳做法和准则”。</span><span class="sxs-lookup"><span data-stu-id="6c40e-125">For more information on [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] security, on signing applications, and on creating assembly manifests, see "Developer Best Practices and Guidelines for Applications in a Least Privileged Environment" on  [MSDN](http://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).</span></span>
