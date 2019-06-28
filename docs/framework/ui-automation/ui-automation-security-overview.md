---
title: UI 自动化安全性概述
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: c74f770f917fc3b2a7d3a18c08270745dac68b12
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422431"
---
# <a name="ui-automation-security-overview"></a>UI 自动化安全性概述

> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。

此概述介绍了的安全模式 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 中 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)]的安全模式。

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>用户帐户控制

安全性是 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 的主要焦点，其中创新是指用户以标准用户（非管理员）身份运行的能力，无需阻止运行需要更高特权的应用程序和服务。

在 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]中，大多数应用程序都提供有标准令牌或管理令牌。 如果无法将应用程序标识为管理应用程序，则默认情况下会作为标准应用程序启动。 用户必须同意 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 提示的运行提升的应用程序才能启动标识为管理的应用程序。 即使用户是本地“Administrators”组的成员，也会在默认情况下显示同意提示，这是因为管理员以标准用户身份运行，直到需要管理凭据的应用程序或系统组件请求授予运行权限。

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>需要更高特权的任务

当用户尝试执行需要管理特权的任务时， [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 会显示一个对话框，询问用户是否同意继续。 此对话框受到跨进程通信保护，因此恶意软件不能模拟用户输入。 同样，其他进程通常无法访问桌面登录屏幕。

UI 自动化客户端必须与其他进程通信，其中某些进程可能正在以更高特权级别运行。 客户端还可能需要访问对其他进程通常不可视的系统对话框。 因此， [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 客户端必须受到系统信任并且必须使用特殊特权运行。

要获得信任以便与以更高特权级别运行的应用程序通信，必须签名应用程序。

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>清单文件

若要访问受保护的系统 UI，应用程序必须生成与包括清单文件`uiAccess`属性中`requestedExecutionLevel`标记，按如下所示：

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

此代码中的 `level` 属性值只是一个示例。

`uiAccess` 为"false"默认设置。也就是说，如果省略该属性，或者没有为程序集没有清单，应用程序不会无法访问受保护的用户界面。

有关详细信息[!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)]安全性、 签名应用程序和创建程序集清单，请参阅[开发人员最佳实践和最小特权环境中的应用程序的准则](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10))。
