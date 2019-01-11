---
title: s_isDebuggerCheckDisabledForTestPurposes 字段
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ada3abcccac4244819cfbef1101a770761df6a50
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221916"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="7b090-102">s_isDebuggerCheckDisabledForTestPurposes 字段</span><span class="sxs-lookup"><span data-stu-id="7b090-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="7b090-103">在此专用字段`System.Windows.Diagnostics.VisualDiagnostics`类由 Visual Studio 用来确定是否将执行活动的调试器内部检查。</span><span class="sxs-lookup"><span data-stu-id="7b090-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b090-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b090-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="7b090-105">API 中的`System.Windows.Diagnostics.VisualDiagnostics`当在调试器下运行应用程序时，类才可用。</span><span class="sxs-lookup"><span data-stu-id="7b090-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="7b090-106">设置`s_isDebuggerCheckDisabledForTestPurposes`到`true`访问调试器外的 Api。</span><span class="sxs-lookup"><span data-stu-id="7b090-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="7b090-107">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="7b090-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="7b090-108">要求</span><span class="sxs-lookup"><span data-stu-id="7b090-108">Requirements</span></span>

<span data-ttu-id="7b090-109">**Namespace**：<xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="7b090-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="7b090-110">**程序集：** PresentationCore （在 PresentationCore.dll 中)</span><span class="sxs-lookup"><span data-stu-id="7b090-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="7b090-111">**.NET framework 版本：** 自 4.6 之后可用。</span><span class="sxs-lookup"><span data-stu-id="7b090-111">**.NET Framework versions:** Available since 4.6.</span></span>