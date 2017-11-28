---
title: "IHostMemoryManager::AcquiredVirtualAddressSpace 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.AcquiredVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480dba9257c34af2cd1bc11aba4a07a4fbbe1162
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a>IHostMemoryManager::AcquiredVirtualAddressSpace 方法
通知主机公共语言运行时 (CLR) 已获取从操作系统指定的内存。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a>参数  
 `startAddress`  
 [in]内存起始地址。  
  
 `size`  
 [in]以字节为单位，内存的大小。  
  
## <a name="remarks"></a>备注  
 `AcquiredVirtualAddressSpace`方法是一个回调方法，必须在承载应用程序的编写器实现。 它是由 CLR 调用。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
