---
title: IMetaDataEmit2::DefineMethodSpec 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: 7547d7557169b1279125141afb5b05e22341942a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432741"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="f6adf-102">IMetaDataEmit2::DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="f6adf-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="f6adf-103">创建方法的泛型实例，并获取定义的标记。</span><span class="sxs-lookup"><span data-stu-id="f6adf-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6adf-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6adf-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6adf-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6adf-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="f6adf-106">中创建泛型实例的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="f6adf-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="f6adf-107">令牌必须是 `mdMethodDef` 或 `mdMemberRef`类型。</span><span class="sxs-lookup"><span data-stu-id="f6adf-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f6adf-108">中指向方法的二进制 COM + 签名的指针。</span><span class="sxs-lookup"><span data-stu-id="f6adf-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="f6adf-109">中`pvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f6adf-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="f6adf-110">弄方法的元数据签名定义的标记。</span><span class="sxs-lookup"><span data-stu-id="f6adf-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6adf-111">要求</span><span class="sxs-lookup"><span data-stu-id="f6adf-111">Requirements</span></span>  
 <span data-ttu-id="f6adf-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6adf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6adf-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f6adf-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6adf-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f6adf-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6adf-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6adf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6adf-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6adf-116">See also</span></span>

- [<span data-ttu-id="f6adf-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f6adf-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="f6adf-118">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f6adf-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
