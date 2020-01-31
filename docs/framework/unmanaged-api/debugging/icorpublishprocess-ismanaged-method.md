---
title: ICorPublishProcess::IsManaged 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790530"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged 方法
获取一个值，该值指示此[ICorPublishProcess](icorpublishprocess-interface.md)引用的进程是否已知具有托管代码。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>参数  
 `pbManaged`  
 弄一个指向布尔值的指针，该布尔值指示进程是否具有托管代码。 如果进程具有托管代码，则值为 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 由于 `ICorPublishProcess` 的当前版本只允许访问具有托管代码的进程，`IsManaged` 总是返回 `true`。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorPublishProcess 接口](icorpublishprocess-interface.md)
