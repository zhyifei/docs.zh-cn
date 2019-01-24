---
title: IMetaDataTables::GetBlob 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa631721965123c4427a5d1ff2e0cec2a1ab2395
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637674"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="78502-102">IMetaDataTables::GetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="78502-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="78502-103">获取一个指向二进制大型对象 (BLOB) 中的指定的列索引处。</span><span class="sxs-lookup"><span data-stu-id="78502-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78502-104">语法</span><span class="sxs-lookup"><span data-stu-id="78502-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78502-105">参数</span><span class="sxs-lookup"><span data-stu-id="78502-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="78502-106">[in]要从其中获取的内存地址`ppData`。</span><span class="sxs-lookup"><span data-stu-id="78502-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="78502-107">[out]指向的大小，以字节为单位的`ppData`。</span><span class="sxs-lookup"><span data-stu-id="78502-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="78502-108">[out]检索到的二进制数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="78502-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78502-109">要求</span><span class="sxs-lookup"><span data-stu-id="78502-109">Requirements</span></span>  
 <span data-ttu-id="78502-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78502-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78502-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="78502-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78502-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="78502-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78502-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78502-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78502-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="78502-114">See also</span></span>
- [<span data-ttu-id="78502-115">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="78502-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="78502-116">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="78502-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
