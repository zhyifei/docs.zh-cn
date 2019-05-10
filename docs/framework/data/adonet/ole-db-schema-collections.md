---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6c3441e86d4c5267418cf8002ba17d539c464d5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645900"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="37f6a-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="37f6a-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="37f6a-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="37f6a-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="37f6a-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="37f6a-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="37f6a-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="37f6a-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="37f6a-106">表</span><span class="sxs-lookup"><span data-stu-id="37f6a-106">Tables</span></span>  
  
- <span data-ttu-id="37f6a-107">列</span><span class="sxs-lookup"><span data-stu-id="37f6a-107">Columns</span></span>  
  
- <span data-ttu-id="37f6a-108">过程</span><span class="sxs-lookup"><span data-stu-id="37f6a-108">Procedures</span></span>  
  
- <span data-ttu-id="37f6a-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37f6a-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="37f6a-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="37f6a-110">Catalog</span></span>  
  
- <span data-ttu-id="37f6a-111">索引</span><span class="sxs-lookup"><span data-stu-id="37f6a-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37f6a-112">表</span><span class="sxs-lookup"><span data-stu-id="37f6a-112">Tables</span></span>  
  
|<span data-ttu-id="37f6a-113">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-113">ColumnName</span></span>|<span data-ttu-id="37f6a-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-115">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-116">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-116">String</span></span>|  
|<span data-ttu-id="37f6a-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-118">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-118">String</span></span>|  
|<span data-ttu-id="37f6a-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-119">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-120">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-120">String</span></span>|  
|<span data-ttu-id="37f6a-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-121">TABLE_TYPE</span></span>|<span data-ttu-id="37f6a-122">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-122">String</span></span>|  
|<span data-ttu-id="37f6a-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-123">TABLE_GUID</span></span>|<span data-ttu-id="37f6a-124">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-124">Guid</span></span>|  
|<span data-ttu-id="37f6a-125">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-125">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-126">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-126">String</span></span>|  
|<span data-ttu-id="37f6a-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-127">TABLE_PROPID</span></span>|<span data-ttu-id="37f6a-128">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-128">Int64</span></span>|  
|<span data-ttu-id="37f6a-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-129">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-130">DateTime</span></span>|  
|<span data-ttu-id="37f6a-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-131">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37f6a-133">列</span><span class="sxs-lookup"><span data-stu-id="37f6a-133">Columns</span></span>  
  
|<span data-ttu-id="37f6a-134">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-134">ColumnName</span></span>|<span data-ttu-id="37f6a-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-136">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-137">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-137">String</span></span>|  
|<span data-ttu-id="37f6a-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-139">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-139">String</span></span>|  
|<span data-ttu-id="37f6a-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-140">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-141">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-141">String</span></span>|  
|<span data-ttu-id="37f6a-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-142">COLUMN_NAME</span></span>|<span data-ttu-id="37f6a-143">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-143">String</span></span>|  
|<span data-ttu-id="37f6a-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-144">COLUMN_GUID</span></span>|<span data-ttu-id="37f6a-145">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-145">Guid</span></span>|  
|<span data-ttu-id="37f6a-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-146">COLUMN_PROPID</span></span>|<span data-ttu-id="37f6a-147">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-147">Int64</span></span>|  
|<span data-ttu-id="37f6a-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-149">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-149">Int64</span></span>|  
|<span data-ttu-id="37f6a-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37f6a-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-151">Boolean</span></span>|  
|<span data-ttu-id="37f6a-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37f6a-153">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-153">String</span></span>|  
|<span data-ttu-id="37f6a-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37f6a-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="37f6a-155">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-155">Int64</span></span>|  
|<span data-ttu-id="37f6a-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37f6a-156">IS_NULLABLE</span></span>|<span data-ttu-id="37f6a-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-157">Boolean</span></span>|  
|<span data-ttu-id="37f6a-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-158">DATA_TYPE</span></span>|<span data-ttu-id="37f6a-159">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-159">Int32</span></span>|  
|<span data-ttu-id="37f6a-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-160">TYPE_GUID</span></span>|<span data-ttu-id="37f6a-161">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-161">Guid</span></span>|  
|<span data-ttu-id="37f6a-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37f6a-163">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-163">Int64</span></span>|  
|<span data-ttu-id="37f6a-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37f6a-165">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-165">Int64</span></span>|  
|<span data-ttu-id="37f6a-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37f6a-167">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-167">Int32</span></span>|  
|<span data-ttu-id="37f6a-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37f6a-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="37f6a-169">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-169">Int16</span></span>|  
|<span data-ttu-id="37f6a-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="37f6a-171">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-171">Int64</span></span>|  
|<span data-ttu-id="37f6a-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37f6a-173">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-173">String</span></span>|  
|<span data-ttu-id="37f6a-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37f6a-175">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-175">String</span></span>|  
|<span data-ttu-id="37f6a-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37f6a-177">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-177">String</span></span>|  
|<span data-ttu-id="37f6a-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="37f6a-179">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-179">String</span></span>|  
|<span data-ttu-id="37f6a-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37f6a-181">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-181">String</span></span>|  
|<span data-ttu-id="37f6a-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-182">COLLATION_NAME</span></span>|<span data-ttu-id="37f6a-183">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-183">String</span></span>|  
|<span data-ttu-id="37f6a-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37f6a-185">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-185">String</span></span>|  
|<span data-ttu-id="37f6a-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37f6a-187">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-187">String</span></span>|  
|<span data-ttu-id="37f6a-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-188">DOMAIN_NAME</span></span>|<span data-ttu-id="37f6a-189">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-189">String</span></span>|  
|<span data-ttu-id="37f6a-190">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-190">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-191">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-191">String</span></span>|  
|<span data-ttu-id="37f6a-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="37f6a-192">COLUMN_LCID</span></span>|<span data-ttu-id="37f6a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-193">Int32</span></span>|  
|<span data-ttu-id="37f6a-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="37f6a-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="37f6a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-195">Int32</span></span>|  
|<span data-ttu-id="37f6a-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="37f6a-196">COLUMN_SORTID</span></span>|<span data-ttu-id="37f6a-197">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-197">Int32</span></span>|  
|<span data-ttu-id="37f6a-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="37f6a-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="37f6a-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="37f6a-199">Byte[]</span></span>|  
|<span data-ttu-id="37f6a-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="37f6a-200">IS_COMPUTED</span></span>|<span data-ttu-id="37f6a-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37f6a-202">过程</span><span class="sxs-lookup"><span data-stu-id="37f6a-202">Procedures</span></span>  
  
