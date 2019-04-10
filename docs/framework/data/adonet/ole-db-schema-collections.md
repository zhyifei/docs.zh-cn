---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164679"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="d3b45-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="d3b45-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="d3b45-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="d3b45-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="d3b45-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="d3b45-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="d3b45-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="d3b45-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d3b45-106">表</span><span class="sxs-lookup"><span data-stu-id="d3b45-106">Tables</span></span>  
  
-   <span data-ttu-id="d3b45-107">列</span><span class="sxs-lookup"><span data-stu-id="d3b45-107">Columns</span></span>  
  
-   <span data-ttu-id="d3b45-108">过程</span><span class="sxs-lookup"><span data-stu-id="d3b45-108">Procedures</span></span>  
  
-   <span data-ttu-id="d3b45-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d3b45-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d3b45-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="d3b45-110">Catalog</span></span>  
  
-   <span data-ttu-id="d3b45-111">索引</span><span class="sxs-lookup"><span data-stu-id="d3b45-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d3b45-112">表</span><span class="sxs-lookup"><span data-stu-id="d3b45-112">Tables</span></span>  
  
|<span data-ttu-id="d3b45-113">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-113">ColumnName</span></span>|<span data-ttu-id="d3b45-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-115">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-116">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-116">String</span></span>|  
|<span data-ttu-id="d3b45-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-118">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-118">String</span></span>|  
|<span data-ttu-id="d3b45-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-119">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-120">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-120">String</span></span>|  
|<span data-ttu-id="d3b45-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-121">TABLE_TYPE</span></span>|<span data-ttu-id="d3b45-122">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-122">String</span></span>|  
|<span data-ttu-id="d3b45-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-123">TABLE_GUID</span></span>|<span data-ttu-id="d3b45-124">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-124">Guid</span></span>|  
|<span data-ttu-id="d3b45-125">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-125">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-126">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-126">String</span></span>|  
|<span data-ttu-id="d3b45-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-127">TABLE_PROPID</span></span>|<span data-ttu-id="d3b45-128">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-128">Int64</span></span>|  
|<span data-ttu-id="d3b45-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-129">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-130">DateTime</span></span>|  
|<span data-ttu-id="d3b45-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-131">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d3b45-133">列</span><span class="sxs-lookup"><span data-stu-id="d3b45-133">Columns</span></span>  
  
|<span data-ttu-id="d3b45-134">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-134">ColumnName</span></span>|<span data-ttu-id="d3b45-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-136">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-137">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-137">String</span></span>|  
|<span data-ttu-id="d3b45-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-139">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-139">String</span></span>|  
|<span data-ttu-id="d3b45-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-140">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-141">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-141">String</span></span>|  
|<span data-ttu-id="d3b45-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-142">COLUMN_NAME</span></span>|<span data-ttu-id="d3b45-143">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-143">String</span></span>|  
|<span data-ttu-id="d3b45-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-144">COLUMN_GUID</span></span>|<span data-ttu-id="d3b45-145">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-145">Guid</span></span>|  
|<span data-ttu-id="d3b45-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-146">COLUMN_PROPID</span></span>|<span data-ttu-id="d3b45-147">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-147">Int64</span></span>|  
|<span data-ttu-id="d3b45-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-149">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-149">Int64</span></span>|  
|<span data-ttu-id="d3b45-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d3b45-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-151">Boolean</span></span>|  
|<span data-ttu-id="d3b45-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d3b45-153">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-153">String</span></span>|  
|<span data-ttu-id="d3b45-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d3b45-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="d3b45-155">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-155">Int64</span></span>|  
|<span data-ttu-id="d3b45-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d3b45-156">IS_NULLABLE</span></span>|<span data-ttu-id="d3b45-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-157">Boolean</span></span>|  
|<span data-ttu-id="d3b45-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-158">DATA_TYPE</span></span>|<span data-ttu-id="d3b45-159">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-159">Int32</span></span>|  
|<span data-ttu-id="d3b45-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-160">TYPE_GUID</span></span>|<span data-ttu-id="d3b45-161">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-161">Guid</span></span>|  
|<span data-ttu-id="d3b45-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d3b45-163">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-163">Int64</span></span>|  
|<span data-ttu-id="d3b45-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d3b45-165">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-165">Int64</span></span>|  
|<span data-ttu-id="d3b45-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d3b45-167">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-167">Int32</span></span>|  
|<span data-ttu-id="d3b45-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d3b45-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="d3b45-169">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-169">Int16</span></span>|  
|<span data-ttu-id="d3b45-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="d3b45-171">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-171">Int64</span></span>|  
|<span data-ttu-id="d3b45-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d3b45-173">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-173">String</span></span>|  
|<span data-ttu-id="d3b45-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d3b45-175">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-175">String</span></span>|  
|<span data-ttu-id="d3b45-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d3b45-177">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-177">String</span></span>|  
|<span data-ttu-id="d3b45-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="d3b45-179">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-179">String</span></span>|  
|<span data-ttu-id="d3b45-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d3b45-181">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-181">String</span></span>|  
|<span data-ttu-id="d3b45-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-182">COLLATION_NAME</span></span>|<span data-ttu-id="d3b45-183">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-183">String</span></span>|  
|<span data-ttu-id="d3b45-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d3b45-185">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-185">String</span></span>|  
|<span data-ttu-id="d3b45-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d3b45-187">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-187">String</span></span>|  
|<span data-ttu-id="d3b45-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-188">DOMAIN_NAME</span></span>|<span data-ttu-id="d3b45-189">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-189">String</span></span>|  
|<span data-ttu-id="d3b45-190">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-190">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-191">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-191">String</span></span>|  
|<span data-ttu-id="d3b45-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="d3b45-192">COLUMN_LCID</span></span>|<span data-ttu-id="d3b45-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-193">Int32</span></span>|  
|<span data-ttu-id="d3b45-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="d3b45-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="d3b45-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-195">Int32</span></span>|  
|<span data-ttu-id="d3b45-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="d3b45-196">COLUMN_SORTID</span></span>|<span data-ttu-id="d3b45-197">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-197">Int32</span></span>|  
|<span data-ttu-id="d3b45-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="d3b45-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="d3b45-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="d3b45-199">Byte[]</span></span>|  
|<span data-ttu-id="d3b45-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="d3b45-200">IS_COMPUTED</span></span>|<span data-ttu-id="d3b45-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d3b45-202">过程</span><span class="sxs-lookup"><span data-stu-id="d3b45-202">Procedures</span></span>  
  
