---
title: UI 自动化安全性概述
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: 70d24c3dcc531abcec6d4dce75b5f0b31757e0c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448770"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="c1bac-102">UI 自动化安全性概述</span><span class="sxs-lookup"><span data-stu-id="c1bac-102">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="c1bac-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="c1bac-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c1bac-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="c1bac-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="c1bac-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="c1bac-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="c1bac-106">用户帐户控制</span><span class="sxs-lookup"><span data-stu-id="c1bac-106">User Account Control</span></span>

<span data-ttu-id="c1bac-107">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span><span class="sxs-lookup"><span data-stu-id="c1bac-107">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="c1bac-108">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span><span class="sxs-lookup"><span data-stu-id="c1bac-108">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="c1bac-109">如果无法将应用程序标识为管理应用程序，则默认情况下会作为标准应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="c1bac-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="c1bac-110">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span><span class="sxs-lookup"><span data-stu-id="c1bac-110">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="c1bac-111">即使用户是本地“Administrators”组的成员，也会在默认情况下显示同意提示，这是因为管理员以标准用户身份运行，直到需要管理凭据的应用程序或系统组件请求授予运行权限。</span><span class="sxs-lookup"><span data-stu-id="c1bac-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="c1bac-112">需要更高特权的任务</span><span class="sxs-lookup"><span data-stu-id="c1bac-112">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="c1bac-113">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span><span class="sxs-lookup"><span data-stu-id="c1bac-113">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="c1bac-114">此对话框受到跨进程通信保护，因此恶意软件不能模拟用户输入。</span><span class="sxs-lookup"><span data-stu-id="c1bac-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="c1bac-115">同样，其他进程通常无法访问桌面登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="c1bac-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="c1bac-116">UI 自动化客户端必须与其他进程通信，其中某些进程可能正在以更高特权级别运行。</span><span class="sxs-lookup"><span data-stu-id="c1bac-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="c1bac-117">客户端还可能需要访问对其他进程通常不可视的系统对话框。</span><span class="sxs-lookup"><span data-stu-id="c1bac-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="c1bac-118">因此， [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 客户端必须受到系统信任并且必须使用特殊特权运行。</span><span class="sxs-lookup"><span data-stu-id="c1bac-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="c1bac-119">要获得信任以便与以更高特权级别运行的应用程序通信，必须签名应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1bac-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="c1bac-120">清单文件</span><span class="sxs-lookup"><span data-stu-id="c1bac-120">Manifest Files</span></span>

<span data-ttu-id="c1bac-121">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span><span class="sxs-lookup"><span data-stu-id="c1bac-121">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="c1bac-122">此代码中的 `level` 属性值只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="c1bac-122">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="c1bac-123">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span><span class="sxs-lookup"><span data-stu-id="c1bac-123">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>
