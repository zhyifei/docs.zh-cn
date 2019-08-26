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
ms.openlocfilehash: a886106e5da49e7124dac5c8ea7416859aa441da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929847"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>ICLRRuntimeInfo::GetVersionString 方法
获取与给定的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口相关联的公共语言运行时 (CLR) 版本信息。  
  
 此方法取代了以下函数:  
  
- [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
- [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>参数  
 `pwzBuffer`  
 弄"V*A*" 格式的 .NET Framework 编译版本。*B*[.*X*] "。 *A*、 *B*和*X*是与主版本、次版本和生成号对应的十进制数字。 *X*是可选的。 如果*X*不存在, 则没有尾随句点。  
  
> [!NOTE]
> 此参数必须匹配 .NET Framework 版本的目录名称, 因为它显示在 C:\Windows\Microsoft.NET\Framework. 下。  
  
 示例值为 "v1.0.3705"、"v 1.1.4322"、"v 2.0.50727" 和 "v4.0"。*x*", 其中*x*依赖于安装的生成号。 请注意, "v" 前缀是必需的。  
  
 `pchBuffer`  
 [in, out]指定的大小`pwzBuffer`以避免缓冲区溢出。 如果`pwzBuffer`为`null` `pwzBuffer` ,则返回`pchBuffer`所需的大小以允许预先分配。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pwzBuffer` 或 `pchBuffer` 为 null。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [.NET Framework 4 和 4.5 中添加的 CLR 承载接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