|<span data-ttu-id="d3b45-203">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-203">ColumnName</span></span>|<span data-ttu-id="d3b45-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d3b45-206">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-206">String</span></span>|  
|<span data-ttu-id="d3b45-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d3b45-208">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-208">String</span></span>|  
|<span data-ttu-id="d3b45-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="d3b45-210">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-210">String</span></span>|  
|<span data-ttu-id="d3b45-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d3b45-212">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-212">Int16</span></span>|  
|<span data-ttu-id="d3b45-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d3b45-214">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-214">String</span></span>|  
|<span data-ttu-id="d3b45-215">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-215">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-216">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-216">String</span></span>|  
|<span data-ttu-id="d3b45-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-217">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-218">DateTime</span></span>|  
|<span data-ttu-id="d3b45-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-219">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d3b45-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d3b45-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d3b45-222">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-222">ColumnName</span></span>|<span data-ttu-id="d3b45-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d3b45-225">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-225">String</span></span>|  
|<span data-ttu-id="d3b45-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d3b45-227">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-227">String</span></span>|  
|<span data-ttu-id="d3b45-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="d3b45-229">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-229">String</span></span>|  
|<span data-ttu-id="d3b45-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-230">PARAMETER_NAME</span></span>|<span data-ttu-id="d3b45-231">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-231">String</span></span>|  
|<span data-ttu-id="d3b45-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-233">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-233">Int32</span></span>|  
|<span data-ttu-id="d3b45-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="d3b45-235">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-235">Int32</span></span>|  
|<span data-ttu-id="d3b45-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="d3b45-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-237">Boolean</span></span>|  
|<span data-ttu-id="d3b45-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="d3b45-239">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-239">String</span></span>|  
|<span data-ttu-id="d3b45-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d3b45-240">IS_NULLABLE</span></span>|<span data-ttu-id="d3b45-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-241">Boolean</span></span>|  
|<span data-ttu-id="d3b45-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-242">DATA_TYPE</span></span>|<span data-ttu-id="d3b45-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-243">Int32</span></span>|  
|<span data-ttu-id="d3b45-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d3b45-245">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-245">Int64</span></span>|  
|<span data-ttu-id="d3b45-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d3b45-247">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-247">Int64</span></span>|  
|<span data-ttu-id="d3b45-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d3b45-249">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-249">Int32</span></span>|  
|<span data-ttu-id="d3b45-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d3b45-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="d3b45-251">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-251">Int16</span></span>|  
|<span data-ttu-id="d3b45-252">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-252">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-253">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-253">String</span></span>|  
|<span data-ttu-id="d3b45-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-254">TYPE_NAME</span></span>|<span data-ttu-id="d3b45-255">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-255">String</span></span>|  
|<span data-ttu-id="d3b45-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="d3b45-257">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="d3b45-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d3b45-258">Catalog</span></span>  
  
|<span data-ttu-id="d3b45-259">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-259">ColumnName</span></span>|<span data-ttu-id="d3b45-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-261">CATALOG_NAME</span></span>|<span data-ttu-id="d3b45-262">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-262">String</span></span>|  
|<span data-ttu-id="d3b45-263">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-263">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-264">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d3b45-265">索引</span><span class="sxs-lookup"><span data-stu-id="d3b45-265">Indexes</span></span>  
  
