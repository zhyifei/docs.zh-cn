---
title: IAssemblyCacheItem 接口
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193604068e379d62107b25f2bc348cd7c8bc6e98
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796705"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem 接口
表示全局程序集缓存中的单个程序集。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[AbortItem 方法](iassemblycacheitem-abortitem-method.md)|允许全局程序集缓存中的程序集在发布前执行清除操作。|  
|[Commit 方法](iassemblycacheitem-commit-method.md)|将缓存的程序集引用提交到内存。|  
|[CreateStream 方法](iassemblycacheitem-createstream-method.md)|创建具有指定名称和格式的流。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
- [全局程序集缓存](../../app-domains/gac.md)
- [IAssemblyCache 接口](iassemblycache-interface.md)
