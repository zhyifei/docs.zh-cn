---
title: "IAssemblyCacheItem::CreateStream 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a24d9732a8e413b3cde0ac1c622743153ff6fd01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitemcreatestream-method"></a>IAssemblyCacheItem::CreateStream 方法
具有指定的名称和格式创建一个流。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFlags`  
 [in]在包括中定义的标志。  
  
 `pszStreamName`  
 [in]要创建的流名称。  
  
 `dwFormat`  
 [in]要进行流处理的文件的格式。  
  
 `dwFormatFlags`  
 [in]在包括中定义的特定格式的标志。  
  
 `ppIStream`  
 [out]返回的地址指针<xref:IStream>实例。  
  
 `puliMaxSize`  
 [in，可选]引用的流的最大大小`ppIStream`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IAssemblyCacheItem 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
