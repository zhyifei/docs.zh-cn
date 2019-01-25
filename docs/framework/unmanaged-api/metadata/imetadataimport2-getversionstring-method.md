---
title: IMetaDataImport2::GetVersionString 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e041efed929255d4ce3af2d051a391bc4179cda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630913"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="6edcb-102">IMetaDataImport2::GetVersionString 方法</span><span class="sxs-lookup"><span data-stu-id="6edcb-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="6edcb-103">获取用于生成程序集的运行时的版本号。</span><span class="sxs-lookup"><span data-stu-id="6edcb-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6edcb-104">语法</span><span class="sxs-lookup"><span data-stu-id="6edcb-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6edcb-105">参数</span><span class="sxs-lookup"><span data-stu-id="6edcb-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="6edcb-106">[out]用于存储指定的版本字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="6edcb-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="6edcb-107">[in]大小，以宽字符为单位的`pwzBuf`数组。</span><span class="sxs-lookup"><span data-stu-id="6edcb-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="6edcb-108">[out]中包括 null 终止符的宽字符数返回`pwzBuf`数组。</span><span class="sxs-lookup"><span data-stu-id="6edcb-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6edcb-109">备注</span><span class="sxs-lookup"><span data-stu-id="6edcb-109">Remarks</span></span>  
 <span data-ttu-id="6edcb-110">`GetVersionString`方法获取当前元数据范围的生成目标版本。</span><span class="sxs-lookup"><span data-stu-id="6edcb-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="6edcb-111">如果从未保存过作用域，它不会生成目标版本，并将返回空字符串。</span><span class="sxs-lookup"><span data-stu-id="6edcb-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6edcb-112">要求</span><span class="sxs-lookup"><span data-stu-id="6edcb-112">Requirements</span></span>  
 <span data-ttu-id="6edcb-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6edcb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6edcb-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6edcb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6edcb-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6edcb-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6edcb-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6edcb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6edcb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6edcb-117">See also</span></span>
- [<span data-ttu-id="6edcb-118">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="6edcb-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="6edcb-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6edcb-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
