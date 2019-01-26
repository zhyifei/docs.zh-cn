---
title: ICLRRuntimeInfo::GetRuntimeDirectory 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26bee605724fd69d972a7e07c6fe6be2fbcabfa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563855"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a>ICLRRuntimeInfo::GetRuntimeDirectory 方法
获取与此接口关联的公共语言运行时 (CLR) 的安装目录。  
  
 此方法取代[GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)在.NET Framework 版本 2.0、 3.0 和 3.5 中提供的函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzBuffer`  
 [out]返回 CLR 安装目录。 安装路径是完全限定的;例如，"c:\windows\microsoft.net\framework\v1.0.3705\\"。  
  
 `pchBuffer`  
 [in、 out]指定的大小`pwzBuffer`以避免缓冲区溢出。 如果`pwzBuffer`为 null，`pchBuffer`返回的所需的大小`pwzBuffer`。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pwzBuffer` 或 `pchBuffer` 为 null。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：** 包含为 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
