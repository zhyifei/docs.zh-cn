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
ms.openlocfilehash: c68ec0b41bb38afc7cefaf47df718fffcf42d250
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842423"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="04bfd-102">IManagedObject::GetSerializedBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="04bfd-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="04bfd-103">获取此托管对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="04bfd-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04bfd-104">语法</span><span class="sxs-lookup"><span data-stu-id="04bfd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04bfd-105">参数</span><span class="sxs-lookup"><span data-stu-id="04bfd-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="04bfd-106">弄指向字符串的指针，该字符串是序列化的对象。</span><span class="sxs-lookup"><span data-stu-id="04bfd-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04bfd-107">备注</span><span class="sxs-lookup"><span data-stu-id="04bfd-107">Remarks</span></span>  
 <span data-ttu-id="04bfd-108">`GetSerializedBuffer`方法会序列化对象，以便将其封送到客户端。</span><span class="sxs-lookup"><span data-stu-id="04bfd-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04bfd-109">要求</span><span class="sxs-lookup"><span data-stu-id="04bfd-109">Requirements</span></span>  
 <span data-ttu-id="04bfd-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04bfd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04bfd-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="04bfd-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04bfd-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="04bfd-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04bfd-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04bfd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04bfd-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04bfd-114">See also</span></span>

- [<span data-ttu-id="04bfd-115">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="04bfd-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