|<span data-ttu-id="d3b45-266">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-266">ColumnName</span></span>|<span data-ttu-id="d3b45-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-268">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-269">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-269">String</span></span>|  
|<span data-ttu-id="d3b45-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-271">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-271">String</span></span>|  
|<span data-ttu-id="d3b45-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-272">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-273">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-273">String</span></span>|  
|<span data-ttu-id="d3b45-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-274">INDEX_CATALOG</span></span>|<span data-ttu-id="d3b45-275">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-275">String</span></span>|  
|<span data-ttu-id="d3b45-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="d3b45-277">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-277">String</span></span>|  
|<span data-ttu-id="d3b45-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-278">INDEX_NAME</span></span>|<span data-ttu-id="d3b45-279">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-279">String</span></span>|  
|<span data-ttu-id="d3b45-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d3b45-280">PRIMARY_KEY</span></span>|<span data-ttu-id="d3b45-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-281">Boolean</span></span>|  
|<span data-ttu-id="d3b45-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d3b45-282">UNIQUE</span></span>|<span data-ttu-id="d3b45-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-283">Boolean</span></span>|  
|<span data-ttu-id="d3b45-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d3b45-284">CLUSTERED</span></span>|<span data-ttu-id="d3b45-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-285">Boolean</span></span>|  
|<span data-ttu-id="d3b45-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-286">TYPE</span></span>|<span data-ttu-id="d3b45-287">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-287">Int32</span></span>|  
|<span data-ttu-id="d3b45-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d3b45-288">FILL_FACTOR</span></span>|<span data-ttu-id="d3b45-289">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-289">Int32</span></span>|  
|<span data-ttu-id="d3b45-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d3b45-290">INITIAL_SIZE</span></span>|<span data-ttu-id="d3b45-291">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-291">Int32</span></span>|  
|<span data-ttu-id="d3b45-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="d3b45-292">NULLS</span></span>|<span data-ttu-id="d3b45-293">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-293">Int32</span></span>|  
|<span data-ttu-id="d3b45-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d3b45-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d3b45-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-295">Boolean</span></span>|  
|<span data-ttu-id="d3b45-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d3b45-296">AUTO_UPDATE</span></span>|<span data-ttu-id="d3b45-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-297">Boolean</span></span>|  
|<span data-ttu-id="d3b45-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d3b45-298">NULL_COLLATION</span></span>|<span data-ttu-id="d3b45-299">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-299">Int32</span></span>|  
|<span data-ttu-id="d3b45-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-301">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-301">Int64</span></span>|  
|<span data-ttu-id="d3b45-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-302">COLUMN_NAME</span></span>|<span data-ttu-id="d3b45-303">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-303">String</span></span>|  
|<span data-ttu-id="d3b45-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-304">COLUMN_GUID</span></span>|<span data-ttu-id="d3b45-305">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-305">Guid</span></span>|  
|<span data-ttu-id="d3b45-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-306">COLUMN_PROPID</span></span>|<span data-ttu-id="d3b45-307">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-307">Int64</span></span>|  
|<span data-ttu-id="d3b45-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d3b45-308">COLLATION</span></span>|<span data-ttu-id="d3b45-309">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-309">Int16</span></span>|  
|<span data-ttu-id="d3b45-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d3b45-310">CARDINALITY</span></span>|<span data-ttu-id="d3b45-311">十进制</span><span class="sxs-lookup"><span data-stu-id="d3b45-311">Decimal</span></span>|  
|<span data-ttu-id="d3b45-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="d3b45-312">PAGES</span></span>|<span data-ttu-id="d3b45-313">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-313">Int32</span></span>|  
|<span data-ttu-id="d3b45-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-314">FILTER_CONDITION</span></span>|<span data-ttu-id="d3b45-315">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-315">String</span></span>|  
|<span data-ttu-id="d3b45-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-316">INTEGRATED</span></span>|<span data-ttu-id="d3b45-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="d3b45-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="d3b45-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="d3b45-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="d3b45-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d3b45-320">表</span><span class="sxs-lookup"><span data-stu-id="d3b45-320">Tables</span></span>  
  
-   <span data-ttu-id="d3b45-321">列</span><span class="sxs-lookup"><span data-stu-id="d3b45-321">Columns</span></span>  
  
-   <span data-ttu-id="d3b45-322">过程</span><span class="sxs-lookup"><span data-stu-id="d3b45-322">Procedures</span></span>  
  
-   <span data-ttu-id="d3b45-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d3b45-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d3b45-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d3b45-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d3b45-325">Views</span><span class="sxs-lookup"><span data-stu-id="d3b45-325">Views</span></span>  
  
-   <span data-ttu-id="d3b45-326">索引</span><span class="sxs-lookup"><span data-stu-id="d3b45-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d3b45-327">表</span><span class="sxs-lookup"><span data-stu-id="d3b45-327">Tables</span></span>  
  
