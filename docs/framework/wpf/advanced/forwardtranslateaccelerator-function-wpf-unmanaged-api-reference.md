---
title: ForwardTranslateAccelerator 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747047"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>ForwardTranslateAccelerator 函数（WPF 非托管 API 参考）
此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。  
  
 由用于 Windows 管理的 Windows Presentation Foundation （WPF）基础结构使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>参数  
 pMsg  
 指向消息的指针。  
  
 appUnhandled  
 当应用程序有机会处理输入消息但尚未处理时 `true`;否则，`false`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