|<span data-ttu-id="37f6a-203">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-203">ColumnName</span></span>|<span data-ttu-id="37f6a-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37f6a-206">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-206">String</span></span>|  
|<span data-ttu-id="37f6a-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37f6a-208">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-208">String</span></span>|  
|<span data-ttu-id="37f6a-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="37f6a-210">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-210">String</span></span>|  
|<span data-ttu-id="37f6a-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37f6a-212">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-212">Int16</span></span>|  
|<span data-ttu-id="37f6a-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37f6a-214">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-214">String</span></span>|  
|<span data-ttu-id="37f6a-215">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-215">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-216">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-216">String</span></span>|  
|<span data-ttu-id="37f6a-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-217">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-218">DateTime</span></span>|  
|<span data-ttu-id="37f6a-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-219">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="37f6a-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37f6a-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="37f6a-222">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-222">ColumnName</span></span>|<span data-ttu-id="37f6a-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37f6a-225">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-225">String</span></span>|  
|<span data-ttu-id="37f6a-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37f6a-227">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-227">String</span></span>|  
|<span data-ttu-id="37f6a-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="37f6a-229">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-229">String</span></span>|  
|<span data-ttu-id="37f6a-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-230">PARAMETER_NAME</span></span>|<span data-ttu-id="37f6a-231">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-231">String</span></span>|  
|<span data-ttu-id="37f6a-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-233">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-233">Int32</span></span>|  
|<span data-ttu-id="37f6a-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="37f6a-235">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-235">Int32</span></span>|  
|<span data-ttu-id="37f6a-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="37f6a-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-237">Boolean</span></span>|  
|<span data-ttu-id="37f6a-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="37f6a-239">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-239">String</span></span>|  
|<span data-ttu-id="37f6a-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37f6a-240">IS_NULLABLE</span></span>|<span data-ttu-id="37f6a-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-241">Boolean</span></span>|  
|<span data-ttu-id="37f6a-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-242">DATA_TYPE</span></span>|<span data-ttu-id="37f6a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-243">Int32</span></span>|  
|<span data-ttu-id="37f6a-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37f6a-245">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-245">Int64</span></span>|  
|<span data-ttu-id="37f6a-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37f6a-247">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-247">Int64</span></span>|  
|<span data-ttu-id="37f6a-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37f6a-249">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-249">Int32</span></span>|  
|<span data-ttu-id="37f6a-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37f6a-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="37f6a-251">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-251">Int16</span></span>|  
|<span data-ttu-id="37f6a-252">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-252">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-253">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-253">String</span></span>|  
|<span data-ttu-id="37f6a-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-254">TYPE_NAME</span></span>|<span data-ttu-id="37f6a-255">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-255">String</span></span>|  
|<span data-ttu-id="37f6a-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="37f6a-257">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="37f6a-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="37f6a-258">Catalog</span></span>  
  
|<span data-ttu-id="37f6a-259">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-259">ColumnName</span></span>|<span data-ttu-id="37f6a-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-261">CATALOG_NAME</span></span>|<span data-ttu-id="37f6a-262">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-262">String</span></span>|  
|<span data-ttu-id="37f6a-263">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-263">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-264">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37f6a-265">索引</span><span class="sxs-lookup"><span data-stu-id="37f6a-265">Indexes</span></span>  
  