|<span data-ttu-id="d3b45-328">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-328">ColumnName</span></span>|<span data-ttu-id="d3b45-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-330">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-331">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-331">String</span></span>|  
|<span data-ttu-id="d3b45-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-333">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-333">String</span></span>|  
|<span data-ttu-id="d3b45-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-334">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-335">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-335">String</span></span>|  
|<span data-ttu-id="d3b45-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-336">TABLE_TYPE</span></span>|<span data-ttu-id="d3b45-337">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-337">String</span></span>|  
|<span data-ttu-id="d3b45-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-338">TABLE_GUID</span></span>|<span data-ttu-id="d3b45-339">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-339">Guid</span></span>|  
|<span data-ttu-id="d3b45-340">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-340">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-341">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-341">String</span></span>|  
|<span data-ttu-id="d3b45-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-342">TABLE_PROPID</span></span>|<span data-ttu-id="d3b45-343">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-343">Int64</span></span>|  
|<span data-ttu-id="d3b45-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-344">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-345">DateTime</span></span>|  
|<span data-ttu-id="d3b45-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-346">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d3b45-348">列</span><span class="sxs-lookup"><span data-stu-id="d3b45-348">Columns</span></span>  
  
|<span data-ttu-id="d3b45-349">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-349">ColumnName</span></span>|<span data-ttu-id="d3b45-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-351">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-352">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-352">String</span></span>|  
|<span data-ttu-id="d3b45-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-354">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-354">String</span></span>|  
|<span data-ttu-id="d3b45-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-355">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-356">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-356">String</span></span>|  
|<span data-ttu-id="d3b45-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-357">COLUMN_NAME</span></span>|<span data-ttu-id="d3b45-358">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-358">String</span></span>|  
|<span data-ttu-id="d3b45-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-359">COLUMN_GUID</span></span>|<span data-ttu-id="d3b45-360">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-360">Guid</span></span>|  
|<span data-ttu-id="d3b45-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-361">COLUMN_PROPID</span></span>|<span data-ttu-id="d3b45-362">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-362">Int64</span></span>|  
|<span data-ttu-id="d3b45-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-364">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-364">Int64</span></span>|  
|<span data-ttu-id="d3b45-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d3b45-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-366">Boolean</span></span>|  
|<span data-ttu-id="d3b45-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d3b45-368">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-368">String</span></span>|  
|<span data-ttu-id="d3b45-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d3b45-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="d3b45-370">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-370">Int64</span></span>|  
|<span data-ttu-id="d3b45-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d3b45-371">IS_NULLABLE</span></span>|<span data-ttu-id="d3b45-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-372">Boolean</span></span>|  
|<span data-ttu-id="d3b45-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-373">DATA_TYPE</span></span>|<span data-ttu-id="d3b45-374">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-374">Int32</span></span>|  
|<span data-ttu-id="d3b45-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-375">TYPE_GUID</span></span>|<span data-ttu-id="d3b45-376">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-376">Guid</span></span>|  
|<span data-ttu-id="d3b45-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d3b45-378">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-378">Int64</span></span>|  
|<span data-ttu-id="d3b45-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d3b45-380">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-380">Int64</span></span>|  
|<span data-ttu-id="d3b45-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d3b45-382">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-382">Int32</span></span>|  
|<span data-ttu-id="d3b45-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d3b45-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="d3b45-384">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-384">Int16</span></span>|  
|<span data-ttu-id="d3b45-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="d3b45-386">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-386">Int64</span></span>|  
|<span data-ttu-id="d3b45-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d3b45-388">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-388">String</span></span>|  
|<span data-ttu-id="d3b45-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d3b45-390">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-390">String</span></span>|  
|<span data-ttu-id="d3b45-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d3b45-392">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-392">String</span></span>|  
|<span data-ttu-id="d3b45-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="d3b45-394">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-394">String</span></span>|  
|<span data-ttu-id="d3b45-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d3b45-396">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-396">String</span></span>|  
|<span data-ttu-id="d3b45-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-397">COLLATION_NAME</span></span>|<span data-ttu-id="d3b45-398">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-398">String</span></span>|  
|<span data-ttu-id="d3b45-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d3b45-400">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-400">String</span></span>|  
|<span data-ttu-id="d3b45-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d3b45-402">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-402">String</span></span>|  
|<span data-ttu-id="d3b45-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-403">DOMAIN_NAME</span></span>|<span data-ttu-id="d3b45-404">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-404">String</span></span>|  
|<span data-ttu-id="d3b45-405">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-405">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-406">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d3b45-407">过程</span><span class="sxs-lookup"><span data-stu-id="d3b45-407">Procedures</span></span>  
  
