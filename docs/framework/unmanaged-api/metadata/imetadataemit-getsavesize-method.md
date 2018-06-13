---
title: IMetaDataEmit::GetSaveSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9a65f76aed00e2b848f8603f1fee4d6acc91f99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449152"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="324ce-102">IMetaDataEmit::GetSaveSize 方法</span><span class="sxs-lookup"><span data-stu-id="324ce-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="324ce-103">获取当前范围内的程序集和其元数据的估计二进制大小。</span><span class="sxs-lookup"><span data-stu-id="324ce-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="324ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="324ce-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="324ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="324ce-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="324ce-106">[in]值为[CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)枚举，它指定是否获取的准确或近似大小。</span><span class="sxs-lookup"><span data-stu-id="324ce-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="324ce-107">只有三个值都无效： cssAccurate，cssQuick，和 cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="324ce-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="324ce-108">cssAccurate 返回准确的存储大小，但需要更长的计算。</span><span class="sxs-lookup"><span data-stu-id="324ce-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="324ce-109">cssQuick 返回的大小，为安全起见，填充，但需要更少时间来计算。</span><span class="sxs-lookup"><span data-stu-id="324ce-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="324ce-110">cssDiscardTransientCAs 告知`GetSaveSize`，它可以抛弃可丢弃的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="324ce-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="324ce-111">[out]指向保存该文件所需的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="324ce-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="324ce-112">备注</span><span class="sxs-lookup"><span data-stu-id="324ce-112">Remarks</span></span>  
 <span data-ttu-id="324ce-113">`GetSaveSize` 计算所需的空间，以字节为单位，以保存在当前范围内的程序集和所有元数据。</span><span class="sxs-lookup"><span data-stu-id="324ce-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="324ce-114">(调用[imetadataemit:: Savetostream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)方法将发出此数目的字节。)</span><span class="sxs-lookup"><span data-stu-id="324ce-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="324ce-115">如果调用方实现[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)接口 (通过[imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)或[imetadataemit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md))，`GetSaveSize`将执行两个周期通过优化并压缩的元数据。</span><span class="sxs-lookup"><span data-stu-id="324ce-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="324ce-116">否则，不执行任何优化。</span><span class="sxs-lookup"><span data-stu-id="324ce-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="324ce-117">如果执行优化，则第一次传递只需进行排序的元数据结构调整导入时搜索的性能。</span><span class="sxs-lookup"><span data-stu-id="324ce-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="324ce-118">此步骤通常会导致移动解决问题，并且保留供将来参考工具的令牌将会失效其副作用的记录。</span><span class="sxs-lookup"><span data-stu-id="324ce-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="324ce-119">元数据不会通知这些令牌更改之前的调用方后的第二个过程，但是。</span><span class="sxs-lookup"><span data-stu-id="324ce-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="324ce-120">第二个阶段中，在各种优化来执行旨在减少将元数据，如优化去除 （早期绑定） 的总体大小`mdTypeRef`和`mdMemberRef`令牌时则引用为的类型或声明中的成员当前的元数据范围。</span><span class="sxs-lookup"><span data-stu-id="324ce-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="324ce-121">在此阶段中，会发生令牌映射的另一轮。</span><span class="sxs-lookup"><span data-stu-id="324ce-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="324ce-122">在后此阶段中，元数据引擎通知调用方，通过其`IMapToken`接口的任何更改令牌值。</span><span class="sxs-lookup"><span data-stu-id="324ce-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="324ce-123">要求</span><span class="sxs-lookup"><span data-stu-id="324ce-123">Requirements</span></span>  
 <span data-ttu-id="324ce-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="324ce-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="324ce-125">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="324ce-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="324ce-126">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="324ce-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="324ce-127">**.NET framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="324ce-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="324ce-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="324ce-128">See Also</span></span>  
 [<span data-ttu-id="324ce-129">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="324ce-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="324ce-130">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="324ce-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
