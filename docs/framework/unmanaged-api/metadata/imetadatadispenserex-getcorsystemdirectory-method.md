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
ms.openlocfilehash: fb673666543bea3df44005ee3b20d311524f51d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175910"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="5519f-102">IMetaDataDispenserEx::GetCORSystemDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="5519f-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="5519f-103">获取保存当前通用语言运行时 （CLR） 的目录。</span><span class="sxs-lookup"><span data-stu-id="5519f-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="5519f-104">此方法仅支持进程外调试器使用。</span><span class="sxs-lookup"><span data-stu-id="5519f-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="5519f-105">如果从其他组件调用，它将返回E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="5519f-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5519f-106">语法</span><span class="sxs-lookup"><span data-stu-id="5519f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5519f-107">parameters</span><span class="sxs-lookup"><span data-stu-id="5519f-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="5519f-108">[出]要接收目录名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5519f-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5519f-109">[在]的大小（以字节为单位）的大小`szBuffer`。</span><span class="sxs-lookup"><span data-stu-id="5519f-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="5519f-110">[出]在 中`szBuffer`实际返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="5519f-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5519f-111">要求</span><span class="sxs-lookup"><span data-stu-id="5519f-111">Requirements</span></span>  
 <span data-ttu-id="5519f-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5519f-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5519f-113">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="5519f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5519f-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5519f-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5519f-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5519f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5519f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5519f-116">See also</span></span>

- [<span data-ttu-id="5519f-117">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="5519f-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="5519f-118">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="5519f-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