|<span data-ttu-id="d3b45-408">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-408">ColumnName</span></span>|<span data-ttu-id="d3b45-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d3b45-411">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-411">String</span></span>|  
|<span data-ttu-id="d3b45-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d3b45-413">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-413">String</span></span>|  
|<span data-ttu-id="d3b45-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="d3b45-415">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-415">String</span></span>|  
|<span data-ttu-id="d3b45-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d3b45-417">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-417">Int16</span></span>|  
|<span data-ttu-id="d3b45-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d3b45-419">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-419">String</span></span>|  
|<span data-ttu-id="d3b45-420">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-420">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-421">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-421">String</span></span>|  
|<span data-ttu-id="d3b45-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-422">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-423">DateTime</span></span>|  
|<span data-ttu-id="d3b45-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-424">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d3b45-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d3b45-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d3b45-427">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-427">ColumnName</span></span>|<span data-ttu-id="d3b45-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d3b45-430">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-430">String</span></span>|  
|<span data-ttu-id="d3b45-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d3b45-432">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-432">String</span></span>|  
|<span data-ttu-id="d3b45-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="d3b45-434">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-434">String</span></span>|  
|<span data-ttu-id="d3b45-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-435">COLUMN_NAME</span></span>|<span data-ttu-id="d3b45-436">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-436">String</span></span>|  
|<span data-ttu-id="d3b45-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-437">COLUMN_GUID</span></span>|<span data-ttu-id="d3b45-438">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-438">Guid</span></span>|  
|<span data-ttu-id="d3b45-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-439">COLUMN_PROPID</span></span>|<span data-ttu-id="d3b45-440">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-440">Int64</span></span>|  
|<span data-ttu-id="d3b45-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="d3b45-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="d3b45-442">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-442">Int64</span></span>|  
|<span data-ttu-id="d3b45-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-444">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-444">Int64</span></span>|  
|<span data-ttu-id="d3b45-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d3b45-445">IS_NULLABLE</span></span>|<span data-ttu-id="d3b45-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-446">Boolean</span></span>|  
|<span data-ttu-id="d3b45-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-447">DATA_TYPE</span></span>|<span data-ttu-id="d3b45-448">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-448">Int32</span></span>|  
|<span data-ttu-id="d3b45-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-449">TYPE_GUID</span></span>|<span data-ttu-id="d3b45-450">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-450">Guid</span></span>|  
|<span data-ttu-id="d3b45-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d3b45-452">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-452">Int64</span></span>|  
|<span data-ttu-id="d3b45-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d3b45-454">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-454">Int64</span></span>|  
|<span data-ttu-id="d3b45-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d3b45-456">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-456">Int32</span></span>|  
|<span data-ttu-id="d3b45-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d3b45-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="d3b45-458">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-458">Int16</span></span>|  
|<span data-ttu-id="d3b45-459">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-459">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-460">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-460">String</span></span>|  
|<span data-ttu-id="d3b45-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d3b45-461">OVERLOAD</span></span>|<span data-ttu-id="d3b45-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d3b45-463">Views</span><span class="sxs-lookup"><span data-stu-id="d3b45-463">Views</span></span>  
  
|<span data-ttu-id="d3b45-464">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-464">ColumnName</span></span>|<span data-ttu-id="d3b45-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-466">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-467">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-467">String</span></span>|  
|<span data-ttu-id="d3b45-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-469">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-469">String</span></span>|  
|<span data-ttu-id="d3b45-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-470">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-471">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-471">String</span></span>|  
|<span data-ttu-id="d3b45-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="d3b45-473">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-473">String</span></span>|  
|<span data-ttu-id="d3b45-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d3b45-474">CHECK_OPTION</span></span>|<span data-ttu-id="d3b45-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-475">Boolean</span></span>|  
|<span data-ttu-id="d3b45-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d3b45-476">IS_UPDATABLE</span></span>|<span data-ttu-id="d3b45-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-477">Boolean</span></span>|  
|<span data-ttu-id="d3b45-478">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-478">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-479">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-479">String</span></span>|  
|<span data-ttu-id="d3b45-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-480">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-481">DateTime</span></span>|  
|<span data-ttu-id="d3b45-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-482">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d3b45-484">索引</span><span class="sxs-lookup"><span data-stu-id="d3b45-484">Indexes</span></span>  
  
