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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 853f137d91e1b3eb4f3f65a06522618f8441dcb3
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053677"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="d2297-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="d2297-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="d2297-103">获取一个指针，该指针指向给定表中指定列和行的单元中包含的值。</span><span class="sxs-lookup"><span data-stu-id="d2297-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2297-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2297-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2297-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2297-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="d2297-106">中表的索引。</span><span class="sxs-lookup"><span data-stu-id="d2297-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="d2297-107">中表中的列的索引。</span><span class="sxs-lookup"><span data-stu-id="d2297-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="d2297-108">中表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="d2297-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="d2297-109">弄指向单元格中的值的指针。</span><span class="sxs-lookup"><span data-stu-id="d2297-109">[out] A pointer to the value in the cell.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="d2297-110">备注</span><span class="sxs-lookup"><span data-stu-id="d2297-110">Remarks</span></span>

<span data-ttu-id="d2297-111">返回的值的 interpretion `pVal`取决于列的类型。</span><span class="sxs-lookup"><span data-stu-id="d2297-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="d2297-112">列类型可通过调用[IMetaDataTables](imetadatatables-getcolumninfo-method.md)来确定。</span><span class="sxs-lookup"><span data-stu-id="d2297-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="d2297-113">**GetColumn**方法自动将**Rid**或**CodedToken**类型的列转换为完整的32位`mdToken`值。</span><span class="sxs-lookup"><span data-stu-id="d2297-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="d2297-114">它还会自动将8位或16位值转换为完整的32位值。</span><span class="sxs-lookup"><span data-stu-id="d2297-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span> 
- <span data-ttu-id="d2297-115">对于*堆*类型列，返回的*pVal*将是对应堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="d2297-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="d2297-116">列类型</span><span class="sxs-lookup"><span data-stu-id="d2297-116">Column type</span></span>              | <span data-ttu-id="d2297-117">pVal 包含</span><span class="sxs-lookup"><span data-stu-id="d2297-117">pVal contains</span></span> | <span data-ttu-id="d2297-118">注释</span><span class="sxs-lookup"><span data-stu-id="d2297-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="d2297-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="d2297-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="d2297-120">（0-63）</span><span class="sxs-lookup"><span data-stu-id="d2297-120">(0..63)</span></span>  | <span data-ttu-id="d2297-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="d2297-121">mdToken</span></span>     | <span data-ttu-id="d2297-122">*pVal*将包含一个完整的令牌。</span><span class="sxs-lookup"><span data-stu-id="d2297-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="d2297-123">函数自动将 Rid 转换为完整的标记。</span><span class="sxs-lookup"><span data-stu-id="d2297-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="d2297-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="d2297-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="d2297-125">（64.. 95）</span><span class="sxs-lookup"><span data-stu-id="d2297-125">(64..95)</span></span> | <span data-ttu-id="d2297-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="d2297-126">mdToken</span></span> | <span data-ttu-id="d2297-127">返回后， *pVal*将包含一个完整的令牌。</span><span class="sxs-lookup"><span data-stu-id="d2297-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="d2297-128">函数自动将 CodedToken 解压缩到完整的令牌中。</span><span class="sxs-lookup"><span data-stu-id="d2297-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="d2297-129">`iSHORT`（96）</span><span class="sxs-lookup"><span data-stu-id="d2297-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="d2297-130">Int16</span><span class="sxs-lookup"><span data-stu-id="d2297-130">Int16</span></span>         | <span data-ttu-id="d2297-131">自动将符号扩展为32位。</span><span class="sxs-lookup"><span data-stu-id="d2297-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="d2297-132">`iUSHORT`（97）</span><span class="sxs-lookup"><span data-stu-id="d2297-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="d2297-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="d2297-133">UInt16</span></span>        | <span data-ttu-id="d2297-134">自动将符号扩展为32位。</span><span class="sxs-lookup"><span data-stu-id="d2297-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="d2297-135">`iLONG`（98）</span><span class="sxs-lookup"><span data-stu-id="d2297-135">`iLONG` (98)</span></span>             | <span data-ttu-id="d2297-136">Int32</span><span class="sxs-lookup"><span data-stu-id="d2297-136">Int32</span></span>         |                                        | 
| <span data-ttu-id="d2297-137">`iULONG`（99）</span><span class="sxs-lookup"><span data-stu-id="d2297-137">`iULONG` (99)</span></span>            | <span data-ttu-id="d2297-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="d2297-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="d2297-139">`iBYTE`（100）</span><span class="sxs-lookup"><span data-stu-id="d2297-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="d2297-140">Byte</span><span class="sxs-lookup"><span data-stu-id="d2297-140">Byte</span></span>          | <span data-ttu-id="d2297-141">自动将符号扩展为32位。</span><span class="sxs-lookup"><span data-stu-id="d2297-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="d2297-142">`iSTRING`（101）</span><span class="sxs-lookup"><span data-stu-id="d2297-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="d2297-143">字符串堆索引</span><span class="sxs-lookup"><span data-stu-id="d2297-143">String heap index</span></span> | <span data-ttu-id="d2297-144">*pVal*是字符串堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="d2297-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="d2297-145">使用[IMetadataTables：： GetString](imetadatatables-getstring-method.md)获取实际的列字符串值。</span><span class="sxs-lookup"><span data-stu-id="d2297-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="d2297-146">`iGUID`（102）</span><span class="sxs-lookup"><span data-stu-id="d2297-146">`iGUID` (102)</span></span>            | <span data-ttu-id="d2297-147">Guid 堆索引</span><span class="sxs-lookup"><span data-stu-id="d2297-147">Guid heap index</span></span> | <span data-ttu-id="d2297-148">*pVal*是 Guid 堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="d2297-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="d2297-149">使用[IMetadataTables：： GetGuid](imetadatatables-getguid-method.md)获取实际的列 Guid 值。</span><span class="sxs-lookup"><span data-stu-id="d2297-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="d2297-150">`iBLOB`（103）</span><span class="sxs-lookup"><span data-stu-id="d2297-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="d2297-151">Blob 堆索引</span><span class="sxs-lookup"><span data-stu-id="d2297-151">Blob heap index</span></span> | <span data-ttu-id="d2297-152">*pVal*是 Blob 堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="d2297-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="d2297-153">使用[IMetadataTables：： GetBlob](imetadatatables-getblob-method.md)获取实际的列 Blob 值。</span><span class="sxs-lookup"><span data-stu-id="d2297-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="d2297-154">要求</span><span class="sxs-lookup"><span data-stu-id="d2297-154">Requirements</span></span>  
 <span data-ttu-id="d2297-155">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2297-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2297-156">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="d2297-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2297-157">**类库**用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d2297-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2297-158">**.NET Framework 版本**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2297-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2297-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2297-159">See also</span></span>

- [<span data-ttu-id="d2297-160">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="d2297-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d2297-161">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="d2297-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
