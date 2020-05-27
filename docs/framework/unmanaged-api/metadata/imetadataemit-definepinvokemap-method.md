---
title: IMetaDataEmit::DefinePinvokeMap 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: 447ec44ed3efc4eec84d1e4acd6f2ec1a730bf74
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008022"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="2c685-102">IMetaDataEmit::DefinePinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="2c685-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="2c685-103">设置指定的标记所引用的方法的 PInvoke 签名功能。</span><span class="sxs-lookup"><span data-stu-id="2c685-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c685-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c685-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c685-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c685-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2c685-106">中目标方法的标记。</span><span class="sxs-lookup"><span data-stu-id="2c685-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="2c685-107">中PInvoke 用来执行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="2c685-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="2c685-108">中非托管 DLL 中目标导出方法的名称。</span><span class="sxs-lookup"><span data-stu-id="2c685-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="2c685-109">中目标本机 DLL 的标记。</span><span class="sxs-lookup"><span data-stu-id="2c685-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c685-110">要求</span><span class="sxs-lookup"><span data-stu-id="2c685-110">Requirements</span></span>  
 <span data-ttu-id="2c685-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c685-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c685-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="2c685-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c685-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2c685-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c685-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c685-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c685-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c685-115">See also</span></span>

- [<span data-ttu-id="2c685-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="2c685-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2c685-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="2c685-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
