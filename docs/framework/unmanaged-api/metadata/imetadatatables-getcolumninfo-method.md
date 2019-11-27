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
ms.openlocfilehash: 854d3ad28cc00c03e903b9e1d2ce3863e3ceef17
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436105"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="72c19-102">IMetaDataTables::GetColumnInfo 方法</span><span class="sxs-lookup"><span data-stu-id="72c19-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="72c19-103">获取有关指定表中指定列的数据。</span><span class="sxs-lookup"><span data-stu-id="72c19-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c19-104">语法</span><span class="sxs-lookup"><span data-stu-id="72c19-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="72c19-105">参数</span><span class="sxs-lookup"><span data-stu-id="72c19-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="72c19-106">中所需表的索引。</span><span class="sxs-lookup"><span data-stu-id="72c19-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="72c19-107">中所需列的索引。</span><span class="sxs-lookup"><span data-stu-id="72c19-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="72c19-108">弄指向行中列的偏移量的指针。</span><span class="sxs-lookup"><span data-stu-id="72c19-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="72c19-109">弄一个指针，指向列的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="72c19-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="72c19-110">弄一个指针，指向列中值的类型。</span><span class="sxs-lookup"><span data-stu-id="72c19-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="72c19-111">弄指向列名的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="72c19-111">[out] A pointer to a pointer to the column name.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="72c19-112">备注</span><span class="sxs-lookup"><span data-stu-id="72c19-112">Remarks</span></span>

<span data-ttu-id="72c19-113">返回的列类型位于值的范围内：</span><span class="sxs-lookup"><span data-stu-id="72c19-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="72c19-114">pType</span><span class="sxs-lookup"><span data-stu-id="72c19-114">pType</span></span>                    | <span data-ttu-id="72c19-115">说明</span><span class="sxs-lookup"><span data-stu-id="72c19-115">Description</span></span>   | <span data-ttu-id="72c19-116">Helper 函数</span><span class="sxs-lookup"><span data-stu-id="72c19-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="72c19-117">`0`.。`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="72c19-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="72c19-118">（0-63）</span><span class="sxs-lookup"><span data-stu-id="72c19-118">(0..63)</span></span>   | <span data-ttu-id="72c19-119">去掉</span><span class="sxs-lookup"><span data-stu-id="72c19-119">Rid</span></span>           | <span data-ttu-id="72c19-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="72c19-120">**IsRidType**</span></span><br><span data-ttu-id="72c19-121">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="72c19-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="72c19-122">`iCodedToken`.。`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="72c19-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="72c19-123">（64.. 95）</span><span class="sxs-lookup"><span data-stu-id="72c19-123">(64..95)</span></span> | <span data-ttu-id="72c19-124">编码标记</span><span class="sxs-lookup"><span data-stu-id="72c19-124">Coded token</span></span> | <span data-ttu-id="72c19-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="72c19-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="72c19-126">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="72c19-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="72c19-127">`iSHORT` （96）</span><span class="sxs-lookup"><span data-stu-id="72c19-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="72c19-128">Int16</span><span class="sxs-lookup"><span data-stu-id="72c19-128">Int16</span></span>         | <span data-ttu-id="72c19-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="72c19-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="72c19-130">`iUSHORT` （97）</span><span class="sxs-lookup"><span data-stu-id="72c19-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="72c19-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="72c19-131">UInt16</span></span>        | <span data-ttu-id="72c19-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="72c19-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="72c19-133">`iLONG` （98）</span><span class="sxs-lookup"><span data-stu-id="72c19-133">`iLONG` (98)</span></span>             | <span data-ttu-id="72c19-134">Int32</span><span class="sxs-lookup"><span data-stu-id="72c19-134">Int32</span></span>         | <span data-ttu-id="72c19-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="72c19-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="72c19-136">`iULONG` （99）</span><span class="sxs-lookup"><span data-stu-id="72c19-136">`iULONG` (99)</span></span>            | <span data-ttu-id="72c19-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="72c19-137">UInt32</span></span>        | <span data-ttu-id="72c19-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="72c19-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="72c19-139">`iBYTE` （100）</span><span class="sxs-lookup"><span data-stu-id="72c19-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="72c19-140">字节</span><span class="sxs-lookup"><span data-stu-id="72c19-140">Byte</span></span>          | <span data-ttu-id="72c19-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="72c19-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="72c19-142">`iSTRING` （101）</span><span class="sxs-lookup"><span data-stu-id="72c19-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="72c19-143">String</span><span class="sxs-lookup"><span data-stu-id="72c19-143">String</span></span>        | <span data-ttu-id="72c19-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="72c19-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="72c19-145">`iGUID` （102）</span><span class="sxs-lookup"><span data-stu-id="72c19-145">`iGUID` (102)</span></span>            | <span data-ttu-id="72c19-146">Guid</span><span class="sxs-lookup"><span data-stu-id="72c19-146">Guid</span></span>          | <span data-ttu-id="72c19-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="72c19-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="72c19-148">`iBLOB` （103）</span><span class="sxs-lookup"><span data-stu-id="72c19-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="72c19-149">Blob</span><span class="sxs-lookup"><span data-stu-id="72c19-149">Blob</span></span>          | <span data-ttu-id="72c19-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="72c19-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="72c19-151">可以使用读取存储在*堆*中的值（即 `IsHeapType == true`）：</span><span class="sxs-lookup"><span data-stu-id="72c19-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="72c19-152">`iSTRING`： **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="72c19-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="72c19-153">`iGUID`： **IMetadataTables. GetGUID**</span><span class="sxs-lookup"><span data-stu-id="72c19-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="72c19-154">`iBLOB`： **IMetadataTables. GetBlob**</span><span class="sxs-lookup"><span data-stu-id="72c19-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72c19-155">若要使用上表中定义的常量，请包含*cor*头文件提供的指令 `#define _DEFINE_META_DATA_META_CONSTANTS`。</span><span class="sxs-lookup"><span data-stu-id="72c19-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="72c19-156">要求</span><span class="sxs-lookup"><span data-stu-id="72c19-156">Requirements</span></span>  
 <span data-ttu-id="72c19-157">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72c19-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c19-158">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="72c19-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72c19-159">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="72c19-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72c19-160">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72c19-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c19-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72c19-161">See also</span></span>

- [<span data-ttu-id="72c19-162">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="72c19-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="72c19-163">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="72c19-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
