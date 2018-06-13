---
title: IMetaDataDispenserEx::GetCORSystemDirectory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf580f6d3fb18e729f3eca300aa817036eb61e4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443425"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="9afec-102">IMetaDataDispenserEx::GetCORSystemDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="9afec-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="9afec-103">获取包含当前的公共语言运行时 (CLR) 的目录。</span><span class="sxs-lookup"><span data-stu-id="9afec-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="9afec-104">进程外调试器支持此方法仅供使用。</span><span class="sxs-lookup"><span data-stu-id="9afec-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="9afec-105">如果从另一个组件调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="9afec-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9afec-106">语法</span><span class="sxs-lookup"><span data-stu-id="9afec-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9afec-107">参数</span><span class="sxs-lookup"><span data-stu-id="9afec-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="9afec-108">[out]要接收的目录名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9afec-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9afec-109">[in]大小，以字节为单位的`szBuffer`。</span><span class="sxs-lookup"><span data-stu-id="9afec-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="9afec-110">[out]中实际返回的字节数`szBuffer`。</span><span class="sxs-lookup"><span data-stu-id="9afec-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9afec-111">要求</span><span class="sxs-lookup"><span data-stu-id="9afec-111">Requirements</span></span>  
 <span data-ttu-id="9afec-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9afec-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9afec-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9afec-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9afec-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9afec-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9afec-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9afec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9afec-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9afec-116">See Also</span></span>  
 [<span data-ttu-id="9afec-117">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="9afec-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="9afec-118">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="9afec-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
