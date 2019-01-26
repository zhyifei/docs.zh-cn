---
title: CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 215f6ff727b814e7e7d7c708c29a8c5221f5797f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575971"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 Windows Presentation Foundation (WPF) 基础结构使用的线程和 windows 管理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a>参数  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 pDispatchDelegate  
 一个指向`IDispatch`接口。  
  
 ppForwarder  
 指向的地址的指针`IDispatch`接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[.NET Framework 系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **DLL:**  
  
 在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll  
  
 在.NET Framework 4 及更高版本：PresentationHost_v0400.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [WPF 非托管 API 参考](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
