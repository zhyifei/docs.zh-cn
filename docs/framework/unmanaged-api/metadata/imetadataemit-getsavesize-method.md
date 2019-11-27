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
ms.openlocfilehash: 125a63638a41707b8eed918253cb1f93abb907eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434336"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="f3be5-102">IMetaDataEmit::GetSaveSize 方法</span><span class="sxs-lookup"><span data-stu-id="f3be5-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="f3be5-103">获取当前范围内的程序集和它的元数据的预计二进制大小。</span><span class="sxs-lookup"><span data-stu-id="f3be5-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3be5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3be5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3be5-105">参数</span><span class="sxs-lookup"><span data-stu-id="f3be5-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="f3be5-106">中[CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)枚举的一个值，该值指定是获取准确大小还是近似大小。</span><span class="sxs-lookup"><span data-stu-id="f3be5-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="f3be5-107">只有三个值有效： cssAccurate、cssQuick 和 cssDiscardTransientCAs：</span><span class="sxs-lookup"><span data-stu-id="f3be5-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="f3be5-108">cssAccurate 返回准确的保存大小，但需要更长的时间来计算。</span><span class="sxs-lookup"><span data-stu-id="f3be5-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="f3be5-109">cssQuick 返回大小，为安全起见，但计算时间较少。</span><span class="sxs-lookup"><span data-stu-id="f3be5-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="f3be5-110">cssDiscardTransientCAs 告知 `GetSaveSize` 它可以丢弃可放弃的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="f3be5-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="f3be5-111">弄一个指针，指向保存该文件所需的大小。</span><span class="sxs-lookup"><span data-stu-id="f3be5-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3be5-112">备注</span><span class="sxs-lookup"><span data-stu-id="f3be5-112">Remarks</span></span>  
 <span data-ttu-id="f3be5-113">`GetSaveSize` 计算在当前作用域中保存程序集及其所有元数据所需的空间（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f3be5-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="f3be5-114">（对[IMetaDataEmit：： SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)方法的调用将发出此数目的字节。）</span><span class="sxs-lookup"><span data-stu-id="f3be5-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="f3be5-115">如果调用方实现了[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)接口（通过[IMetaDataEmit：： SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)或[IMetaDataEmit：： Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)），`GetSaveSize` 将对元数据执行两次传递以对其进行优化和压缩。</span><span class="sxs-lookup"><span data-stu-id="f3be5-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="f3be5-116">否则，不执行任何优化。</span><span class="sxs-lookup"><span data-stu-id="f3be5-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="f3be5-117">如果执行了优化，则第一个传递将只对元数据结构进行排序，以优化导入时间搜索的性能。</span><span class="sxs-lookup"><span data-stu-id="f3be5-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="f3be5-118">此步骤通常会导致四处移动记录，并产生副作用，由工具保留的标记将会失效。</span><span class="sxs-lookup"><span data-stu-id="f3be5-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="f3be5-119">但是，在第二次传递后，元数据不会将这些令牌更改通知给调用方。</span><span class="sxs-lookup"><span data-stu-id="f3be5-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="f3be5-120">在第二次传递中，将执行各种优化，以减少元数据的总大小，例如，在引用到在当前元数据范围内声明的类型或成员时，`mdTypeRef` 和 `mdMemberRef` 令牌进行优化。</span><span class="sxs-lookup"><span data-stu-id="f3be5-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="f3be5-121">在此阶段中，会发生另一轮标记映射。</span><span class="sxs-lookup"><span data-stu-id="f3be5-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="f3be5-122">此次传递后，元数据引擎通过其 `IMapToken` 接口通知调用方所有已更改的令牌值。</span><span class="sxs-lookup"><span data-stu-id="f3be5-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3be5-123">要求</span><span class="sxs-lookup"><span data-stu-id="f3be5-123">Requirements</span></span>  
 <span data-ttu-id="f3be5-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3be5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3be5-125">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f3be5-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3be5-126">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f3be5-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3be5-127">**.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3be5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3be5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3be5-128">See also</span></span>

- [<span data-ttu-id="f3be5-129">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f3be5-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f3be5-130">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f3be5-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
