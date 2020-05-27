---
title: IMetaDataDispenserEx 接口
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 96f0c0c254ce255581ac2937c805096918ab29e8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008048"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="de489-102">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="de489-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="de489-103">扩展[IMetaDataDispenser 接口](imetadatadispenser-interface.md)接口，以提供控制元数据 api 对当前元数据范围的操作方式的功能。</span><span class="sxs-lookup"><span data-stu-id="de489-103">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de489-104">方法</span><span class="sxs-lookup"><span data-stu-id="de489-104">Methods</span></span>  
  
|<span data-ttu-id="de489-105">方法</span><span class="sxs-lookup"><span data-stu-id="de489-105">Method</span></span>|<span data-ttu-id="de489-106">说明</span><span class="sxs-lookup"><span data-stu-id="de489-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de489-107">FindAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="de489-107">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="de489-108">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="de489-108">This method is not implemented.</span></span> <span data-ttu-id="de489-109">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="de489-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="de489-110">FindAssemblyModule 方法</span><span class="sxs-lookup"><span data-stu-id="de489-110">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="de489-111">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="de489-111">This method is not implemented.</span></span> <span data-ttu-id="de489-112">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="de489-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="de489-113">GetCORSystemDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="de489-113">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="de489-114">获取保存当前公共语言运行时（CLR）的目录。</span><span class="sxs-lookup"><span data-stu-id="de489-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="de489-115">此方法仅支持在进程外调试器中使用。</span><span class="sxs-lookup"><span data-stu-id="de489-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="de489-116">如果从另一个组件调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="de489-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="de489-117">GetOption 方法</span><span class="sxs-lookup"><span data-stu-id="de489-117">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="de489-118">为当前元数据范围获取指定选项的值。</span><span class="sxs-lookup"><span data-stu-id="de489-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="de489-119">选项控制如何处理对当前元数据范围的调用。</span><span class="sxs-lookup"><span data-stu-id="de489-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="de489-120">OpenScopeOnITypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="de489-120">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="de489-121">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="de489-121">This method is not implemented.</span></span> <span data-ttu-id="de489-122">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="de489-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="de489-123">SetOption 方法</span><span class="sxs-lookup"><span data-stu-id="de489-123">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="de489-124">为当前元数据范围将指定的选项设置为给定的值。</span><span class="sxs-lookup"><span data-stu-id="de489-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="de489-125">选项控制如何处理对当前元数据范围的调用。</span><span class="sxs-lookup"><span data-stu-id="de489-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de489-126">要求</span><span class="sxs-lookup"><span data-stu-id="de489-126">Requirements</span></span>  
 <span data-ttu-id="de489-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de489-127">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de489-128">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="de489-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de489-129">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="de489-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de489-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de489-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de489-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de489-131">See also</span></span>

- [<span data-ttu-id="de489-132">元数据接口</span><span class="sxs-lookup"><span data-stu-id="de489-132">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="de489-133">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="de489-133">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="de489-134">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="de489-134">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="de489-135">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="de489-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
