---
title: "缓解：应向 CspParameters.ParentWindowHandle 分配 HWND"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b65aaf7149ca29b2af3efdf44ee9489a04c73a2
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a><span data-ttu-id="77c11-102">缓解：应向 CspParameters.ParentWindowHandle 分配 HWND</span><span class="sxs-lookup"><span data-stu-id="77c11-102">Mitigation: CspParameters.ParentWindowHandle Expects an HWND</span></span>

<span data-ttu-id="77c11-103">借助 .NET Framework 2.0 中引入的 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 属性，应用程序可以注册父窗口句柄值，这样任何需要访问密钥的 UI（如 PIN 提示或同意对话框）将会作为指定窗口的子模式打开。</span><span class="sxs-lookup"><span data-stu-id="77c11-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property, introduced in the .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or a consent dialog) opens as a modal child to the specified window.</span></span> <span data-ttu-id="77c11-104">自定位 .NET Framework 4.7 的应用程序起，可以向此属性分配窗口句柄 (HWND)。</span><span class="sxs-lookup"><span data-stu-id="77c11-104">Starting with applications that target the .NET Framework 4.7, a window handle (HWND) can be assigned to this property.</span></span>

<span data-ttu-id="77c11-105">在 .NET Framework 4.6.2 及更早版本中，分配给 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 属性的值应为 <xref:System.IntPtr>，用于表示 HWND 值在内存中的驻留位置。</span><span class="sxs-lookup"><span data-stu-id="77c11-105">In versions of the .NET Framework through the .NET Framework 4.6.2, the value assigned to the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property was expected to be an <xref:System.IntPtr> that represents the location in memory where the HWND value resided.</span></span> <span data-ttu-id="77c11-106">在 Windows 7 和旧版 Windows 操作系统上，将属性设置为 `form.Handle` 不会造成任何影响；但在 Windows 8 及更高版本上，此操作会生成 <xref:System.Security.Cryptography> 并显示消息“参数不正确。”</span><span class="sxs-lookup"><span data-stu-id="77c11-106">On Windows 7 and earlier versions of the Windows operating system, setting the property to `form.Handle` had no effect, but on Windows 8 and later versions, it results in a <xref:System.Security.Cryptography> with the message, "The parameter is incorrect."</span></span>

<span data-ttu-id="77c11-107">自面向 .NET Framework 4.7 的应用起，Windows 窗体应用程序可以使用如下代码设置 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 属性：</span><span class="sxs-lookup"><span data-stu-id="77c11-107">Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a><span data-ttu-id="77c11-108">影响</span><span class="sxs-lookup"><span data-stu-id="77c11-108">Impact</span></span>

<span data-ttu-id="77c11-109">对于要注册父窗口关系且定位 .NET Framework 4.7 或更高版本的应用程序，建议使用简易窗体：</span><span class="sxs-lookup"><span data-stu-id="77c11-109">Applications targeting the .NET Framework 4.7 or later that wish to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a><span data-ttu-id="77c11-110">缓解操作</span><span class="sxs-lookup"><span data-stu-id="77c11-110">Mitigation</span></span>

<span data-ttu-id="77c11-111">已确定正确值是保留 `form.Handle` 值的内存位置地址的开发者可以将 <xref:System.AppContext> 开关 `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` 设置为 `true`，从而选择禁用此行为更改：</span><span class="sxs-lookup"><span data-stu-id="77c11-111">Developers who had identified that the correct value was the address of the memory location that held the `form.Handle` value can opt out of this change in behavior by setting the <xref:System.AppContext> switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="77c11-112">以编程方式对 <xref:System.AppContext> 实例设置兼容性开关。</span><span class="sxs-lookup"><span data-stu-id="77c11-112">By programmatically setting compatibility switches on the <xref:System.AppContext> instance.</span></span>

- <span data-ttu-id="77c11-113">在 app.config 文件的 `<runtime>` 部分中添加下面的代码行：</span><span class="sxs-lookup"><span data-stu-id="77c11-113">By adding the following line to the `<runtime>` section of the app.config file:</span></span>
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

<span data-ttu-id="77c11-114">相反，希望为在 .NET Framework 4.7 控制下运行，但面向旧版 .NET Framework 的应用程序选择启用新行为的用户可以将 <xref:System.AppContext> 开关设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="77c11-114">Conversely, users who wish to opt in to the new behavior for applications that run under the .NET Framework 4.7 but target an earlier version of the .NET Framework versions can set the <xref:System.AppContext> switch to `false`.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="77c11-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="77c11-115">See also</span></span>

[<span data-ttu-id="77c11-116">.NET Framework 4.7 中的重定目标更改</span><span class="sxs-lookup"><span data-stu-id="77c11-116">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