|<span data-ttu-id="d3b45-485">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-485">ColumnName</span></span>|<span data-ttu-id="d3b45-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-487">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-488">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-488">String</span></span>|  
|<span data-ttu-id="d3b45-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-490">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-490">String</span></span>|  
|<span data-ttu-id="d3b45-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-491">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-492">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-492">String</span></span>|  
|<span data-ttu-id="d3b45-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-493">INDEX_CATALOG</span></span>|<span data-ttu-id="d3b45-494">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-494">String</span></span>|  
|<span data-ttu-id="d3b45-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="d3b45-496">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-496">String</span></span>|  
|<span data-ttu-id="d3b45-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-497">INDEX_NAME</span></span>|<span data-ttu-id="d3b45-498">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-498">String</span></span>|  
|<span data-ttu-id="d3b45-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d3b45-499">PRIMARY_KEY</span></span>|<span data-ttu-id="d3b45-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-500">Boolean</span></span>|  
|<span data-ttu-id="d3b45-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d3b45-501">UNIQUE</span></span>|<span data-ttu-id="d3b45-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-502">Boolean</span></span>|  
|<span data-ttu-id="d3b45-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d3b45-503">CLUSTERED</span></span>|<span data-ttu-id="d3b45-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-504">Boolean</span></span>|  
|<span data-ttu-id="d3b45-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-505">TYPE</span></span>|<span data-ttu-id="d3b45-506">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-506">Int32</span></span>|  
|<span data-ttu-id="d3b45-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d3b45-507">FILL_FACTOR</span></span>|<span data-ttu-id="d3b45-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-508">Int32</span></span>|  
|<span data-ttu-id="d3b45-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d3b45-509">INITIAL_SIZE</span></span>|<span data-ttu-id="d3b45-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-510">Int32</span></span>|  
|<span data-ttu-id="d3b45-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="d3b45-511">NULLS</span></span>|<span data-ttu-id="d3b45-512">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-512">Int32</span></span>|  
|<span data-ttu-id="d3b45-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d3b45-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d3b45-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-514">Boolean</span></span>|  
|<span data-ttu-id="d3b45-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d3b45-515">AUTO_UPDATE</span></span>|<span data-ttu-id="d3b45-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-516">Boolean</span></span>|  
|<span data-ttu-id="d3b45-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d3b45-517">NULL_COLLATION</span></span>|<span data-ttu-id="d3b45-518">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-518">Int32</span></span>|  
|<span data-ttu-id="d3b45-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-520">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-520">Int64</span></span>|  
|<span data-ttu-id="d3b45-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-521">COLUMN_NAME</span></span>|<span data-ttu-id="d3b45-522">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-522">String</span></span>|  
|<span data-ttu-id="d3b45-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-523">COLUMN_GUID</span></span>|<span data-ttu-id="d3b45-524">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-524">Guid</span></span>|  
|<span data-ttu-id="d3b45-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-525">COLUMN_PROPID</span></span>|<span data-ttu-id="d3b45-526">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-526">Int64</span></span>|  
|<span data-ttu-id="d3b45-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d3b45-527">COLLATION</span></span>|<span data-ttu-id="d3b45-528">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-528">Int16</span></span>|  
|<span data-ttu-id="d3b45-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d3b45-529">CARDINALITY</span></span>|<span data-ttu-id="d3b45-530">十进制</span><span class="sxs-lookup"><span data-stu-id="d3b45-530">Decimal</span></span>|  
|<span data-ttu-id="d3b45-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="d3b45-531">PAGES</span></span>|<span data-ttu-id="d3b45-532">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-532">Int32</span></span>|  
|<span data-ttu-id="d3b45-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-533">FILTER_CONDITION</span></span>|<span data-ttu-id="d3b45-534">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-534">String</span></span>|  
|<span data-ttu-id="d3b45-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-535">INTEGRATED</span></span>|<span data-ttu-id="d3b45-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="d3b45-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="d3b45-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="d3b45-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="d3b45-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d3b45-539">表</span><span class="sxs-lookup"><span data-stu-id="d3b45-539">Tables</span></span>  
  
-   <span data-ttu-id="d3b45-540">列</span><span class="sxs-lookup"><span data-stu-id="d3b45-540">Columns</span></span>  
  
-   <span data-ttu-id="d3b45-541">过程</span><span class="sxs-lookup"><span data-stu-id="d3b45-541">Procedures</span></span>  
  
-   <span data-ttu-id="d3b45-542">Views</span><span class="sxs-lookup"><span data-stu-id="d3b45-542">Views</span></span>  
  
-   <span data-ttu-id="d3b45-543">索引</span><span class="sxs-lookup"><span data-stu-id="d3b45-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d3b45-544">表</span><span class="sxs-lookup"><span data-stu-id="d3b45-544">Tables</span></span>  
  
|<span data-ttu-id="d3b45-545">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-545">ColumnName</span></span>|<span data-ttu-id="d3b45-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-547">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-548">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-548">String</span></span>|  
|<span data-ttu-id="d3b45-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-550">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-550">String</span></span>|  
|<span data-ttu-id="d3b45-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-551">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-552">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-552">String</span></span>|  
|<span data-ttu-id="d3b45-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-553">TABLE_TYPE</span></span>|<span data-ttu-id="d3b45-554">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-554">String</span></span>|  
|<span data-ttu-id="d3b45-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-555">TABLE_GUID</span></span>|<span data-ttu-id="d3b45-556">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-556">Guid</span></span>|  
|<span data-ttu-id="d3b45-557">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-557">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-558">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-558">String</span></span>|  
|<span data-ttu-id="d3b45-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-559">TABLE_PROPID</span></span>|<span data-ttu-id="d3b45-560">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-560">Int64</span></span>|  
|<span data-ttu-id="d3b45-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-561">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-562">DateTime</span></span>|  
|<span data-ttu-id="d3b45-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-563">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d3b45-565">列</span><span class="sxs-lookup"><span data-stu-id="d3b45-565">Columns</span></span>  
  
