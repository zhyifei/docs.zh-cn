---
title: IMetaDataTables 接口
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 17305f2c088dd6f479da4c823d3db0fd50c0b3d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443217"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="b28fc-102">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="b28fc-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="b28fc-103">提供存储和检索表中元数据信息的方法。</span><span class="sxs-lookup"><span data-stu-id="b28fc-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b28fc-104">方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-104">Methods</span></span>  
  
|<span data-ttu-id="b28fc-105">方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-105">Method</span></span>|<span data-ttu-id="b28fc-106">说明</span><span class="sxs-lookup"><span data-stu-id="b28fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b28fc-107">GetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="b28fc-108">获取一个指针，该指针指向指定列索引处的二进制大型对象（BLOB）。</span><span class="sxs-lookup"><span data-stu-id="b28fc-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="b28fc-109">GetBlobHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="b28fc-110">获取 BLOB 堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b28fc-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="b28fc-111">GetCodedTokenInfo 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="b28fc-112">获取一个指针，该指针指向与指定的行索引相关联的标记的数组。</span><span class="sxs-lookup"><span data-stu-id="b28fc-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="b28fc-113">GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="b28fc-114">获取一个指针，该指针指向指定表索引处的表中指定列索引处的列中包含的值。</span><span class="sxs-lookup"><span data-stu-id="b28fc-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b28fc-115">GetColumnInfo 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="b28fc-116">获取有关指定表中指定列的数据。</span><span class="sxs-lookup"><span data-stu-id="b28fc-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="b28fc-117">GetGuid 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="b28fc-118">获取指定索引处的行的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b28fc-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="b28fc-119">GetGuidHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="b28fc-120">获取 GUID 堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b28fc-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="b28fc-121">GetNextBlob 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="b28fc-122">获取表中下一个 BLOB 的索引。</span><span class="sxs-lookup"><span data-stu-id="b28fc-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="b28fc-123">GetNextGuid 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="b28fc-124">获取当前表列中的下一个 GUID 值的索引。</span><span class="sxs-lookup"><span data-stu-id="b28fc-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="b28fc-125">GetNextString 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="b28fc-126">获取当前表列中的下一个字符串的索引。</span><span class="sxs-lookup"><span data-stu-id="b28fc-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="b28fc-127">GetNextUserString 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="b28fc-128">获取包含当前表列中的下一个硬编码字符串的行的索引。</span><span class="sxs-lookup"><span data-stu-id="b28fc-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="b28fc-129">GetNumTables 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="b28fc-130">获取当前 `IMetaDataTables` 实例的范围中的表数。</span><span class="sxs-lookup"><span data-stu-id="b28fc-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="b28fc-131">GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="b28fc-132">获取位于指定表索引处的表中指定行索引处的行。</span><span class="sxs-lookup"><span data-stu-id="b28fc-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b28fc-133">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="b28fc-134">从当前引用范围内的表列中获取指定索引处的字符串。</span><span class="sxs-lookup"><span data-stu-id="b28fc-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="b28fc-135">GetStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="b28fc-136">获取字符串堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b28fc-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="b28fc-137">GetTableIndex 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="b28fc-138">获取指定的标记所引用的表的索引。</span><span class="sxs-lookup"><span data-stu-id="b28fc-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="b28fc-139">GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="b28fc-140">获取指定表索引处的表的名称、行大小、行数、列数和键列索引。</span><span class="sxs-lookup"><span data-stu-id="b28fc-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="b28fc-141">GetUserString 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="b28fc-142">获取当前范围内字符串列中指定索引处的硬编码字符串。</span><span class="sxs-lookup"><span data-stu-id="b28fc-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="b28fc-143">GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="b28fc-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="b28fc-144">获取用户字符串堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b28fc-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b28fc-145">要求</span><span class="sxs-lookup"><span data-stu-id="b28fc-145">Requirements</span></span>  
 <span data-ttu-id="b28fc-146">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b28fc-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28fc-147">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b28fc-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b28fc-148">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b28fc-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b28fc-149">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28fc-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28fc-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b28fc-150">See also</span></span>

- [<span data-ttu-id="b28fc-151">元数据接口</span><span class="sxs-lookup"><span data-stu-id="b28fc-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b28fc-152">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="b28fc-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