|<span data-ttu-id="37f6a-266">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-266">ColumnName</span></span>|<span data-ttu-id="37f6a-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-268">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-269">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-269">String</span></span>|  
|<span data-ttu-id="37f6a-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-271">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-271">String</span></span>|  
|<span data-ttu-id="37f6a-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-272">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-273">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-273">String</span></span>|  
|<span data-ttu-id="37f6a-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-274">INDEX_CATALOG</span></span>|<span data-ttu-id="37f6a-275">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-275">String</span></span>|  
|<span data-ttu-id="37f6a-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="37f6a-277">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-277">String</span></span>|  
|<span data-ttu-id="37f6a-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-278">INDEX_NAME</span></span>|<span data-ttu-id="37f6a-279">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-279">String</span></span>|  
|<span data-ttu-id="37f6a-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37f6a-280">PRIMARY_KEY</span></span>|<span data-ttu-id="37f6a-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-281">Boolean</span></span>|  
|<span data-ttu-id="37f6a-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37f6a-282">UNIQUE</span></span>|<span data-ttu-id="37f6a-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-283">Boolean</span></span>|  
|<span data-ttu-id="37f6a-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37f6a-284">CLUSTERED</span></span>|<span data-ttu-id="37f6a-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-285">Boolean</span></span>|  
|<span data-ttu-id="37f6a-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-286">TYPE</span></span>|<span data-ttu-id="37f6a-287">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-287">Int32</span></span>|  
|<span data-ttu-id="37f6a-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37f6a-288">FILL_FACTOR</span></span>|<span data-ttu-id="37f6a-289">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-289">Int32</span></span>|  
|<span data-ttu-id="37f6a-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37f6a-290">INITIAL_SIZE</span></span>|<span data-ttu-id="37f6a-291">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-291">Int32</span></span>|  
|<span data-ttu-id="37f6a-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="37f6a-292">NULLS</span></span>|<span data-ttu-id="37f6a-293">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-293">Int32</span></span>|  
|<span data-ttu-id="37f6a-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37f6a-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37f6a-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-295">Boolean</span></span>|  
|<span data-ttu-id="37f6a-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37f6a-296">AUTO_UPDATE</span></span>|<span data-ttu-id="37f6a-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-297">Boolean</span></span>|  
|<span data-ttu-id="37f6a-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37f6a-298">NULL_COLLATION</span></span>|<span data-ttu-id="37f6a-299">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-299">Int32</span></span>|  
|<span data-ttu-id="37f6a-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-301">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-301">Int64</span></span>|  
|<span data-ttu-id="37f6a-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-302">COLUMN_NAME</span></span>|<span data-ttu-id="37f6a-303">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-303">String</span></span>|  
|<span data-ttu-id="37f6a-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-304">COLUMN_GUID</span></span>|<span data-ttu-id="37f6a-305">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-305">Guid</span></span>|  
|<span data-ttu-id="37f6a-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-306">COLUMN_PROPID</span></span>|<span data-ttu-id="37f6a-307">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-307">Int64</span></span>|  
|<span data-ttu-id="37f6a-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37f6a-308">COLLATION</span></span>|<span data-ttu-id="37f6a-309">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-309">Int16</span></span>|  
|<span data-ttu-id="37f6a-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37f6a-310">CARDINALITY</span></span>|<span data-ttu-id="37f6a-311">十进制</span><span class="sxs-lookup"><span data-stu-id="37f6a-311">Decimal</span></span>|  
|<span data-ttu-id="37f6a-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="37f6a-312">PAGES</span></span>|<span data-ttu-id="37f6a-313">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-313">Int32</span></span>|  
|<span data-ttu-id="37f6a-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-314">FILTER_CONDITION</span></span>|<span data-ttu-id="37f6a-315">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-315">String</span></span>|  
|<span data-ttu-id="37f6a-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-316">INTEGRATED</span></span>|<span data-ttu-id="37f6a-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="37f6a-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="37f6a-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="37f6a-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="37f6a-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="37f6a-320">表</span><span class="sxs-lookup"><span data-stu-id="37f6a-320">Tables</span></span>  
  
- <span data-ttu-id="37f6a-321">列</span><span class="sxs-lookup"><span data-stu-id="37f6a-321">Columns</span></span>  
  
- <span data-ttu-id="37f6a-322">过程</span><span class="sxs-lookup"><span data-stu-id="37f6a-322">Procedures</span></span>  
  
- <span data-ttu-id="37f6a-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="37f6a-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="37f6a-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37f6a-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="37f6a-325">Views</span><span class="sxs-lookup"><span data-stu-id="37f6a-325">Views</span></span>  
  
- <span data-ttu-id="37f6a-326">索引</span><span class="sxs-lookup"><span data-stu-id="37f6a-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37f6a-327">表</span><span class="sxs-lookup"><span data-stu-id="37f6a-327">Tables</span></span>  
  
