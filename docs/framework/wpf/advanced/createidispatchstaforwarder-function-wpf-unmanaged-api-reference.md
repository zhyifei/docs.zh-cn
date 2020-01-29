---
title: CreateIDispatchSTAForwarder 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738028"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder 函数（WPF 非托管 API 参考）
此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。  
  
 由 Windows Presentation Foundation （WPF）基础结构用于线程和 Windows 管理。  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>매개 변수  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 pDispatchDelegate  
 指向 `IDispatch` 接口的指针。  
  
 ppForwarder  
 指向 `IDispatch` 接口的地址的指针。  
  
## <a name="requirements"></a>요구 사항  
 **平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [F 관리되지 않는 API 참조](wpf-unmanaged-api-reference.md)
