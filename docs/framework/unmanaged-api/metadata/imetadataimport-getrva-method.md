---
title: IMetaDataImport::GetRVA 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177218"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="a8972-102">IMetaDataImport::GetRVA 方法</span><span class="sxs-lookup"><span data-stu-id="a8972-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="a8972-103">获取由指定令牌表示的方法或字段的相对虚拟地址 （RVA） 和实现标志。</span><span class="sxs-lookup"><span data-stu-id="a8972-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8972-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8972-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8972-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a8972-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a8972-106">[在]表示要返回 RVA 的代码对象的 MethodDef 或 FieldDef 元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="a8972-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="a8972-107">如果令牌是 FieldDef，则该字段必须是全局变量。</span><span class="sxs-lookup"><span data-stu-id="a8972-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="a8972-108">[出]指向令牌表示的代码对象的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a8972-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="a8972-109">[出]指向方法的实现标志的指针。</span><span class="sxs-lookup"><span data-stu-id="a8972-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="a8972-110">此值是[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举中的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a8972-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="a8972-111">仅当 是`pdwImplFlags`MethodDef`tk`令牌时，值才有效。</span><span class="sxs-lookup"><span data-stu-id="a8972-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8972-112">要求</span><span class="sxs-lookup"><span data-stu-id="a8972-112">Requirements</span></span>  
 <span data-ttu-id="a8972-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8972-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8972-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a8972-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8972-115">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="a8972-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8972-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8972-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8972-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8972-117">See also</span></span>

- [<span data-ttu-id="a8972-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a8972-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a8972-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a8972-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
