---
title: IMetaDataTables::GetColumn 方法
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177143"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="65836-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="65836-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="65836-103">获取指向给定表中指定列和行单元格中包含的值的指针。</span><span class="sxs-lookup"><span data-stu-id="65836-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65836-104">语法</span><span class="sxs-lookup"><span data-stu-id="65836-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65836-105">parameters</span><span class="sxs-lookup"><span data-stu-id="65836-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="65836-106">[在]表的索引。</span><span class="sxs-lookup"><span data-stu-id="65836-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="65836-107">[在]表中列的索引。</span><span class="sxs-lookup"><span data-stu-id="65836-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="65836-108">[在]表中行的索引。</span><span class="sxs-lookup"><span data-stu-id="65836-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="65836-109">[出]指向单元格中值的指针。</span><span class="sxs-lookup"><span data-stu-id="65836-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="65836-110">备注</span><span class="sxs-lookup"><span data-stu-id="65836-110">Remarks</span></span>

<span data-ttu-id="65836-111">返回的值的解释`pVal`取决于列的类型。</span><span class="sxs-lookup"><span data-stu-id="65836-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="65836-112">可以通过调用[IMetaDataTables](imetadatatables-getcolumninfo-method.md)来确定列类型。</span><span class="sxs-lookup"><span data-stu-id="65836-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="65836-113">**GetColumn**方法会自动将 **"Rid"** 或"**编码令牌"** 类型的列转换为完整的 32 位`mdToken`值。</span><span class="sxs-lookup"><span data-stu-id="65836-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="65836-114">它还会自动将 8 位或 16 位值转换为完整的 32 位值。</span><span class="sxs-lookup"><span data-stu-id="65836-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="65836-115">对于*堆*类型列，返回的*pVal*将是相应堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="65836-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="65836-116">列类型</span><span class="sxs-lookup"><span data-stu-id="65836-116">Column type</span></span>              | <span data-ttu-id="65836-117">pVal 包含</span><span class="sxs-lookup"><span data-stu-id="65836-117">pVal contains</span></span> | <span data-ttu-id="65836-118">注释</span><span class="sxs-lookup"><span data-stu-id="65836-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="65836-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="65836-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="65836-120">(0..63)</span><span class="sxs-lookup"><span data-stu-id="65836-120">(0..63)</span></span>  | <span data-ttu-id="65836-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="65836-121">mdToken</span></span>     | <span data-ttu-id="65836-122">*pVal*将包含一个完整的令牌。</span><span class="sxs-lookup"><span data-stu-id="65836-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="65836-123">该函数会自动将 Rid 转换为完整令牌。</span><span class="sxs-lookup"><span data-stu-id="65836-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="65836-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="65836-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="65836-125">(64..95)</span><span class="sxs-lookup"><span data-stu-id="65836-125">(64..95)</span></span> | <span data-ttu-id="65836-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="65836-126">mdToken</span></span> | <span data-ttu-id="65836-127">返回后 *，pVal*将包含一个完整的令牌。</span><span class="sxs-lookup"><span data-stu-id="65836-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="65836-128">该函数会自动将编码令牌解压缩为完整令牌。</span><span class="sxs-lookup"><span data-stu-id="65836-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="65836-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="65836-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="65836-130">Int16</span><span class="sxs-lookup"><span data-stu-id="65836-130">Int16</span></span>         | <span data-ttu-id="65836-131">自动签名扩展到 32 位。</span><span class="sxs-lookup"><span data-stu-id="65836-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="65836-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="65836-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="65836-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="65836-133">UInt16</span></span>        | <span data-ttu-id="65836-134">自动签名扩展到 32 位。</span><span class="sxs-lookup"><span data-stu-id="65836-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="65836-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="65836-135">`iLONG` (98)</span></span>             | <span data-ttu-id="65836-136">Int32</span><span class="sxs-lookup"><span data-stu-id="65836-136">Int32</span></span>         |                                        |
| <span data-ttu-id="65836-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="65836-137">`iULONG` (99)</span></span>            | <span data-ttu-id="65836-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="65836-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="65836-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="65836-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="65836-140">Byte</span><span class="sxs-lookup"><span data-stu-id="65836-140">Byte</span></span>          | <span data-ttu-id="65836-141">自动签名扩展到 32 位。</span><span class="sxs-lookup"><span data-stu-id="65836-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="65836-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="65836-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="65836-143">字符串堆索引</span><span class="sxs-lookup"><span data-stu-id="65836-143">String heap index</span></span> | <span data-ttu-id="65836-144">*pVal*是字符串堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="65836-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="65836-145">使用[IMetadataTables：：获取String](imetadatatables-getstring-method.md)获取实际列字符串值。</span><span class="sxs-lookup"><span data-stu-id="65836-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="65836-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="65836-146">`iGUID` (102)</span></span>            | <span data-ttu-id="65836-147">吉德堆索引</span><span class="sxs-lookup"><span data-stu-id="65836-147">Guid heap index</span></span> | <span data-ttu-id="65836-148">*pVal*是 Guid 堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="65836-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="65836-149">使用[IMetadataTables：：getGuid](imetadatatables-getguid-method.md)获取实际列 Guid 值。</span><span class="sxs-lookup"><span data-stu-id="65836-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="65836-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="65836-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="65836-151">Blob 堆索引</span><span class="sxs-lookup"><span data-stu-id="65836-151">Blob heap index</span></span> | <span data-ttu-id="65836-152">*pVal*是 Blob 堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="65836-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="65836-153">使用[IMetadataTables：：获取 Blob](imetadatatables-getblob-method.md)获取实际列 Blob 值。</span><span class="sxs-lookup"><span data-stu-id="65836-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="65836-154">要求</span><span class="sxs-lookup"><span data-stu-id="65836-154">Requirements</span></span>  
 <span data-ttu-id="65836-155">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65836-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65836-156">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="65836-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65836-157">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="65836-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65836-158">**.NET 框架版本**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65836-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65836-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65836-159">See also</span></span>

- [<span data-ttu-id="65836-160">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="65836-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="65836-161">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="65836-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
