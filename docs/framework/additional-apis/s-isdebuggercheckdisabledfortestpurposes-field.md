---
title: "s_isDebuggerCheckDisabledForTestPurposes 字段"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
api_name: System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location: PresentationCore.dll
api_type: Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
robots: noindex,nofollow
ms.openlocfilehash: 97e5d32bff3e3150b56e8d9492aacc40f09f2afe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>s_isDebuggerCheckDisabledForTestPurposes 字段

在此专用字段`System.Windows.Diagnostics.VisualDiagnostics`类由 Visual Studio 用来确定是否将执行活动调试器内部检查。

## <a name="syntax"></a>语法
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  API 中的`System.Windows.Diagnostics.VisualDiagnostics`当在调试器下运行应用程序时，类才可用。 设置`s_isDebuggerCheckDisabledForTestPurposes`到`true`访问调试器外部 Api。  
>   
>  Microsoft 不支持在生产应用程序在任何情况下使用此字段。  

## <a name="requirements"></a>要求

**Namespace:**<xref:System.Windows.Diagnostics>

**程序集：** PresentationCore （在 PresentationCore.dll)

**.NET framework 版本：**自 4.6 之后可用。
