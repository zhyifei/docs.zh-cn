---
title: ICLRAssemblyReferenceList 接口
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615873"
---
# <a name="iclrassemblyreferencelist-interface"></a>ICLRAssemblyReferenceList 接口
管理由公共语言运行时（CLR）而不是由宿主加载的程序集的列表。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[IsAssemblyReferenceInList 方法](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|获取一个值，该值指示提供的指针是否引用列表中的程序集。|  
|[IsStringAssemblyReferenceInList 方法](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。|  
  
## <a name="remarks"></a>备注  
 调用[ICLRAssemblyIdentityManager：： GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)方法以获取指向实例的指针 `ICLRAssemblyReferenceList` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRAssemblyIdentityManager 接口](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore 接口](ihostassemblystore-interface.md)
- [承载接口](hosting-interfaces.md)
