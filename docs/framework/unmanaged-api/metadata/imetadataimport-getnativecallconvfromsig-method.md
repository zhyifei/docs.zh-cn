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
ms.openlocfilehash: 963d46aea4ab31e770cb845fe699208f6c8f9ac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447235"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="3c3a4-102">IMetaDataImport::GetNativeCallConvFromSig 方法</span><span class="sxs-lookup"><span data-stu-id="3c3a4-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="3c3a4-103">获取指定的签名指针所表示的方法的本机调用约定。</span><span class="sxs-lookup"><span data-stu-id="3c3a4-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c3a4-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c3a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c3a4-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="3c3a4-106">[in]指向要返回的调用约定的方法的元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="3c3a4-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="3c3a4-107">[in]以字节为单位的大小`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="3c3a4-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="3c3a4-108">[out]指向的本机调用约定的指针。</span><span class="sxs-lookup"><span data-stu-id="3c3a4-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3a4-109">要求</span><span class="sxs-lookup"><span data-stu-id="3c3a4-109">Requirements</span></span>  
 <span data-ttu-id="3c3a4-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c3a4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3a4-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c3a4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c3a4-112">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3c3a4-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c3a4-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3a4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c3a4-114">See Also</span></span>  
 <xref:System.Runtime.InteropServices.CallingConvention>  
 [<span data-ttu-id="3c3a4-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3c3a4-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3c3a4-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3c3a4-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
