---
title: IMetaDataTables::GetColumnInfo 方法
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177124"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="5b2da-102">IMetaDataTables::GetColumnInfo 方法</span><span class="sxs-lookup"><span data-stu-id="5b2da-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="5b2da-103">获取有关指定表中指定列的数据。</span><span class="sxs-lookup"><span data-stu-id="5b2da-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b2da-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b2da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b2da-105">parameters</span><span class="sxs-lookup"><span data-stu-id="5b2da-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="5b2da-106">[在]所需表的索引。</span><span class="sxs-lookup"><span data-stu-id="5b2da-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="5b2da-107">[在]所需列的索引。</span><span class="sxs-lookup"><span data-stu-id="5b2da-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="5b2da-108">[出]指向行中列偏移的指针。</span><span class="sxs-lookup"><span data-stu-id="5b2da-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="5b2da-109">[出]指向列的大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="5b2da-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="5b2da-110">[出]指向列中值类型的指针。</span><span class="sxs-lookup"><span data-stu-id="5b2da-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="5b2da-111">[出]指向列名称的指针。</span><span class="sxs-lookup"><span data-stu-id="5b2da-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="5b2da-112">备注</span><span class="sxs-lookup"><span data-stu-id="5b2da-112">Remarks</span></span>

<span data-ttu-id="5b2da-113">返回的列类型在值范围内：</span><span class="sxs-lookup"><span data-stu-id="5b2da-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="5b2da-114">p类型</span><span class="sxs-lookup"><span data-stu-id="5b2da-114">pType</span></span>                    | <span data-ttu-id="5b2da-115">说明</span><span class="sxs-lookup"><span data-stu-id="5b2da-115">Description</span></span>   | <span data-ttu-id="5b2da-116">帮助器功能</span><span class="sxs-lookup"><span data-stu-id="5b2da-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="5b2da-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="5b2da-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="5b2da-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="5b2da-118">(0..63)</span></span>   | <span data-ttu-id="5b2da-119">摆脱</span><span class="sxs-lookup"><span data-stu-id="5b2da-119">Rid</span></span>           | <span data-ttu-id="5b2da-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="5b2da-120">**IsRidType**</span></span><br><span data-ttu-id="5b2da-121">**IsRidorToken**</span><span class="sxs-lookup"><span data-stu-id="5b2da-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="5b2da-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="5b2da-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="5b2da-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="5b2da-123">(64..95)</span></span> | <span data-ttu-id="5b2da-124">编码令牌</span><span class="sxs-lookup"><span data-stu-id="5b2da-124">Coded token</span></span> | <span data-ttu-id="5b2da-125">**已编码令牌类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="5b2da-126">**IsRidorToken**</span><span class="sxs-lookup"><span data-stu-id="5b2da-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="5b2da-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="5b2da-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="5b2da-128">Int16</span><span class="sxs-lookup"><span data-stu-id="5b2da-128">Int16</span></span>         | <span data-ttu-id="5b2da-129">**固定类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="5b2da-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="5b2da-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="5b2da-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="5b2da-131">UInt16</span></span>        | <span data-ttu-id="5b2da-132">**固定类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="5b2da-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="5b2da-133">`iLONG` (98)</span></span>             | <span data-ttu-id="5b2da-134">Int32</span><span class="sxs-lookup"><span data-stu-id="5b2da-134">Int32</span></span>         | <span data-ttu-id="5b2da-135">**固定类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="5b2da-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="5b2da-136">`iULONG` (99)</span></span>            | <span data-ttu-id="5b2da-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="5b2da-137">UInt32</span></span>        | <span data-ttu-id="5b2da-138">**固定类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="5b2da-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="5b2da-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="5b2da-140">Byte</span><span class="sxs-lookup"><span data-stu-id="5b2da-140">Byte</span></span>          | <span data-ttu-id="5b2da-141">**固定类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="5b2da-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="5b2da-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="5b2da-143">String</span><span class="sxs-lookup"><span data-stu-id="5b2da-143">String</span></span>        | <span data-ttu-id="5b2da-144">**IsHeap 类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="5b2da-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="5b2da-145">`iGUID` (102)</span></span>            | <span data-ttu-id="5b2da-146">Guid</span><span class="sxs-lookup"><span data-stu-id="5b2da-146">Guid</span></span>          | <span data-ttu-id="5b2da-147">**IsHeap 类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="5b2da-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="5b2da-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="5b2da-149">Blob</span><span class="sxs-lookup"><span data-stu-id="5b2da-149">Blob</span></span>          | <span data-ttu-id="5b2da-150">**IsHeap 类型**</span><span class="sxs-lookup"><span data-stu-id="5b2da-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="5b2da-151">可以使用以下方式读取堆中存储*的值（即* `IsHeapType == true`），</span><span class="sxs-lookup"><span data-stu-id="5b2da-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="5b2da-152">`iSTRING`**：IMetadatatables.GetString**</span><span class="sxs-lookup"><span data-stu-id="5b2da-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="5b2da-153">`iGUID`**：IMetadatatables.GetGUID**</span><span class="sxs-lookup"><span data-stu-id="5b2da-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="5b2da-154">`iBLOB`**：IMetadatatables.获取Blob**</span><span class="sxs-lookup"><span data-stu-id="5b2da-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b2da-155">要使用上表中定义的常量，请包括`#define _DEFINE_META_DATA_META_CONSTANTS`*cor.h*标头文件提供的指令。</span><span class="sxs-lookup"><span data-stu-id="5b2da-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b2da-156">要求</span><span class="sxs-lookup"><span data-stu-id="5b2da-156">Requirements</span></span>  
 <span data-ttu-id="5b2da-157">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b2da-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b2da-158">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="5b2da-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b2da-159">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5b2da-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b2da-160">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b2da-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b2da-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b2da-161">See also</span></span>

- [<span data-ttu-id="5b2da-162">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="5b2da-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5b2da-163">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="5b2da-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
