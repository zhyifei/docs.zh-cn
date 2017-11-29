---
title: "IManagedObject::GetSerializedBuffer 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetSerializedBuffer
api_location: mscoree.dll
api_type: COM
f1_keywords: GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d326fba5cbdb38dd2c5d07f4f69f3f2d8e75114c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="eeb6f-102">IManagedObject::GetSerializedBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="eeb6f-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="eeb6f-103">获取此托管对象的字符串表示。</span><span class="sxs-lookup"><span data-stu-id="eeb6f-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb6f-104">语法</span><span class="sxs-lookup"><span data-stu-id="eeb6f-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eeb6f-105">参数</span><span class="sxs-lookup"><span data-stu-id="eeb6f-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="eeb6f-106">[out]指向的序列化的对象的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="eeb6f-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eeb6f-107">备注</span><span class="sxs-lookup"><span data-stu-id="eeb6f-107">Remarks</span></span>  
 <span data-ttu-id="eeb6f-108">`GetSerializedBuffer`方法序列化对象，因此它可以封送到客户端。</span><span class="sxs-lookup"><span data-stu-id="eeb6f-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeb6f-109">要求</span><span class="sxs-lookup"><span data-stu-id="eeb6f-109">Requirements</span></span>  
 <span data-ttu-id="eeb6f-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eeb6f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb6f-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eeb6f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eeb6f-112">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eeb6f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eeb6f-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb6f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb6f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eeb6f-114">See Also</span></span>  
 [<span data-ttu-id="eeb6f-115">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="eeb6f-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
