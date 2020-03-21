---
title: IMetaDataEmit::DefineMethod 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177662"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="07c69-102">IMetaDataEmit::DefineMethod 方法</span><span class="sxs-lookup"><span data-stu-id="07c69-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="07c69-103">使用指定签名的方法或全局函数创建定义，并将令牌返回到该方法定义。</span><span class="sxs-lookup"><span data-stu-id="07c69-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c69-104">语法</span><span class="sxs-lookup"><span data-stu-id="07c69-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="07c69-105">parameters</span><span class="sxs-lookup"><span data-stu-id="07c69-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="07c69-106">[在]方法`mdTypedef`的父类或父接口的令牌。</span><span class="sxs-lookup"><span data-stu-id="07c69-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="07c69-107">如果要`td`定义`mdTokenNil`全局函数，则设置为 ，设置为 。。</span><span class="sxs-lookup"><span data-stu-id="07c69-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="07c69-108">[在]Unicode 中的成员名称。</span><span class="sxs-lookup"><span data-stu-id="07c69-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="07c69-109">[在][CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举的值，用于指定方法或全局函数的属性。</span><span class="sxs-lookup"><span data-stu-id="07c69-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="07c69-110">[在]方法签名。</span><span class="sxs-lookup"><span data-stu-id="07c69-110">[in] The method signature.</span></span> <span data-ttu-id="07c69-111">签名将保留为提供。</span><span class="sxs-lookup"><span data-stu-id="07c69-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="07c69-112">如果需要为任何参数指定其他信息，请使用[IMetaDataEmit：：setParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="07c69-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="07c69-113">[在]中的`pvSigBlob`字节计数。</span><span class="sxs-lookup"><span data-stu-id="07c69-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="07c69-114">[在]代码的地址。</span><span class="sxs-lookup"><span data-stu-id="07c69-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="07c69-115">[在][CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举的值，用于指定方法的实现特征。</span><span class="sxs-lookup"><span data-stu-id="07c69-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="07c69-116">[出]成员令牌。</span><span class="sxs-lookup"><span data-stu-id="07c69-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07c69-117">备注</span><span class="sxs-lookup"><span data-stu-id="07c69-117">Remarks</span></span>  
 <span data-ttu-id="07c69-118">元数据 API 保证以与调用方为给定的封闭类或接口发出方法的顺序保留方法，该类或接口在`td`参数中指定。</span><span class="sxs-lookup"><span data-stu-id="07c69-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="07c69-119">有关 使用`DefineMethod`和特定参数设置的其他信息，请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="07c69-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="07c69-120">V 表中的插槽</span><span class="sxs-lookup"><span data-stu-id="07c69-120">Slots in the V-table</span></span>  
 <span data-ttu-id="07c69-121">运行时使用方法定义来设置 v 表槽。</span><span class="sxs-lookup"><span data-stu-id="07c69-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="07c69-122">如果需要跳过一个或多个插槽（例如，使用 COM 接口布局保留奇偶校验），则定义虚拟方法以占用 v 表中的插槽或插槽;例如，使用 COM 接口布局保留奇偶校验，则使用虚拟方法占用 v-table 中的插槽或插槽。将`dwMethodFlags`设置为`mdRTSpecialName`[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举的值，并将名称指定为：</span><span class="sxs-lookup"><span data-stu-id="07c69-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="07c69-123">_VtblGap\<*序数*>\<*CountOfSlots*计数\_></span><span class="sxs-lookup"><span data-stu-id="07c69-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="07c69-124">*其中序列编号*是方法的序列号 *，CountOfSlots*是 v 表中要跳过的插槽数。</span><span class="sxs-lookup"><span data-stu-id="07c69-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="07c69-125">如果省略*了 CountOflots，* 则假定为 1。</span><span class="sxs-lookup"><span data-stu-id="07c69-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="07c69-126">这些虚拟方法不能从托管或非托管代码调用，任何尝试调用它们（从托管代码或非托管代码）都会生成异常。</span><span class="sxs-lookup"><span data-stu-id="07c69-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="07c69-127">它们的唯一目的是占用运行时为 COM 集成生成的 v 表中的空间。</span><span class="sxs-lookup"><span data-stu-id="07c69-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="07c69-128">重复方法</span><span class="sxs-lookup"><span data-stu-id="07c69-128">Duplicate Methods</span></span>  
 <span data-ttu-id="07c69-129">不应定义重复的方法。</span><span class="sxs-lookup"><span data-stu-id="07c69-129">You should not define duplicate methods.</span></span> <span data-ttu-id="07c69-130">`DefineMethod`也就是说，不应使用`td`中`wzName`重复的值集调用 ， 和`pvSig`参数。</span><span class="sxs-lookup"><span data-stu-id="07c69-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="07c69-131">（这三个参数一起唯一地定义方法。</span><span class="sxs-lookup"><span data-stu-id="07c69-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="07c69-132">但是，可以使用重复的三重，前提是，对于方法定义之一，可以在`mdPrivateScope``dwMethodFlags`参数中设置位。</span><span class="sxs-lookup"><span data-stu-id="07c69-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="07c69-133">（该`mdPrivateScope`位表示编译器不会发出对此方法定义的引用。</span><span class="sxs-lookup"><span data-stu-id="07c69-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="07c69-134">方法实现信息</span><span class="sxs-lookup"><span data-stu-id="07c69-134">Method Implementation Information</span></span>  
 <span data-ttu-id="07c69-135">在声明方法时，通常不知道有关方法实现的信息。</span><span class="sxs-lookup"><span data-stu-id="07c69-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="07c69-136">因此，调用 时不需要传递`ulCodeRVA`和`dwImplFlags`参数中的值。 `DefineMethod`</span><span class="sxs-lookup"><span data-stu-id="07c69-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="07c69-137">这些值稍后可以通过[IMetaDataEmit：：设置方法Implflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)或[IMetaDataEmit：：SetRVA，](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)视情况而定。</span><span class="sxs-lookup"><span data-stu-id="07c69-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="07c69-138">在某些情况下，如平台调用 （PInvoke） 或 COM 互通方案，将不会提供方法正文，并且`ulCodeRVA`应设置为零。</span><span class="sxs-lookup"><span data-stu-id="07c69-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="07c69-139">在这些情况下，方法不应标记为抽象，因为运行时将定位实现。</span><span class="sxs-lookup"><span data-stu-id="07c69-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="07c69-140">定义 PInvoke 的方法</span><span class="sxs-lookup"><span data-stu-id="07c69-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="07c69-141">要通过 PInvoke 调用每个非托管函数，必须定义表示目标非托管函数的托管方法。</span><span class="sxs-lookup"><span data-stu-id="07c69-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="07c69-142">要定义托管方法，请使用`DefineMethod`设置为特定值的某些参数，具体取决于 PInvoke 的使用方式：</span><span class="sxs-lookup"><span data-stu-id="07c69-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="07c69-143">True PInvoke - 涉及调用驻留在非托管 DLL 中的外部非托管方法。</span><span class="sxs-lookup"><span data-stu-id="07c69-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="07c69-144">本地 PInvoke - 涉及调用嵌入在当前托管模块中的本机非托管方法。</span><span class="sxs-lookup"><span data-stu-id="07c69-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="07c69-145">参数设置在下表中给出。</span><span class="sxs-lookup"><span data-stu-id="07c69-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="07c69-146">参数</span><span class="sxs-lookup"><span data-stu-id="07c69-146">Parameter</span></span>|<span data-ttu-id="07c69-147">真实 PInvoke 的值</span><span class="sxs-lookup"><span data-stu-id="07c69-147">Values for true PInvoke</span></span>|<span data-ttu-id="07c69-148">本地 PInvoke 的值</span><span class="sxs-lookup"><span data-stu-id="07c69-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="07c69-149">设置`mdStatic`;清楚`mdSynchronized`和`mdAbstract`。</span><span class="sxs-lookup"><span data-stu-id="07c69-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="07c69-150">有效的通用语言运行时 （CLR） 方法签名，具有有效的托管类型的参数。</span><span class="sxs-lookup"><span data-stu-id="07c69-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="07c69-151">具有有效托管类型的参数的有效 CLR 方法签名。</span><span class="sxs-lookup"><span data-stu-id="07c69-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="07c69-152">0</span><span class="sxs-lookup"><span data-stu-id="07c69-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="07c69-153">设置 `miCil` 和 `miManaged`。</span><span class="sxs-lookup"><span data-stu-id="07c69-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="07c69-154">设置 `miNative` 和 `miUnmanaged`。</span><span class="sxs-lookup"><span data-stu-id="07c69-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07c69-155">要求</span><span class="sxs-lookup"><span data-stu-id="07c69-155">Requirements</span></span>  
 <span data-ttu-id="07c69-156">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07c69-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07c69-157">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="07c69-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07c69-158">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="07c69-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07c69-159">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07c69-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c69-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07c69-160">See also</span></span>

- [<span data-ttu-id="07c69-161">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="07c69-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="07c69-162">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="07c69-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
