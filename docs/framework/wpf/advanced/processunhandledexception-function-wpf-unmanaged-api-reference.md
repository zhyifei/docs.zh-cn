---
title: ProcessUnhandledException 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 0c8751454be6e0eed547c38e9d0bc7931abaec3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196965"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>ProcessUnhandledException 函数 （WPF 非托管 API 参考）
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 Windows Presentation Foundation (WPF) 基础结构用于异常处理。  
  
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
 **平台：** 请参阅[.NET Framework 系统需求](../../get-started/system-requirements.md)。  
  
 **DLL:**  
  
 在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll  
  
 在.NET Framework 4 及更高版本：PresentationHost_v0400.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
