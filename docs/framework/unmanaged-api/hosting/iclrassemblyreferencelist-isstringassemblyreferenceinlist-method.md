---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
ms.openlocfilehash: 91f174cab4986882df795eb531baedfc0dd43962
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615860"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a>ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 方法
获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a>参数  
 `pwzAssemblyName`  
 中要搜索的程序集的名称。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|此字符串将显示在列表中。|  
|S_FALSE|该字符串未出现在列表中。|  
|E_FAIL|发生未知的灾难性故障。 方法返回 E_FAIL 后，公共语言运行时在进程中将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRAssemblyIdentityManager 接口](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 接口](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 接口](ihostassemblymanager-interface.md)
- [IHostAssemblyStore 接口](ihostassemblystore-interface.md)
