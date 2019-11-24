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
ms.openlocfilehash: 06ff6a1885a5e9bb819c2897aaf85e5c2b9b1147
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437243"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="c99c0-102">IMetaDataImport::GetNativeCallConvFromSig 方法</span><span class="sxs-lookup"><span data-stu-id="c99c0-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="c99c0-103">获取指定的签名指针所表示的方法的本机调用约定。</span><span class="sxs-lookup"><span data-stu-id="c99c0-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="c99c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c99c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="c99c0-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="c99c0-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span><span class="sxs-lookup"><span data-stu-id="c99c0-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="c99c0-107">[in] The size in bytes of `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="c99c0-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="c99c0-108">[out] A pointer to the native calling convention.</span><span class="sxs-lookup"><span data-stu-id="c99c0-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c99c0-109">要求</span><span class="sxs-lookup"><span data-stu-id="c99c0-109">Requirements</span></span>  
 <span data-ttu-id="c99c0-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c99c0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c99c0-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c99c0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c99c0-112">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c99c0-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c99c0-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c99c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99c0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c99c0-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="c99c0-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c99c0-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c99c0-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c99c0-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