|<span data-ttu-id="37f6a-328">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-328">ColumnName</span></span>|<span data-ttu-id="37f6a-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-330">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-331">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-331">String</span></span>|  
|<span data-ttu-id="37f6a-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-333">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-333">String</span></span>|  
|<span data-ttu-id="37f6a-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-334">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-335">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-335">String</span></span>|  
|<span data-ttu-id="37f6a-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-336">TABLE_TYPE</span></span>|<span data-ttu-id="37f6a-337">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-337">String</span></span>|  
|<span data-ttu-id="37f6a-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-338">TABLE_GUID</span></span>|<span data-ttu-id="37f6a-339">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-339">Guid</span></span>|  
|<span data-ttu-id="37f6a-340">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-340">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-341">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-341">String</span></span>|  
|<span data-ttu-id="37f6a-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-342">TABLE_PROPID</span></span>|<span data-ttu-id="37f6a-343">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-343">Int64</span></span>|  
|<span data-ttu-id="37f6a-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-344">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-345">DateTime</span></span>|  
|<span data-ttu-id="37f6a-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-346">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37f6a-348">列</span><span class="sxs-lookup"><span data-stu-id="37f6a-348">Columns</span></span>  
  
|<span data-ttu-id="37f6a-349">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-349">ColumnName</span></span>|<span data-ttu-id="37f6a-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-351">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-352">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-352">String</span></span>|  
|<span data-ttu-id="37f6a-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-354">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-354">String</span></span>|  
|<span data-ttu-id="37f6a-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-355">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-356">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-356">String</span></span>|  
|<span data-ttu-id="37f6a-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-357">COLUMN_NAME</span></span>|<span data-ttu-id="37f6a-358">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-358">String</span></span>|  
|<span data-ttu-id="37f6a-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-359">COLUMN_GUID</span></span>|<span data-ttu-id="37f6a-360">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-360">Guid</span></span>|  
|<span data-ttu-id="37f6a-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-361">COLUMN_PROPID</span></span>|<span data-ttu-id="37f6a-362">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-362">Int64</span></span>|  
|<span data-ttu-id="37f6a-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-364">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-364">Int64</span></span>|  
|<span data-ttu-id="37f6a-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37f6a-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-366">Boolean</span></span>|  
|<span data-ttu-id="37f6a-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37f6a-368">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-368">String</span></span>|  
|<span data-ttu-id="37f6a-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37f6a-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="37f6a-370">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-370">Int64</span></span>|  
|<span data-ttu-id="37f6a-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37f6a-371">IS_NULLABLE</span></span>|<span data-ttu-id="37f6a-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-372">Boolean</span></span>|  
|<span data-ttu-id="37f6a-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-373">DATA_TYPE</span></span>|<span data-ttu-id="37f6a-374">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-374">Int32</span></span>|  
|<span data-ttu-id="37f6a-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-375">TYPE_GUID</span></span>|<span data-ttu-id="37f6a-376">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-376">Guid</span></span>|  
|<span data-ttu-id="37f6a-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37f6a-378">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-378">Int64</span></span>|  
|<span data-ttu-id="37f6a-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37f6a-380">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-380">Int64</span></span>|  
|<span data-ttu-id="37f6a-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37f6a-382">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-382">Int32</span></span>|  
|<span data-ttu-id="37f6a-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37f6a-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="37f6a-384">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-384">Int16</span></span>|  
|<span data-ttu-id="37f6a-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="37f6a-386">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-386">Int64</span></span>|  
|<span data-ttu-id="37f6a-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37f6a-388">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-388">String</span></span>|  
|<span data-ttu-id="37f6a-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37f6a-390">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-390">String</span></span>|  
|<span data-ttu-id="37f6a-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37f6a-392">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-392">String</span></span>|  
|<span data-ttu-id="37f6a-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="37f6a-394">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-394">String</span></span>|  
|<span data-ttu-id="37f6a-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37f6a-396">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-396">String</span></span>|  
|<span data-ttu-id="37f6a-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-397">COLLATION_NAME</span></span>|<span data-ttu-id="37f6a-398">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-398">String</span></span>|  
|<span data-ttu-id="37f6a-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37f6a-400">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-400">String</span></span>|  
|<span data-ttu-id="37f6a-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37f6a-402">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-402">String</span></span>|  
|<span data-ttu-id="37f6a-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-403">DOMAIN_NAME</span></span>|<span data-ttu-id="37f6a-404">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-404">String</span></span>|  
|<span data-ttu-id="37f6a-405">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-405">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-406">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37f6a-407">过程</span><span class="sxs-lookup"><span data-stu-id="37f6a-407">Procedures</span></span>  
  
