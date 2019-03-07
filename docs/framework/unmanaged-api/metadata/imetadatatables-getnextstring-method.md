---
title: IMetaDataTables::GetNextString 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b057b0537bbeff7433b776e64456ccc810cee54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473482"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="a6607-102">IMetaDataTables::GetNextString 方法</span><span class="sxs-lookup"><span data-stu-id="a6607-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="a6607-103">获取当前表的列中的下一个字符串的索引。</span><span class="sxs-lookup"><span data-stu-id="a6607-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6607-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6607-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6607-105">参数</span><span class="sxs-lookup"><span data-stu-id="a6607-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="a6607-106">[in]从字符串表的列索引值。</span><span class="sxs-lookup"><span data-stu-id="a6607-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="a6607-107">[out]索引列中的下一个字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="a6607-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6607-108">要求</span><span class="sxs-lookup"><span data-stu-id="a6607-108">Requirements</span></span>  
 <span data-ttu-id="a6607-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6607-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6607-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a6607-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6607-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a6607-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6607-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6607-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6607-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6607-113">See also</span></span>
- [<span data-ttu-id="a6607-114">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="a6607-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="a6607-115">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="a6607-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
