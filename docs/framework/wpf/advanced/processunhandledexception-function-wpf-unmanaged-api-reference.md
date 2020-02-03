---
title: ProcessUnhandledException 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743920"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>ProcessUnhandledException 函数（WPF 非托管 API 参考）
此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。  
  
 由 Windows Presentation Foundation （WPF）基础结构用于异常处理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a>参数  
 errorMsg  
 错误消息。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