|<span data-ttu-id="37f6a-408">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-408">ColumnName</span></span>|<span data-ttu-id="37f6a-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37f6a-411">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-411">String</span></span>|  
|<span data-ttu-id="37f6a-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37f6a-413">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-413">String</span></span>|  
|<span data-ttu-id="37f6a-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="37f6a-415">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-415">String</span></span>|  
|<span data-ttu-id="37f6a-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37f6a-417">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-417">Int16</span></span>|  
|<span data-ttu-id="37f6a-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37f6a-419">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-419">String</span></span>|  
|<span data-ttu-id="37f6a-420">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-420">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-421">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-421">String</span></span>|  
|<span data-ttu-id="37f6a-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-422">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-423">DateTime</span></span>|  
|<span data-ttu-id="37f6a-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-424">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="37f6a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="37f6a-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="37f6a-427">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-427">ColumnName</span></span>|<span data-ttu-id="37f6a-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37f6a-430">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-430">String</span></span>|  
|<span data-ttu-id="37f6a-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37f6a-432">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-432">String</span></span>|  
|<span data-ttu-id="37f6a-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="37f6a-434">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-434">String</span></span>|  
|<span data-ttu-id="37f6a-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-435">COLUMN_NAME</span></span>|<span data-ttu-id="37f6a-436">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-436">String</span></span>|  
|<span data-ttu-id="37f6a-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-437">COLUMN_GUID</span></span>|<span data-ttu-id="37f6a-438">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-438">Guid</span></span>|  
|<span data-ttu-id="37f6a-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-439">COLUMN_PROPID</span></span>|<span data-ttu-id="37f6a-440">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-440">Int64</span></span>|  
|<span data-ttu-id="37f6a-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="37f6a-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="37f6a-442">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-442">Int64</span></span>|  
|<span data-ttu-id="37f6a-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-444">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-444">Int64</span></span>|  
|<span data-ttu-id="37f6a-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37f6a-445">IS_NULLABLE</span></span>|<span data-ttu-id="37f6a-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-446">Boolean</span></span>|  
|<span data-ttu-id="37f6a-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-447">DATA_TYPE</span></span>|<span data-ttu-id="37f6a-448">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-448">Int32</span></span>|  
|<span data-ttu-id="37f6a-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-449">TYPE_GUID</span></span>|<span data-ttu-id="37f6a-450">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-450">Guid</span></span>|  
|<span data-ttu-id="37f6a-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37f6a-452">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-452">Int64</span></span>|  
|<span data-ttu-id="37f6a-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37f6a-454">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-454">Int64</span></span>|  
|<span data-ttu-id="37f6a-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37f6a-456">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-456">Int32</span></span>|  
|<span data-ttu-id="37f6a-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37f6a-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="37f6a-458">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-458">Int16</span></span>|  
|<span data-ttu-id="37f6a-459">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-459">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-460">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-460">String</span></span>|  
|<span data-ttu-id="37f6a-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="37f6a-461">OVERLOAD</span></span>|<span data-ttu-id="37f6a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="37f6a-463">Views</span><span class="sxs-lookup"><span data-stu-id="37f6a-463">Views</span></span>  
  
|<span data-ttu-id="37f6a-464">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-464">ColumnName</span></span>|<span data-ttu-id="37f6a-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-466">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-467">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-467">String</span></span>|  
|<span data-ttu-id="37f6a-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-469">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-469">String</span></span>|  
|<span data-ttu-id="37f6a-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-470">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-471">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-471">String</span></span>|  
|<span data-ttu-id="37f6a-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="37f6a-473">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-473">String</span></span>|  
|<span data-ttu-id="37f6a-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="37f6a-474">CHECK_OPTION</span></span>|<span data-ttu-id="37f6a-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-475">Boolean</span></span>|  
|<span data-ttu-id="37f6a-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="37f6a-476">IS_UPDATABLE</span></span>|<span data-ttu-id="37f6a-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-477">Boolean</span></span>|  
|<span data-ttu-id="37f6a-478">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-478">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-479">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-479">String</span></span>|  
|<span data-ttu-id="37f6a-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-480">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-481">DateTime</span></span>|  
|<span data-ttu-id="37f6a-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-482">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37f6a-484">索引</span><span class="sxs-lookup"><span data-stu-id="37f6a-484">Indexes</span></span>  
  
