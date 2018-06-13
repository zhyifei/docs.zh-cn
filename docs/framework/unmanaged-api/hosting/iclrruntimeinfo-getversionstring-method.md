---
title: ICLRRuntimeInfo::GetVersionString 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b18323644220ffdce1caad966b8a0c2a7baddde2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434632"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>ICLRRuntimeInfo::GetVersionString 方法
获取与关联的公共语言运行时 (CLR) 版本信息给定[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。  
  
 此方法取代以下函数：  
  
-   [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzBuffer`  
 [out]格式中的.NET Framework 编译版本"v*A*。*B*[。*X*]"。 *A*， *B*，和*X*是对应于主版本、 次版本，以及内部版本号的十进制数字。 *X*是可选的。 如果*X*不是存在，则没有尾随句点。  
  
> [!NOTE]
>  此参数必须与它在 C:\Windows\Microsoft.NET\Framework 下显示匹配有关.NET Framework 版本中，目录名。  
  
 示例值为"v1.0.3705"、"v1.1.4322"、"v2.0.50727"和"v4.0。*x*"，其中*x*取决于安装的内部版本号。 请注意，"v"前缀是必需的。  
  
 `pchBuffer`  
 [在中，out]指定的大小`pwzBuffer`以避免缓冲区溢出。 如果`pwzBuffer`是`null`，`pchBuffer`返回的所需的大小`pwzBuffer`以允许预分配。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pwzBuffer` 或 `pchBuffer` 为 null。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [.NET Framework 4 和 4.5 中添加的 CLR 承载接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
