---
title: "IMetaDataEmit::DefineMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fa136f5e6669e58ef709db5b53f538804cfcac2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="aea59-102">IMetaDataEmit::DefineMethod 方法</span><span class="sxs-lookup"><span data-stu-id="aea59-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="aea59-103">创建一个定义为方法或全局函数使用指定的签名，并将令牌返回到该方法定义。</span><span class="sxs-lookup"><span data-stu-id="aea59-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea59-104">语法</span><span class="sxs-lookup"><span data-stu-id="aea59-104">Syntax</span></span>  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aea59-105">参数</span><span class="sxs-lookup"><span data-stu-id="aea59-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="aea59-106">[in]`mdTypedef`令牌的父类或父接口的方法。</span><span class="sxs-lookup"><span data-stu-id="aea59-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="aea59-107">设置`td`到`mdTokenNil`，如果你正在定义的全局函数。</span><span class="sxs-lookup"><span data-stu-id="aea59-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="aea59-108">[in]Unicode 中的成员名称。</span><span class="sxs-lookup"><span data-stu-id="aea59-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="aea59-109">[in]值为[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)指定方法或全局函数的特性的枚举。</span><span class="sxs-lookup"><span data-stu-id="aea59-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="aea59-110">[in]方法签名中。</span><span class="sxs-lookup"><span data-stu-id="aea59-110">[in] The method signature.</span></span> <span data-ttu-id="aea59-111">作为提供，并会保持签名。</span><span class="sxs-lookup"><span data-stu-id="aea59-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="aea59-112">如果你需要指定任何参数的其他信息，使用[imetadataemit:: Setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="aea59-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="aea59-113">[in]中的字节计数`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="aea59-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="aea59-114">[in]代码的地址。</span><span class="sxs-lookup"><span data-stu-id="aea59-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="aea59-115">[in]值为[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举，指定方法实现功能。</span><span class="sxs-lookup"><span data-stu-id="aea59-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="aea59-116">[out]成员标记中。</span><span class="sxs-lookup"><span data-stu-id="aea59-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aea59-117">备注</span><span class="sxs-lookup"><span data-stu-id="aea59-117">Remarks</span></span>  
 <span data-ttu-id="aea59-118">元数据 API 保证为给定的封闭类或接口，在中指定的调用方发出它们按保留相同的顺序中的方法`td`参数。</span><span class="sxs-lookup"><span data-stu-id="aea59-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="aea59-119">有关使用的其他信息`DefineMethod`和特定的参数设置如下所示。</span><span class="sxs-lookup"><span data-stu-id="aea59-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="aea59-120">V-表中的槽</span><span class="sxs-lookup"><span data-stu-id="aea59-120">Slots in the V-table</span></span>  
 <span data-ttu-id="aea59-121">运行时使用方法定义来设置 v-表槽。</span><span class="sxs-lookup"><span data-stu-id="aea59-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="aea59-122">在一个或多个槽需要已跳过，例如用于这种情况并保留有一个 COM 接口布局，奇偶校验 dummy 方法定义以占用槽或 v-表; 中的槽设置`dwMethodFlags`到`mdRTSpecialName`值[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举和将名称指定为：</span><span class="sxs-lookup"><span data-stu-id="aea59-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="aea59-123">_VtblGap\<*SequenceNumber*>\<\_*槽数*></span><span class="sxs-lookup"><span data-stu-id="aea59-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>  
  
 <span data-ttu-id="aea59-124">其中*SequenceNumber*是方法的序列号和*槽数*是要跳过 v-表中的槽数。</span><span class="sxs-lookup"><span data-stu-id="aea59-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="aea59-125">如果*槽数*是省略，则假定为 1。</span><span class="sxs-lookup"><span data-stu-id="aea59-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="aea59-126">这些虚拟方法不是可从托管或非托管代码调用，并从托管或非托管代码中调用它们的任何尝试生成异常。</span><span class="sxs-lookup"><span data-stu-id="aea59-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="aea59-127">它们的唯一用途是将会占用空间运行时为 COM 集成生成 v-表中。</span><span class="sxs-lookup"><span data-stu-id="aea59-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="aea59-128">重复的方法</span><span class="sxs-lookup"><span data-stu-id="aea59-128">Duplicate Methods</span></span>  
 <span data-ttu-id="aea59-129">不应定义重复的方法。</span><span class="sxs-lookup"><span data-stu-id="aea59-129">You should not define duplicate methods.</span></span> <span data-ttu-id="aea59-130">也就是说，不应调用`DefineMethod`重复的一组值中使用`td`， `wzName`，和`pvSig`参数。</span><span class="sxs-lookup"><span data-stu-id="aea59-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="aea59-131">(这三个参数组合在一起唯一定义的方法。)。</span><span class="sxs-lookup"><span data-stu-id="aea59-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="aea59-132">但是，可以使用重复三元组，前提是，对于一种方法定义中，你设置`mdPrivateScope`中位`dwMethodFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="aea59-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="aea59-133">(`mdPrivateScope`位意味着编译器将发出对此方法定义的引用。)</span><span class="sxs-lookup"><span data-stu-id="aea59-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="aea59-134">方法的实现信息</span><span class="sxs-lookup"><span data-stu-id="aea59-134">Method Implementation Information</span></span>  
 <span data-ttu-id="aea59-135">在声明的方法时通常不知道有关方法的实现的信息。</span><span class="sxs-lookup"><span data-stu-id="aea59-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="aea59-136">因此，不需要传递中的值`ulCodeRVA`和`dwImplFlags`参数调用时`DefineMethod`。</span><span class="sxs-lookup"><span data-stu-id="aea59-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="aea59-137">可以通过更高版本提供值[imetadataemit:: Setmethodimplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)或[imetadataemit:: Setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)适当。</span><span class="sxs-lookup"><span data-stu-id="aea59-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="aea59-138">在某些情况下，如平台调用 (PInvoke) 或 COM 互操作方案中，未将提供方法体，和`ulCodeRVA`应设置为零。</span><span class="sxs-lookup"><span data-stu-id="aea59-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="aea59-139">在这些情况下，该方法不应被标记为抽象，因为运行时将查找其实现。</span><span class="sxs-lookup"><span data-stu-id="aea59-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="aea59-140">为 PInvoke 定义方法</span><span class="sxs-lookup"><span data-stu-id="aea59-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="aea59-141">对于每个要通过 PInvoke 调用的非托管函数，必须定义表示目标的非托管函数的托管的方法。</span><span class="sxs-lookup"><span data-stu-id="aea59-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="aea59-142">若要定义的托管的方法，使用`DefineMethod`一些设置为特定值，具体取决于在其中使用 PInvoke 的方法的参数：</span><span class="sxs-lookup"><span data-stu-id="aea59-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
