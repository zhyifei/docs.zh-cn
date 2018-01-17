---
title: "IMetaDataEmit::GetSaveSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7585f6adbca97b252fdad90276b0cd422d32c04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize 方法
获取当前范围内的程序集和其元数据的估计二进制大小。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fSave`  
 [in]值为[CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)枚举，它指定是否获取的准确或近似大小。 只有三个值都无效： cssAccurate，cssQuick，和 cssDiscardTransientCAs:  
  
-   cssAccurate 返回准确的存储大小，但需要更长的计算。  
  
-   cssQuick 返回的大小，为安全起见，填充，但需要更少时间来计算。  
  
-   cssDiscardTransientCAs 告知`GetSaveSize`，它可以抛弃可丢弃的自定义属性。  
  
 `pdwSaveSize`  
 [out]指向保存该文件所需的大小的指针。  
  
## <a name="remarks"></a>备注  
 `GetSaveSize`计算所需的空间，以字节为单位，以保存在当前范围内的程序集和所有元数据。 (调用[imetadataemit:: Savetostream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)方法将发出此数目的字节。)  
  
 如果调用方实现[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)接口 (通过[imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)或[imetadataemit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md))，`GetSaveSize`将执行两个周期通过优化并压缩的元数据。 否则，不执行任何优化。  
  
 如果执行优化，则第一次传递只需进行排序的元数据结构调整导入时搜索的性能。 此步骤通常会导致移动解决问题，并且保留供将来参考工具的令牌将会失效其副作用的记录。 元数据不会通知这些令牌更改之前的调用方后的第二个过程，但是。 第二个阶段中，在各种优化来执行旨在减少将元数据，如优化去除 （早期绑定） 的总体大小`mdTypeRef`和`mdMemberRef`令牌时则引用为的类型或声明中的成员当前的元数据范围。 在此阶段中，会发生令牌映射的另一轮。 在后此阶段中，元数据引擎通知调用方，通过其`IMapToken`接口的任何更改令牌值。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
