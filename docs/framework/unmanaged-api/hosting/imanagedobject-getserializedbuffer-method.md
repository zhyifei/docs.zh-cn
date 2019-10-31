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
ms.openlocfilehash: 4a55ae265230c4da3cc0a19b06a7597be8661beb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103250"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="9fd6c-102">IManagedObject::GetSerializedBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="9fd6c-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="9fd6c-103">获取此托管对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd6c-104">语法</span><span class="sxs-lookup"><span data-stu-id="9fd6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fd6c-105">参数</span><span class="sxs-lookup"><span data-stu-id="9fd6c-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="9fd6c-106">弄指向字符串的指针，该字符串是序列化的对象。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fd6c-107">备注</span><span class="sxs-lookup"><span data-stu-id="9fd6c-107">Remarks</span></span>  
 <span data-ttu-id="9fd6c-108">`GetSerializedBuffer` 方法会序列化对象，以便将其封送到客户端。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fd6c-109">要求</span><span class="sxs-lookup"><span data-stu-id="9fd6c-109">Requirements</span></span>  
 <span data-ttu-id="9fd6c-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fd6c-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9fd6c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fd6c-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9fd6c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fd6c-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fd6c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd6c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9fd6c-114">See also</span></span>

- [<span data-ttu-id="9fd6c-115">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="9fd6c-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