|<span data-ttu-id="d3b45-566">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-566">ColumnName</span></span>|<span data-ttu-id="d3b45-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-568">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-569">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-569">String</span></span>|  
|<span data-ttu-id="d3b45-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-571">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-571">String</span></span>|  
|<span data-ttu-id="d3b45-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-572">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-573">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-573">String</span></span>|  
|<span data-ttu-id="d3b45-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-574">COLUMN_NAME</span></span>|<span data-ttu-id="d3b45-575">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-575">String</span></span>|  
|<span data-ttu-id="d3b45-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-576">COLUMN_GUID</span></span>|<span data-ttu-id="d3b45-577">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-577">Guid</span></span>|  
|<span data-ttu-id="d3b45-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-578">COLUMN_PROPID</span></span>|<span data-ttu-id="d3b45-579">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-579">Int64</span></span>|  
|<span data-ttu-id="d3b45-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-581">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-581">Int64</span></span>|  
|<span data-ttu-id="d3b45-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d3b45-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-583">Boolean</span></span>|  
|<span data-ttu-id="d3b45-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d3b45-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d3b45-585">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-585">String</span></span>|  
|<span data-ttu-id="d3b45-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d3b45-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="d3b45-587">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-587">Int64</span></span>|  
|<span data-ttu-id="d3b45-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d3b45-588">IS_NULLABLE</span></span>|<span data-ttu-id="d3b45-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-589">Boolean</span></span>|  
|<span data-ttu-id="d3b45-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-590">DATA_TYPE</span></span>|<span data-ttu-id="d3b45-591">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-591">Int32</span></span>|  
|<span data-ttu-id="d3b45-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-592">TYPE_GUID</span></span>|<span data-ttu-id="d3b45-593">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-593">Guid</span></span>|  
|<span data-ttu-id="d3b45-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d3b45-595">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-595">Int64</span></span>|  
|<span data-ttu-id="d3b45-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d3b45-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d3b45-597">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-597">Int64</span></span>|  
|<span data-ttu-id="d3b45-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d3b45-599">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-599">Int32</span></span>|  
|<span data-ttu-id="d3b45-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d3b45-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="d3b45-601">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-601">Int16</span></span>|  
|<span data-ttu-id="d3b45-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d3b45-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="d3b45-603">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-603">Int64</span></span>|  
|<span data-ttu-id="d3b45-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d3b45-605">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-605">String</span></span>|  
|<span data-ttu-id="d3b45-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d3b45-607">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-607">String</span></span>|  
|<span data-ttu-id="d3b45-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d3b45-609">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-609">String</span></span>|  
|<span data-ttu-id="d3b45-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="d3b45-611">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-611">String</span></span>|  
|<span data-ttu-id="d3b45-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d3b45-613">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-613">String</span></span>|  
|<span data-ttu-id="d3b45-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-614">COLLATION_NAME</span></span>|<span data-ttu-id="d3b45-615">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-615">String</span></span>|  
|<span data-ttu-id="d3b45-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d3b45-617">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-617">String</span></span>|  
|<span data-ttu-id="d3b45-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d3b45-619">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-619">String</span></span>|  
|<span data-ttu-id="d3b45-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-620">DOMAIN_NAME</span></span>|<span data-ttu-id="d3b45-621">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-621">String</span></span>|  
|<span data-ttu-id="d3b45-622">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-622">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-623">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d3b45-624">过程</span><span class="sxs-lookup"><span data-stu-id="d3b45-624">Procedures</span></span>  
  
|<span data-ttu-id="d3b45-625">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-625">ColumnName</span></span>|<span data-ttu-id="d3b45-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d3b45-628">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-628">String</span></span>|  
|<span data-ttu-id="d3b45-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d3b45-630">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-630">String</span></span>|  
|<span data-ttu-id="d3b45-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="d3b45-632">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-632">String</span></span>|  
|<span data-ttu-id="d3b45-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d3b45-634">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-634">Int16</span></span>|  
|<span data-ttu-id="d3b45-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d3b45-636">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-636">String</span></span>|  
|<span data-ttu-id="d3b45-637">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-637">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-638">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-638">String</span></span>|  
|<span data-ttu-id="d3b45-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-639">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-640">DateTime</span></span>|  
|<span data-ttu-id="d3b45-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-641">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d3b45-643">Views</span><span class="sxs-lookup"><span data-stu-id="d3b45-643">Views</span></span>  
  
|<span data-ttu-id="d3b45-644">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-644">ColumnName</span></span>|<span data-ttu-id="d3b45-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-646">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-647">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-647">String</span></span>|  
|<span data-ttu-id="d3b45-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-649">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-649">String</span></span>|  
|<span data-ttu-id="d3b45-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-650">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-651">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-651">String</span></span>|  
|<span data-ttu-id="d3b45-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="d3b45-653">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-653">String</span></span>|  
|<span data-ttu-id="d3b45-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d3b45-654">CHECK_OPTION</span></span>|<span data-ttu-id="d3b45-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-655">Boolean</span></span>|  
|<span data-ttu-id="d3b45-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d3b45-656">IS_UPDATABLE</span></span>|<span data-ttu-id="d3b45-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-657">Boolean</span></span>|  
|<span data-ttu-id="d3b45-658">描述</span><span class="sxs-lookup"><span data-stu-id="d3b45-658">DESCRIPTION</span></span>|<span data-ttu-id="d3b45-659">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-659">String</span></span>|  
|<span data-ttu-id="d3b45-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-660">DATE_CREATED</span></span>|<span data-ttu-id="d3b45-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-661">DateTime</span></span>|  
|<span data-ttu-id="d3b45-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d3b45-662">DATE_MODIFIED</span></span>|<span data-ttu-id="d3b45-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3b45-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d3b45-664">索引</span><span class="sxs-lookup"><span data-stu-id="d3b45-664">Indexes</span></span>  
  
