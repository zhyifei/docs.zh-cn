---
title: ICLRAssemblyIdentityManager 接口
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: f06c8228d5eb850c0d5ff94d12be03d7fb75023b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615912"
---
# <a name="iclrassemblyidentitymanager-interface"></a>ICLRAssemblyIdentityManager 接口
提供一些方法，这些方法支持宿主与公共语言运行时（CLR）与程序集之间的通信。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetBindingIdentityFromFile 方法](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|获取指定文件路径处的程序集的程序集标识绑定数据。|  
|[GetBindingIdentityFromStream 方法](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|获取指定流中的程序集的规范程序集标识数据。|  
|[GetCLRAssemblyReferenceList 方法](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|从提供的部分程序集标识列表中获取[ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)实例。|  
|[GetProbingAssembliesFromReference 方法](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|获取具有指定标识的程序集所引用的程序集标识的[ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)枚举器。|  
|[GetReferencedAssembliesFromFile 方法](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|获取一个[ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)实例，该实例包含程序集在指定文件路径处引用的程序集的列表。|  
|[GetReferencedAssembliesFromStream 方法](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|获取一个指向 `ICLRReferenceAssemblyEnum` 对象的指针，该对象包含指定流中的程序集所引用的程序集的程序集标识数据。|  
|[IsStronglyNamed 方法](iclrassemblyidentitymanager-isstronglynamed-method.md)|获取一个值，该值指示指定的程序集是否具有强名称。|  
  
## <a name="remarks"></a>备注  
 用于 `ICLRAssemblyIdentityManager` 获取的实例 `ICLRAssemblyReferenceList` 并枚举程序集标识。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRAssemblyReferenceList 接口](iclrassemblyreferencelist-interface.md)
- [ICLRProbingAssemblyEnum 接口](iclrprobingassemblyenum-interface.md)
- [承载接口](hosting-interfaces.md)
