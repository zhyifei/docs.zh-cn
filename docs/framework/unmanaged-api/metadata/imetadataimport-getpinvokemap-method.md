---
title: IMetaDataImport::GetPinvokeMap 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: c458fef77b49f522ca21dd5487731f4d43588cea
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437095"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="d1190-102">IMetaDataImport::GetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="d1190-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="d1190-103">获取用于表示 PInvoke 调用的目标程序集的 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="d1190-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1190-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1190-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1190-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1190-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="d1190-106">中要为其获取 PInvoke 映射元数据的 FieldDef 或 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="d1190-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="d1190-107">弄一个指针，指向用于映射的标志。</span><span class="sxs-lookup"><span data-stu-id="d1190-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="d1190-108">此值是[CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md)枚举中的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d1190-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="d1190-109">弄非托管目标 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="d1190-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="d1190-110">中`szImportName`的大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="d1190-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="d1190-111">弄`szImportName`中返回的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="d1190-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="d1190-112">弄一个指针，指向表示非托管目标对象库的 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="d1190-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1190-113">要求</span><span class="sxs-lookup"><span data-stu-id="d1190-113">Requirements</span></span>  
 <span data-ttu-id="d1190-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1190-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1190-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="d1190-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1190-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d1190-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1190-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1190-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1190-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1190-118">See also</span></span>

- [<span data-ttu-id="d1190-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d1190-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d1190-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d1190-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