|<span data-ttu-id="37f6a-485">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-485">ColumnName</span></span>|<span data-ttu-id="37f6a-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-487">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-488">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-488">String</span></span>|  
|<span data-ttu-id="37f6a-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-490">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-490">String</span></span>|  
|<span data-ttu-id="37f6a-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-491">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-492">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-492">String</span></span>|  
|<span data-ttu-id="37f6a-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-493">INDEX_CATALOG</span></span>|<span data-ttu-id="37f6a-494">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-494">String</span></span>|  
|<span data-ttu-id="37f6a-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="37f6a-496">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-496">String</span></span>|  
|<span data-ttu-id="37f6a-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-497">INDEX_NAME</span></span>|<span data-ttu-id="37f6a-498">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-498">String</span></span>|  
|<span data-ttu-id="37f6a-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37f6a-499">PRIMARY_KEY</span></span>|<span data-ttu-id="37f6a-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-500">Boolean</span></span>|  
|<span data-ttu-id="37f6a-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37f6a-501">UNIQUE</span></span>|<span data-ttu-id="37f6a-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-502">Boolean</span></span>|  
|<span data-ttu-id="37f6a-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37f6a-503">CLUSTERED</span></span>|<span data-ttu-id="37f6a-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-504">Boolean</span></span>|  
|<span data-ttu-id="37f6a-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-505">TYPE</span></span>|<span data-ttu-id="37f6a-506">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-506">Int32</span></span>|  
|<span data-ttu-id="37f6a-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37f6a-507">FILL_FACTOR</span></span>|<span data-ttu-id="37f6a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-508">Int32</span></span>|  
|<span data-ttu-id="37f6a-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37f6a-509">INITIAL_SIZE</span></span>|<span data-ttu-id="37f6a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-510">Int32</span></span>|  
|<span data-ttu-id="37f6a-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="37f6a-511">NULLS</span></span>|<span data-ttu-id="37f6a-512">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-512">Int32</span></span>|  
|<span data-ttu-id="37f6a-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37f6a-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37f6a-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-514">Boolean</span></span>|  
|<span data-ttu-id="37f6a-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37f6a-515">AUTO_UPDATE</span></span>|<span data-ttu-id="37f6a-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-516">Boolean</span></span>|  
|<span data-ttu-id="37f6a-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37f6a-517">NULL_COLLATION</span></span>|<span data-ttu-id="37f6a-518">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-518">Int32</span></span>|  
|<span data-ttu-id="37f6a-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-520">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-520">Int64</span></span>|  
|<span data-ttu-id="37f6a-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-521">COLUMN_NAME</span></span>|<span data-ttu-id="37f6a-522">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-522">String</span></span>|  
|<span data-ttu-id="37f6a-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-523">COLUMN_GUID</span></span>|<span data-ttu-id="37f6a-524">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-524">Guid</span></span>|  
|<span data-ttu-id="37f6a-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-525">COLUMN_PROPID</span></span>|<span data-ttu-id="37f6a-526">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-526">Int64</span></span>|  
|<span data-ttu-id="37f6a-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37f6a-527">COLLATION</span></span>|<span data-ttu-id="37f6a-528">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-528">Int16</span></span>|  
|<span data-ttu-id="37f6a-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37f6a-529">CARDINALITY</span></span>|<span data-ttu-id="37f6a-530">十进制</span><span class="sxs-lookup"><span data-stu-id="37f6a-530">Decimal</span></span>|  
|<span data-ttu-id="37f6a-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="37f6a-531">PAGES</span></span>|<span data-ttu-id="37f6a-532">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-532">Int32</span></span>|  
|<span data-ttu-id="37f6a-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-533">FILTER_CONDITION</span></span>|<span data-ttu-id="37f6a-534">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-534">String</span></span>|  
|<span data-ttu-id="37f6a-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-535">INTEGRATED</span></span>|<span data-ttu-id="37f6a-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="37f6a-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="37f6a-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="37f6a-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="37f6a-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="37f6a-539">表</span><span class="sxs-lookup"><span data-stu-id="37f6a-539">Tables</span></span>  
  
- <span data-ttu-id="37f6a-540">列</span><span class="sxs-lookup"><span data-stu-id="37f6a-540">Columns</span></span>  
  
- <span data-ttu-id="37f6a-541">过程</span><span class="sxs-lookup"><span data-stu-id="37f6a-541">Procedures</span></span>  
  
- <span data-ttu-id="37f6a-542">Views</span><span class="sxs-lookup"><span data-stu-id="37f6a-542">Views</span></span>  
  
- <span data-ttu-id="37f6a-543">索引</span><span class="sxs-lookup"><span data-stu-id="37f6a-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37f6a-544">表</span><span class="sxs-lookup"><span data-stu-id="37f6a-544">Tables</span></span>  
  
|<span data-ttu-id="37f6a-545">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-545">ColumnName</span></span>|<span data-ttu-id="37f6a-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-547">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-548">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-548">String</span></span>|  
|<span data-ttu-id="37f6a-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-550">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-550">String</span></span>|  
|<span data-ttu-id="37f6a-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-551">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-552">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-552">String</span></span>|  
|<span data-ttu-id="37f6a-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-553">TABLE_TYPE</span></span>|<span data-ttu-id="37f6a-554">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-554">String</span></span>|  
|<span data-ttu-id="37f6a-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-555">TABLE_GUID</span></span>|<span data-ttu-id="37f6a-556">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-556">Guid</span></span>|  
|<span data-ttu-id="37f6a-557">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-557">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-558">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-558">String</span></span>|  
|<span data-ttu-id="37f6a-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-559">TABLE_PROPID</span></span>|<span data-ttu-id="37f6a-560">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-560">Int64</span></span>|  
|<span data-ttu-id="37f6a-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-561">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-562">DateTime</span></span>|  
|<span data-ttu-id="37f6a-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-563">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37f6a-565">列</span><span class="sxs-lookup"><span data-stu-id="37f6a-565">Columns</span></span>  
  
