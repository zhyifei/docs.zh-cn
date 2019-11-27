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
ms.openlocfilehash: da9a13a3dea34f6681f47e95c5b352a710d7458b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431217"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="8a544-102">IMetaDataDispenserEx::GetCORSystemDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="8a544-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="8a544-103">获取保存当前公共语言运行时（CLR）的目录。</span><span class="sxs-lookup"><span data-stu-id="8a544-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="8a544-104">此方法仅支持在进程外调试器中使用。</span><span class="sxs-lookup"><span data-stu-id="8a544-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="8a544-105">如果从另一个组件调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="8a544-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a544-106">语法</span><span class="sxs-lookup"><span data-stu-id="8a544-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a544-107">参数</span><span class="sxs-lookup"><span data-stu-id="8a544-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="8a544-108">弄要接收目录名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8a544-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="8a544-109">中`szBuffer`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8a544-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="8a544-110">弄`szBuffer`中实际返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="8a544-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a544-111">要求</span><span class="sxs-lookup"><span data-stu-id="8a544-111">Requirements</span></span>  
 <span data-ttu-id="8a544-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a544-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a544-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8a544-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a544-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8a544-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a544-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a544-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a544-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a544-116">See also</span></span>

- [<span data-ttu-id="8a544-117">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="8a544-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="8a544-118">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="8a544-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
