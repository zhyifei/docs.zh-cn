---
title: 转发加速器功能 - WPF 非托管 API 引用
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186623"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>转发加速器功能（WPF 非托管 API 引用）
此 API 支持 Windows 演示基础 （WPF） 基础结构，不用于直接从代码中使用。  
  
 由 Windows 演示基础 （WPF） 基础结构用于窗口管理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>parameters  
 pMsg  
 指向消息的指针。  
  
 应用程序未处理  
 `true`当应用程序已有机会处理输入消息，但尚未处理它;否则， `false`.  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[.NET 框架系统要求](../../get-started/system-requirements.md)。  
  
 **Dll：**  
  
 在 .NET 框架 3.0 和 3.5 中：演示HostDLL.dll  
  
 在 .NET 框架 4 及更高版本：PresentationHost_v0400.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