-   <span data-ttu-id="aea59-143">True PInvoke-涉及驻留在非托管 DLL 的外部的非托管方法的调用。</span><span class="sxs-lookup"><span data-stu-id="aea59-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
-   <span data-ttu-id="aea59-144">本地 PInvoke — 涉及在当前的托管模块中嵌入的本机非托管方法的调用。</span><span class="sxs-lookup"><span data-stu-id="aea59-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="aea59-145">下表中提供的参数设置。</span><span class="sxs-lookup"><span data-stu-id="aea59-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="aea59-146">参数</span><span class="sxs-lookup"><span data-stu-id="aea59-146">Parameter</span></span>|<span data-ttu-id="aea59-147">值 true PInvoke</span><span class="sxs-lookup"><span data-stu-id="aea59-147">Values for true PInvoke</span></span>|<span data-ttu-id="aea59-148">本地 PInvoke 值</span><span class="sxs-lookup"><span data-stu-id="aea59-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="aea59-149">设置`mdStatic`; 清除`mdSynchronized`和`mdAbstract`。</span><span class="sxs-lookup"><span data-stu-id="aea59-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="aea59-150">一个有效的公共语言运行时 (CLR) 方法签名，其参数属于有效的托管类型。</span><span class="sxs-lookup"><span data-stu-id="aea59-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="aea59-151">一个有效的 CLR 方法签名，其有效的参数的托管类型。</span><span class="sxs-lookup"><span data-stu-id="aea59-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="aea59-152">0</span><span class="sxs-lookup"><span data-stu-id="aea59-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="aea59-153">设置`miCil`和`miManaged`。</span><span class="sxs-lookup"><span data-stu-id="aea59-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="aea59-154">设置`miNative`和`miUnmanaged`。</span><span class="sxs-lookup"><span data-stu-id="aea59-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aea59-155">惠?</span><span class="sxs-lookup"><span data-stu-id="aea59-155">Requirements</span></span>  
 <span data-ttu-id="aea59-156">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aea59-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aea59-157">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aea59-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aea59-158">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="aea59-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aea59-159">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aea59-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea59-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="aea59-160">See Also</span></span>  
 [<span data-ttu-id="aea59-161">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="aea59-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="aea59-162">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="aea59-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