|<span data-ttu-id="37f6a-566">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-566">ColumnName</span></span>|<span data-ttu-id="37f6a-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-568">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-569">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-569">String</span></span>|  
|<span data-ttu-id="37f6a-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-571">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-571">String</span></span>|  
|<span data-ttu-id="37f6a-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-572">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-573">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-573">String</span></span>|  
|<span data-ttu-id="37f6a-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-574">COLUMN_NAME</span></span>|<span data-ttu-id="37f6a-575">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-575">String</span></span>|  
|<span data-ttu-id="37f6a-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-576">COLUMN_GUID</span></span>|<span data-ttu-id="37f6a-577">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-577">Guid</span></span>|  
|<span data-ttu-id="37f6a-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-578">COLUMN_PROPID</span></span>|<span data-ttu-id="37f6a-579">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-579">Int64</span></span>|  
|<span data-ttu-id="37f6a-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-581">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-581">Int64</span></span>|  
|<span data-ttu-id="37f6a-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37f6a-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-583">Boolean</span></span>|  
|<span data-ttu-id="37f6a-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37f6a-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37f6a-585">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-585">String</span></span>|  
|<span data-ttu-id="37f6a-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37f6a-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="37f6a-587">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-587">Int64</span></span>|  
|<span data-ttu-id="37f6a-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37f6a-588">IS_NULLABLE</span></span>|<span data-ttu-id="37f6a-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-589">Boolean</span></span>|  
|<span data-ttu-id="37f6a-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-590">DATA_TYPE</span></span>|<span data-ttu-id="37f6a-591">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-591">Int32</span></span>|  
|<span data-ttu-id="37f6a-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-592">TYPE_GUID</span></span>|<span data-ttu-id="37f6a-593">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-593">Guid</span></span>|  
|<span data-ttu-id="37f6a-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37f6a-595">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-595">Int64</span></span>|  
|<span data-ttu-id="37f6a-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37f6a-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37f6a-597">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-597">Int64</span></span>|  
|<span data-ttu-id="37f6a-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37f6a-599">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-599">Int32</span></span>|  
|<span data-ttu-id="37f6a-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37f6a-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="37f6a-601">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-601">Int16</span></span>|  
|<span data-ttu-id="37f6a-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37f6a-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="37f6a-603">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-603">Int64</span></span>|  
|<span data-ttu-id="37f6a-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37f6a-605">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-605">String</span></span>|  
|<span data-ttu-id="37f6a-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37f6a-607">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-607">String</span></span>|  
|<span data-ttu-id="37f6a-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37f6a-609">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-609">String</span></span>|  
|<span data-ttu-id="37f6a-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="37f6a-611">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-611">String</span></span>|  
|<span data-ttu-id="37f6a-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37f6a-613">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-613">String</span></span>|  
|<span data-ttu-id="37f6a-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-614">COLLATION_NAME</span></span>|<span data-ttu-id="37f6a-615">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-615">String</span></span>|  
|<span data-ttu-id="37f6a-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37f6a-617">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-617">String</span></span>|  
|<span data-ttu-id="37f6a-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37f6a-619">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-619">String</span></span>|  
|<span data-ttu-id="37f6a-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-620">DOMAIN_NAME</span></span>|<span data-ttu-id="37f6a-621">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-621">String</span></span>|  
|<span data-ttu-id="37f6a-622">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-622">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-623">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37f6a-624">过程</span><span class="sxs-lookup"><span data-stu-id="37f6a-624">Procedures</span></span>  
  
|<span data-ttu-id="37f6a-625">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-625">ColumnName</span></span>|<span data-ttu-id="37f6a-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37f6a-628">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-628">String</span></span>|  
|<span data-ttu-id="37f6a-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37f6a-630">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-630">String</span></span>|  
|<span data-ttu-id="37f6a-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="37f6a-632">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-632">String</span></span>|  
|<span data-ttu-id="37f6a-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37f6a-634">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-634">Int16</span></span>|  
|<span data-ttu-id="37f6a-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37f6a-636">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-636">String</span></span>|  
|<span data-ttu-id="37f6a-637">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-637">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-638">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-638">String</span></span>|  
|<span data-ttu-id="37f6a-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-639">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-640">DateTime</span></span>|  
|<span data-ttu-id="37f6a-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-641">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="37f6a-643">Views</span><span class="sxs-lookup"><span data-stu-id="37f6a-643">Views</span></span>  
  
|<span data-ttu-id="37f6a-644">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-644">ColumnName</span></span>|<span data-ttu-id="37f6a-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-646">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-647">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-647">String</span></span>|  
|<span data-ttu-id="37f6a-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-649">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-649">String</span></span>|  
|<span data-ttu-id="37f6a-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-650">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-651">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-651">String</span></span>|  
|<span data-ttu-id="37f6a-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="37f6a-653">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-653">String</span></span>|  
|<span data-ttu-id="37f6a-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="37f6a-654">CHECK_OPTION</span></span>|<span data-ttu-id="37f6a-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-655">Boolean</span></span>|  
|<span data-ttu-id="37f6a-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="37f6a-656">IS_UPDATABLE</span></span>|<span data-ttu-id="37f6a-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-657">Boolean</span></span>|  
|<span data-ttu-id="37f6a-658">描述</span><span class="sxs-lookup"><span data-stu-id="37f6a-658">DESCRIPTION</span></span>|<span data-ttu-id="37f6a-659">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-659">String</span></span>|  
|<span data-ttu-id="37f6a-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-660">DATE_CREATED</span></span>|<span data-ttu-id="37f6a-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-661">DateTime</span></span>|  
|<span data-ttu-id="37f6a-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37f6a-662">DATE_MODIFIED</span></span>|<span data-ttu-id="37f6a-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="37f6a-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37f6a-664">索引</span><span class="sxs-lookup"><span data-stu-id="37f6a-664">Indexes</span></span>  
  
