---
title: IMetaDataImport::GetNativeCallConvFromSig 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44b5dfb31cfe0364a745b729018be536f6be9aac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778965"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="67e99-102">IMetaDataImport::GetNativeCallConvFromSig 方法</span><span class="sxs-lookup"><span data-stu-id="67e99-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="67e99-103">获取指定的签名指针所表示的方法的本机调用约定。</span><span class="sxs-lookup"><span data-stu-id="67e99-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e99-104">语法</span><span class="sxs-lookup"><span data-stu-id="67e99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67e99-105">参数</span><span class="sxs-lookup"><span data-stu-id="67e99-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="67e99-106">[in]指向要返回的调用约定的方法的元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="67e99-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="67e99-107">[in]以字节为单位的大小`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="67e99-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="67e99-108">[out]一个指向本机调用约定。</span><span class="sxs-lookup"><span data-stu-id="67e99-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67e99-109">要求</span><span class="sxs-lookup"><span data-stu-id="67e99-109">Requirements</span></span>  
 <span data-ttu-id="67e99-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67e99-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e99-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67e99-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67e99-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="67e99-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67e99-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e99-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e99-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="67e99-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="67e99-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="67e99-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="67e99-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="67e99-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
