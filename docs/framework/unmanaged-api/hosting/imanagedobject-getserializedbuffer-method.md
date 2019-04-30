---
title: IManagedObject::GetSerializedBuffer 方法
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb9242160b684b3c7b90756d7b20811ad162fc30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043624"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="9e2f3-102">IManagedObject::GetSerializedBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="9e2f3-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="9e2f3-103">获取此托管对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="9e2f3-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e2f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e2f3-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e2f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e2f3-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="9e2f3-106">[out]指向为序列化的对象的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="9e2f3-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e2f3-107">备注</span><span class="sxs-lookup"><span data-stu-id="9e2f3-107">Remarks</span></span>  
 <span data-ttu-id="9e2f3-108">`GetSerializedBuffer`方法序列化的对象，因此它可以封送到客户端。</span><span class="sxs-lookup"><span data-stu-id="9e2f3-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e2f3-109">要求</span><span class="sxs-lookup"><span data-stu-id="9e2f3-109">Requirements</span></span>  
 <span data-ttu-id="9e2f3-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e2f3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e2f3-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e2f3-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e2f3-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9e2f3-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e2f3-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e2f3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e2f3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e2f3-114">See also</span></span>

- [<span data-ttu-id="9e2f3-115">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="9e2f3-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