|<span data-ttu-id="d3b45-665">列名</span><span class="sxs-lookup"><span data-stu-id="d3b45-665">ColumnName</span></span>|<span data-ttu-id="d3b45-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="d3b45-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d3b45-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-667">TABLE_CATALOG</span></span>|<span data-ttu-id="d3b45-668">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-668">String</span></span>|  
|<span data-ttu-id="d3b45-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="d3b45-670">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-670">String</span></span>|  
|<span data-ttu-id="d3b45-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-671">TABLE_NAME</span></span>|<span data-ttu-id="d3b45-672">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-672">String</span></span>|  
|<span data-ttu-id="d3b45-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d3b45-673">INDEX_CATALOG</span></span>|<span data-ttu-id="d3b45-674">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-674">String</span></span>|  
|<span data-ttu-id="d3b45-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d3b45-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="d3b45-676">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-676">String</span></span>|  
|<span data-ttu-id="d3b45-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-677">INDEX_NAME</span></span>|<span data-ttu-id="d3b45-678">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-678">String</span></span>|  
|<span data-ttu-id="d3b45-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d3b45-679">PRIMARY_KEY</span></span>|<span data-ttu-id="d3b45-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-680">Boolean</span></span>|  
|<span data-ttu-id="d3b45-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d3b45-681">UNIQUE</span></span>|<span data-ttu-id="d3b45-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-682">Boolean</span></span>|  
|<span data-ttu-id="d3b45-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d3b45-683">CLUSTERED</span></span>|<span data-ttu-id="d3b45-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-684">Boolean</span></span>|  
|<span data-ttu-id="d3b45-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="d3b45-685">TYPE</span></span>|<span data-ttu-id="d3b45-686">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-686">Int32</span></span>|  
|<span data-ttu-id="d3b45-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d3b45-687">FILL_FACTOR</span></span>|<span data-ttu-id="d3b45-688">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-688">Int32</span></span>|  
|<span data-ttu-id="d3b45-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d3b45-689">INITIAL_SIZE</span></span>|<span data-ttu-id="d3b45-690">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-690">Int32</span></span>|  
|<span data-ttu-id="d3b45-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="d3b45-691">NULLS</span></span>|<span data-ttu-id="d3b45-692">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-692">Int32</span></span>|  
|<span data-ttu-id="d3b45-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d3b45-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d3b45-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-694">Boolean</span></span>|  
|<span data-ttu-id="d3b45-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d3b45-695">AUTO_UPDATE</span></span>|<span data-ttu-id="d3b45-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-696">Boolean</span></span>|  
|<span data-ttu-id="d3b45-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d3b45-697">NULL_COLLATION</span></span>|<span data-ttu-id="d3b45-698">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-698">Int32</span></span>|  
|<span data-ttu-id="d3b45-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="d3b45-700">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-700">Int64</span></span>|  
|<span data-ttu-id="d3b45-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d3b45-701">COLUMN_NAME</span></span>|<span data-ttu-id="d3b45-702">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-702">String</span></span>|  
|<span data-ttu-id="d3b45-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-703">COLUMN_GUID</span></span>|<span data-ttu-id="d3b45-704">GUID</span><span class="sxs-lookup"><span data-stu-id="d3b45-704">Guid</span></span>|  
|<span data-ttu-id="d3b45-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d3b45-705">COLUMN_PROPID</span></span>|<span data-ttu-id="d3b45-706">Int64</span><span class="sxs-lookup"><span data-stu-id="d3b45-706">Int64</span></span>|  
|<span data-ttu-id="d3b45-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d3b45-707">COLLATION</span></span>|<span data-ttu-id="d3b45-708">Int16</span><span class="sxs-lookup"><span data-stu-id="d3b45-708">Int16</span></span>|  
|<span data-ttu-id="d3b45-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d3b45-709">CARDINALITY</span></span>|<span data-ttu-id="d3b45-710">十进制</span><span class="sxs-lookup"><span data-stu-id="d3b45-710">Decimal</span></span>|  
|<span data-ttu-id="d3b45-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="d3b45-711">PAGES</span></span>|<span data-ttu-id="d3b45-712">Int32</span><span class="sxs-lookup"><span data-stu-id="d3b45-712">Int32</span></span>|  
|<span data-ttu-id="d3b45-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d3b45-713">FILTER_CONDITION</span></span>|<span data-ttu-id="d3b45-714">String</span><span class="sxs-lookup"><span data-stu-id="d3b45-714">String</span></span>|  
|<span data-ttu-id="d3b45-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d3b45-715">INTEGRATED</span></span>|<span data-ttu-id="d3b45-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="d3b45-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3b45-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3b45-717">See also</span></span>

- [<span data-ttu-id="d3b45-718">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d3b45-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
