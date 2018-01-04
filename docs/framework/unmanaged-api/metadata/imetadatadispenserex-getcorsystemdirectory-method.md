---
title: "IMetaDataDispenserEx::GetCORSystemDirectory 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetCORSystemDirectory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e93f544e504949b496881369c15905ef43a0d2f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a>IMetaDataDispenserEx::GetCORSystemDirectory 方法
获取包含当前的公共语言运行时 (CLR) 的目录。 进程外调试器支持此方法仅供使用。 如果从另一个组件调用，它将返回 E_NOTIMPL。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szBuffer`  
 [out]要接收的目录名称的缓冲区。  
  
 `cchBuffer`  
 [in]大小，以字节为单位的`szBuffer`。  
  
 `pchBuffer`  
 [out]中实际返回的字节数`szBuffer`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
