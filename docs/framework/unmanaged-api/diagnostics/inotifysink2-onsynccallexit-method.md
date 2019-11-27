---
title: INotifySink2::OnSyncCallExit 方法
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
ms.openlocfilehash: 03b8afc1276dae6244bcf12bd0bc78c2fa5380bb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448679"
---
# <a name="inotifysink2onsynccallexit-method"></a>INotifySink2::OnSyncCallExit 方法
在退出调用时调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>参数  
 `in_CallID`  
 中正在退出的调用的 ID。 请参阅[CALL_ID 结构](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)。  
  
 `out_ppBuffer`  
 弄调用缓冲区。  
  
 `out_pBufferSize`  
 弄调用缓冲区的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则 S_OK。  
  
## <a name="requirements"></a>要求  
 **标头：** ProtocolNotify2 .idl  
  
## <a name="see-also"></a>另请参阅

- [INotifySink2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [INotifySource2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [INotifyConnection2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
