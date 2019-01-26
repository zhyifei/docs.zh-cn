---
title: IAssemblyCacheItem::Commit 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b39cdec6d5cc10256c2911c98f94b7565295408
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537993"
---
# <a name="iassemblycacheitemcommit-method"></a>IAssemblyCacheItem::Commit 方法
提交对内存的缓存程序集引用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFlags`  
 [in]包括的标志。  
  
 `pulDisposition`  
 [out，optional]一个值，指示操作的结果。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [IAssemblyCacheItem 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