|<span data-ttu-id="37f6a-665">列名</span><span class="sxs-lookup"><span data-stu-id="37f6a-665">ColumnName</span></span>|<span data-ttu-id="37f6a-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f6a-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37f6a-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-667">TABLE_CATALOG</span></span>|<span data-ttu-id="37f6a-668">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-668">String</span></span>|  
|<span data-ttu-id="37f6a-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="37f6a-670">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-670">String</span></span>|  
|<span data-ttu-id="37f6a-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-671">TABLE_NAME</span></span>|<span data-ttu-id="37f6a-672">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-672">String</span></span>|  
|<span data-ttu-id="37f6a-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37f6a-673">INDEX_CATALOG</span></span>|<span data-ttu-id="37f6a-674">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-674">String</span></span>|  
|<span data-ttu-id="37f6a-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37f6a-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="37f6a-676">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-676">String</span></span>|  
|<span data-ttu-id="37f6a-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-677">INDEX_NAME</span></span>|<span data-ttu-id="37f6a-678">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-678">String</span></span>|  
|<span data-ttu-id="37f6a-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37f6a-679">PRIMARY_KEY</span></span>|<span data-ttu-id="37f6a-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-680">Boolean</span></span>|  
|<span data-ttu-id="37f6a-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37f6a-681">UNIQUE</span></span>|<span data-ttu-id="37f6a-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-682">Boolean</span></span>|  
|<span data-ttu-id="37f6a-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37f6a-683">CLUSTERED</span></span>|<span data-ttu-id="37f6a-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-684">Boolean</span></span>|  
|<span data-ttu-id="37f6a-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="37f6a-685">TYPE</span></span>|<span data-ttu-id="37f6a-686">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-686">Int32</span></span>|  
|<span data-ttu-id="37f6a-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37f6a-687">FILL_FACTOR</span></span>|<span data-ttu-id="37f6a-688">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-688">Int32</span></span>|  
|<span data-ttu-id="37f6a-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37f6a-689">INITIAL_SIZE</span></span>|<span data-ttu-id="37f6a-690">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-690">Int32</span></span>|  
|<span data-ttu-id="37f6a-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="37f6a-691">NULLS</span></span>|<span data-ttu-id="37f6a-692">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-692">Int32</span></span>|  
|<span data-ttu-id="37f6a-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37f6a-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37f6a-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-694">Boolean</span></span>|  
|<span data-ttu-id="37f6a-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37f6a-695">AUTO_UPDATE</span></span>|<span data-ttu-id="37f6a-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-696">Boolean</span></span>|  
|<span data-ttu-id="37f6a-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37f6a-697">NULL_COLLATION</span></span>|<span data-ttu-id="37f6a-698">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-698">Int32</span></span>|  
|<span data-ttu-id="37f6a-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="37f6a-700">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-700">Int64</span></span>|  
|<span data-ttu-id="37f6a-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37f6a-701">COLUMN_NAME</span></span>|<span data-ttu-id="37f6a-702">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-702">String</span></span>|  
|<span data-ttu-id="37f6a-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-703">COLUMN_GUID</span></span>|<span data-ttu-id="37f6a-704">GUID</span><span class="sxs-lookup"><span data-stu-id="37f6a-704">Guid</span></span>|  
|<span data-ttu-id="37f6a-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37f6a-705">COLUMN_PROPID</span></span>|<span data-ttu-id="37f6a-706">Int64</span><span class="sxs-lookup"><span data-stu-id="37f6a-706">Int64</span></span>|  
|<span data-ttu-id="37f6a-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37f6a-707">COLLATION</span></span>|<span data-ttu-id="37f6a-708">Int16</span><span class="sxs-lookup"><span data-stu-id="37f6a-708">Int16</span></span>|  
|<span data-ttu-id="37f6a-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37f6a-709">CARDINALITY</span></span>|<span data-ttu-id="37f6a-710">十进制</span><span class="sxs-lookup"><span data-stu-id="37f6a-710">Decimal</span></span>|  
|<span data-ttu-id="37f6a-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="37f6a-711">PAGES</span></span>|<span data-ttu-id="37f6a-712">Int32</span><span class="sxs-lookup"><span data-stu-id="37f6a-712">Int32</span></span>|  
|<span data-ttu-id="37f6a-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37f6a-713">FILTER_CONDITION</span></span>|<span data-ttu-id="37f6a-714">String</span><span class="sxs-lookup"><span data-stu-id="37f6a-714">String</span></span>|  
|<span data-ttu-id="37f6a-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37f6a-715">INTEGRATED</span></span>|<span data-ttu-id="37f6a-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="37f6a-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37f6a-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="37f6a-717">See also</span></span>

- [<span data-ttu-id="37f6a-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="37f6a-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
