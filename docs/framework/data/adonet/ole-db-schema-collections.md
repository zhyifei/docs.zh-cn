---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164679"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="45864-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="45864-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="45864-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="45864-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="45864-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="45864-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="45864-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="45864-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="45864-106">表</span><span class="sxs-lookup"><span data-stu-id="45864-106">Tables</span></span>  
  
-   <span data-ttu-id="45864-107">列</span><span class="sxs-lookup"><span data-stu-id="45864-107">Columns</span></span>  
  
-   <span data-ttu-id="45864-108">过程</span><span class="sxs-lookup"><span data-stu-id="45864-108">Procedures</span></span>  
  
-   <span data-ttu-id="45864-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="45864-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="45864-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="45864-110">Catalog</span></span>  
  
-   <span data-ttu-id="45864-111">索引</span><span class="sxs-lookup"><span data-stu-id="45864-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="45864-112">表</span><span class="sxs-lookup"><span data-stu-id="45864-112">Tables</span></span>  
  
|<span data-ttu-id="45864-113">列名</span><span class="sxs-lookup"><span data-stu-id="45864-113">ColumnName</span></span>|<span data-ttu-id="45864-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-115">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-116">String</span><span class="sxs-lookup"><span data-stu-id="45864-116">String</span></span>|  
|<span data-ttu-id="45864-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-118">String</span><span class="sxs-lookup"><span data-stu-id="45864-118">String</span></span>|  
|<span data-ttu-id="45864-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-119">TABLE_NAME</span></span>|<span data-ttu-id="45864-120">String</span><span class="sxs-lookup"><span data-stu-id="45864-120">String</span></span>|  
|<span data-ttu-id="45864-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-121">TABLE_TYPE</span></span>|<span data-ttu-id="45864-122">String</span><span class="sxs-lookup"><span data-stu-id="45864-122">String</span></span>|  
|<span data-ttu-id="45864-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-123">TABLE_GUID</span></span>|<span data-ttu-id="45864-124">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-124">Guid</span></span>|  
|<span data-ttu-id="45864-125">描述</span><span class="sxs-lookup"><span data-stu-id="45864-125">DESCRIPTION</span></span>|<span data-ttu-id="45864-126">String</span><span class="sxs-lookup"><span data-stu-id="45864-126">String</span></span>|  
|<span data-ttu-id="45864-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-127">TABLE_PROPID</span></span>|<span data-ttu-id="45864-128">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-128">Int64</span></span>|  
|<span data-ttu-id="45864-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-129">DATE_CREATED</span></span>|<span data-ttu-id="45864-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-130">DateTime</span></span>|  
|<span data-ttu-id="45864-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-131">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="45864-133">列</span><span class="sxs-lookup"><span data-stu-id="45864-133">Columns</span></span>  
  
|<span data-ttu-id="45864-134">列名</span><span class="sxs-lookup"><span data-stu-id="45864-134">ColumnName</span></span>|<span data-ttu-id="45864-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-136">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-137">String</span><span class="sxs-lookup"><span data-stu-id="45864-137">String</span></span>|  
|<span data-ttu-id="45864-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-139">String</span><span class="sxs-lookup"><span data-stu-id="45864-139">String</span></span>|  
|<span data-ttu-id="45864-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-140">TABLE_NAME</span></span>|<span data-ttu-id="45864-141">String</span><span class="sxs-lookup"><span data-stu-id="45864-141">String</span></span>|  
|<span data-ttu-id="45864-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-142">COLUMN_NAME</span></span>|<span data-ttu-id="45864-143">String</span><span class="sxs-lookup"><span data-stu-id="45864-143">String</span></span>|  
|<span data-ttu-id="45864-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-144">COLUMN_GUID</span></span>|<span data-ttu-id="45864-145">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-145">Guid</span></span>|  
|<span data-ttu-id="45864-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-146">COLUMN_PROPID</span></span>|<span data-ttu-id="45864-147">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-147">Int64</span></span>|  
|<span data-ttu-id="45864-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-149">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-149">Int64</span></span>|  
|<span data-ttu-id="45864-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="45864-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-151">Boolean</span></span>|  
|<span data-ttu-id="45864-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="45864-153">String</span><span class="sxs-lookup"><span data-stu-id="45864-153">String</span></span>|  
|<span data-ttu-id="45864-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="45864-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="45864-155">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-155">Int64</span></span>|  
|<span data-ttu-id="45864-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="45864-156">IS_NULLABLE</span></span>|<span data-ttu-id="45864-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-157">Boolean</span></span>|  
|<span data-ttu-id="45864-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-158">DATA_TYPE</span></span>|<span data-ttu-id="45864-159">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-159">Int32</span></span>|  
|<span data-ttu-id="45864-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-160">TYPE_GUID</span></span>|<span data-ttu-id="45864-161">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-161">Guid</span></span>|  
|<span data-ttu-id="45864-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="45864-163">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-163">Int64</span></span>|  
|<span data-ttu-id="45864-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="45864-165">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-165">Int64</span></span>|  
|<span data-ttu-id="45864-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="45864-167">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-167">Int32</span></span>|  
|<span data-ttu-id="45864-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="45864-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="45864-169">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-169">Int16</span></span>|  
|<span data-ttu-id="45864-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="45864-171">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-171">Int64</span></span>|  
|<span data-ttu-id="45864-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="45864-173">String</span><span class="sxs-lookup"><span data-stu-id="45864-173">String</span></span>|  
|<span data-ttu-id="45864-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="45864-175">String</span><span class="sxs-lookup"><span data-stu-id="45864-175">String</span></span>|  
|<span data-ttu-id="45864-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="45864-177">String</span><span class="sxs-lookup"><span data-stu-id="45864-177">String</span></span>|  
|<span data-ttu-id="45864-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="45864-179">String</span><span class="sxs-lookup"><span data-stu-id="45864-179">String</span></span>|  
|<span data-ttu-id="45864-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="45864-181">String</span><span class="sxs-lookup"><span data-stu-id="45864-181">String</span></span>|  
|<span data-ttu-id="45864-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-182">COLLATION_NAME</span></span>|<span data-ttu-id="45864-183">String</span><span class="sxs-lookup"><span data-stu-id="45864-183">String</span></span>|  
|<span data-ttu-id="45864-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="45864-185">String</span><span class="sxs-lookup"><span data-stu-id="45864-185">String</span></span>|  
|<span data-ttu-id="45864-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="45864-187">String</span><span class="sxs-lookup"><span data-stu-id="45864-187">String</span></span>|  
|<span data-ttu-id="45864-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-188">DOMAIN_NAME</span></span>|<span data-ttu-id="45864-189">String</span><span class="sxs-lookup"><span data-stu-id="45864-189">String</span></span>|  
|<span data-ttu-id="45864-190">描述</span><span class="sxs-lookup"><span data-stu-id="45864-190">DESCRIPTION</span></span>|<span data-ttu-id="45864-191">String</span><span class="sxs-lookup"><span data-stu-id="45864-191">String</span></span>|  
|<span data-ttu-id="45864-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="45864-192">COLUMN_LCID</span></span>|<span data-ttu-id="45864-193">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-193">Int32</span></span>|  
|<span data-ttu-id="45864-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="45864-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="45864-195">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-195">Int32</span></span>|  
|<span data-ttu-id="45864-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="45864-196">COLUMN_SORTID</span></span>|<span data-ttu-id="45864-197">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-197">Int32</span></span>|  
|<span data-ttu-id="45864-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="45864-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="45864-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="45864-199">Byte[]</span></span>|  
|<span data-ttu-id="45864-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="45864-200">IS_COMPUTED</span></span>|<span data-ttu-id="45864-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="45864-202">过程</span><span class="sxs-lookup"><span data-stu-id="45864-202">Procedures</span></span>  
  
|<span data-ttu-id="45864-203">列名</span><span class="sxs-lookup"><span data-stu-id="45864-203">ColumnName</span></span>|<span data-ttu-id="45864-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="45864-206">String</span><span class="sxs-lookup"><span data-stu-id="45864-206">String</span></span>|  
|<span data-ttu-id="45864-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="45864-208">String</span><span class="sxs-lookup"><span data-stu-id="45864-208">String</span></span>|  
|<span data-ttu-id="45864-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="45864-210">String</span><span class="sxs-lookup"><span data-stu-id="45864-210">String</span></span>|  
|<span data-ttu-id="45864-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="45864-212">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-212">Int16</span></span>|  
|<span data-ttu-id="45864-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="45864-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="45864-214">String</span><span class="sxs-lookup"><span data-stu-id="45864-214">String</span></span>|  
|<span data-ttu-id="45864-215">描述</span><span class="sxs-lookup"><span data-stu-id="45864-215">DESCRIPTION</span></span>|<span data-ttu-id="45864-216">String</span><span class="sxs-lookup"><span data-stu-id="45864-216">String</span></span>|  
|<span data-ttu-id="45864-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-217">DATE_CREATED</span></span>|<span data-ttu-id="45864-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-218">DateTime</span></span>|  
|<span data-ttu-id="45864-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-219">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="45864-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="45864-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="45864-222">列名</span><span class="sxs-lookup"><span data-stu-id="45864-222">ColumnName</span></span>|<span data-ttu-id="45864-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="45864-225">String</span><span class="sxs-lookup"><span data-stu-id="45864-225">String</span></span>|  
|<span data-ttu-id="45864-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="45864-227">String</span><span class="sxs-lookup"><span data-stu-id="45864-227">String</span></span>|  
|<span data-ttu-id="45864-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="45864-229">String</span><span class="sxs-lookup"><span data-stu-id="45864-229">String</span></span>|  
|<span data-ttu-id="45864-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-230">PARAMETER_NAME</span></span>|<span data-ttu-id="45864-231">String</span><span class="sxs-lookup"><span data-stu-id="45864-231">String</span></span>|  
|<span data-ttu-id="45864-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-233">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-233">Int32</span></span>|  
|<span data-ttu-id="45864-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="45864-235">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-235">Int32</span></span>|  
|<span data-ttu-id="45864-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="45864-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-237">Boolean</span></span>|  
|<span data-ttu-id="45864-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="45864-239">String</span><span class="sxs-lookup"><span data-stu-id="45864-239">String</span></span>|  
|<span data-ttu-id="45864-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="45864-240">IS_NULLABLE</span></span>|<span data-ttu-id="45864-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-241">Boolean</span></span>|  
|<span data-ttu-id="45864-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-242">DATA_TYPE</span></span>|<span data-ttu-id="45864-243">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-243">Int32</span></span>|  
|<span data-ttu-id="45864-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="45864-245">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-245">Int64</span></span>|  
|<span data-ttu-id="45864-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="45864-247">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-247">Int64</span></span>|  
|<span data-ttu-id="45864-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="45864-249">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-249">Int32</span></span>|  
|<span data-ttu-id="45864-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="45864-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="45864-251">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-251">Int16</span></span>|  
|<span data-ttu-id="45864-252">描述</span><span class="sxs-lookup"><span data-stu-id="45864-252">DESCRIPTION</span></span>|<span data-ttu-id="45864-253">String</span><span class="sxs-lookup"><span data-stu-id="45864-253">String</span></span>|  
|<span data-ttu-id="45864-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-254">TYPE_NAME</span></span>|<span data-ttu-id="45864-255">String</span><span class="sxs-lookup"><span data-stu-id="45864-255">String</span></span>|  
|<span data-ttu-id="45864-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="45864-257">String</span><span class="sxs-lookup"><span data-stu-id="45864-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="45864-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="45864-258">Catalog</span></span>  
  
|<span data-ttu-id="45864-259">列名</span><span class="sxs-lookup"><span data-stu-id="45864-259">ColumnName</span></span>|<span data-ttu-id="45864-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-261">CATALOG_NAME</span></span>|<span data-ttu-id="45864-262">String</span><span class="sxs-lookup"><span data-stu-id="45864-262">String</span></span>|  
|<span data-ttu-id="45864-263">描述</span><span class="sxs-lookup"><span data-stu-id="45864-263">DESCRIPTION</span></span>|<span data-ttu-id="45864-264">String</span><span class="sxs-lookup"><span data-stu-id="45864-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="45864-265">索引</span><span class="sxs-lookup"><span data-stu-id="45864-265">Indexes</span></span>  
  
|<span data-ttu-id="45864-266">列名</span><span class="sxs-lookup"><span data-stu-id="45864-266">ColumnName</span></span>|<span data-ttu-id="45864-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-268">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-269">String</span><span class="sxs-lookup"><span data-stu-id="45864-269">String</span></span>|  
|<span data-ttu-id="45864-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-271">String</span><span class="sxs-lookup"><span data-stu-id="45864-271">String</span></span>|  
|<span data-ttu-id="45864-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-272">TABLE_NAME</span></span>|<span data-ttu-id="45864-273">String</span><span class="sxs-lookup"><span data-stu-id="45864-273">String</span></span>|  
|<span data-ttu-id="45864-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-274">INDEX_CATALOG</span></span>|<span data-ttu-id="45864-275">String</span><span class="sxs-lookup"><span data-stu-id="45864-275">String</span></span>|  
|<span data-ttu-id="45864-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="45864-277">String</span><span class="sxs-lookup"><span data-stu-id="45864-277">String</span></span>|  
|<span data-ttu-id="45864-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-278">INDEX_NAME</span></span>|<span data-ttu-id="45864-279">String</span><span class="sxs-lookup"><span data-stu-id="45864-279">String</span></span>|  
|<span data-ttu-id="45864-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="45864-280">PRIMARY_KEY</span></span>|<span data-ttu-id="45864-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-281">Boolean</span></span>|  
|<span data-ttu-id="45864-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="45864-282">UNIQUE</span></span>|<span data-ttu-id="45864-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-283">Boolean</span></span>|  
|<span data-ttu-id="45864-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="45864-284">CLUSTERED</span></span>|<span data-ttu-id="45864-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-285">Boolean</span></span>|  
|<span data-ttu-id="45864-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-286">TYPE</span></span>|<span data-ttu-id="45864-287">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-287">Int32</span></span>|  
|<span data-ttu-id="45864-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="45864-288">FILL_FACTOR</span></span>|<span data-ttu-id="45864-289">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-289">Int32</span></span>|  
|<span data-ttu-id="45864-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="45864-290">INITIAL_SIZE</span></span>|<span data-ttu-id="45864-291">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-291">Int32</span></span>|  
|<span data-ttu-id="45864-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="45864-292">NULLS</span></span>|<span data-ttu-id="45864-293">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-293">Int32</span></span>|  
|<span data-ttu-id="45864-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="45864-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="45864-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-295">Boolean</span></span>|  
|<span data-ttu-id="45864-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="45864-296">AUTO_UPDATE</span></span>|<span data-ttu-id="45864-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-297">Boolean</span></span>|  
|<span data-ttu-id="45864-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="45864-298">NULL_COLLATION</span></span>|<span data-ttu-id="45864-299">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-299">Int32</span></span>|  
|<span data-ttu-id="45864-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-301">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-301">Int64</span></span>|  
|<span data-ttu-id="45864-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-302">COLUMN_NAME</span></span>|<span data-ttu-id="45864-303">String</span><span class="sxs-lookup"><span data-stu-id="45864-303">String</span></span>|  
|<span data-ttu-id="45864-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-304">COLUMN_GUID</span></span>|<span data-ttu-id="45864-305">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-305">Guid</span></span>|  
|<span data-ttu-id="45864-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-306">COLUMN_PROPID</span></span>|<span data-ttu-id="45864-307">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-307">Int64</span></span>|  
|<span data-ttu-id="45864-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="45864-308">COLLATION</span></span>|<span data-ttu-id="45864-309">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-309">Int16</span></span>|  
|<span data-ttu-id="45864-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="45864-310">CARDINALITY</span></span>|<span data-ttu-id="45864-311">十进制</span><span class="sxs-lookup"><span data-stu-id="45864-311">Decimal</span></span>|  
|<span data-ttu-id="45864-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="45864-312">PAGES</span></span>|<span data-ttu-id="45864-313">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-313">Int32</span></span>|  
|<span data-ttu-id="45864-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="45864-314">FILTER_CONDITION</span></span>|<span data-ttu-id="45864-315">String</span><span class="sxs-lookup"><span data-stu-id="45864-315">String</span></span>|  
|<span data-ttu-id="45864-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="45864-316">INTEGRATED</span></span>|<span data-ttu-id="45864-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="45864-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="45864-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="45864-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="45864-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="45864-320">表</span><span class="sxs-lookup"><span data-stu-id="45864-320">Tables</span></span>  
  
-   <span data-ttu-id="45864-321">列</span><span class="sxs-lookup"><span data-stu-id="45864-321">Columns</span></span>  
  
-   <span data-ttu-id="45864-322">过程</span><span class="sxs-lookup"><span data-stu-id="45864-322">Procedures</span></span>  
  
-   <span data-ttu-id="45864-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="45864-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="45864-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="45864-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="45864-325">Views</span><span class="sxs-lookup"><span data-stu-id="45864-325">Views</span></span>  
  
-   <span data-ttu-id="45864-326">索引</span><span class="sxs-lookup"><span data-stu-id="45864-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="45864-327">表</span><span class="sxs-lookup"><span data-stu-id="45864-327">Tables</span></span>  
  
|<span data-ttu-id="45864-328">列名</span><span class="sxs-lookup"><span data-stu-id="45864-328">ColumnName</span></span>|<span data-ttu-id="45864-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-330">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-331">String</span><span class="sxs-lookup"><span data-stu-id="45864-331">String</span></span>|  
|<span data-ttu-id="45864-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-333">String</span><span class="sxs-lookup"><span data-stu-id="45864-333">String</span></span>|  
|<span data-ttu-id="45864-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-334">TABLE_NAME</span></span>|<span data-ttu-id="45864-335">String</span><span class="sxs-lookup"><span data-stu-id="45864-335">String</span></span>|  
|<span data-ttu-id="45864-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-336">TABLE_TYPE</span></span>|<span data-ttu-id="45864-337">String</span><span class="sxs-lookup"><span data-stu-id="45864-337">String</span></span>|  
|<span data-ttu-id="45864-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-338">TABLE_GUID</span></span>|<span data-ttu-id="45864-339">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-339">Guid</span></span>|  
|<span data-ttu-id="45864-340">描述</span><span class="sxs-lookup"><span data-stu-id="45864-340">DESCRIPTION</span></span>|<span data-ttu-id="45864-341">String</span><span class="sxs-lookup"><span data-stu-id="45864-341">String</span></span>|  
|<span data-ttu-id="45864-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-342">TABLE_PROPID</span></span>|<span data-ttu-id="45864-343">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-343">Int64</span></span>|  
|<span data-ttu-id="45864-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-344">DATE_CREATED</span></span>|<span data-ttu-id="45864-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-345">DateTime</span></span>|  
|<span data-ttu-id="45864-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-346">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="45864-348">列</span><span class="sxs-lookup"><span data-stu-id="45864-348">Columns</span></span>  
  
|<span data-ttu-id="45864-349">列名</span><span class="sxs-lookup"><span data-stu-id="45864-349">ColumnName</span></span>|<span data-ttu-id="45864-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-351">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-352">String</span><span class="sxs-lookup"><span data-stu-id="45864-352">String</span></span>|  
|<span data-ttu-id="45864-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-354">String</span><span class="sxs-lookup"><span data-stu-id="45864-354">String</span></span>|  
|<span data-ttu-id="45864-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-355">TABLE_NAME</span></span>|<span data-ttu-id="45864-356">String</span><span class="sxs-lookup"><span data-stu-id="45864-356">String</span></span>|  
|<span data-ttu-id="45864-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-357">COLUMN_NAME</span></span>|<span data-ttu-id="45864-358">String</span><span class="sxs-lookup"><span data-stu-id="45864-358">String</span></span>|  
|<span data-ttu-id="45864-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-359">COLUMN_GUID</span></span>|<span data-ttu-id="45864-360">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-360">Guid</span></span>|  
|<span data-ttu-id="45864-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-361">COLUMN_PROPID</span></span>|<span data-ttu-id="45864-362">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-362">Int64</span></span>|  
|<span data-ttu-id="45864-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-364">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-364">Int64</span></span>|  
|<span data-ttu-id="45864-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="45864-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-366">Boolean</span></span>|  
|<span data-ttu-id="45864-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="45864-368">String</span><span class="sxs-lookup"><span data-stu-id="45864-368">String</span></span>|  
|<span data-ttu-id="45864-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="45864-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="45864-370">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-370">Int64</span></span>|  
|<span data-ttu-id="45864-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="45864-371">IS_NULLABLE</span></span>|<span data-ttu-id="45864-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-372">Boolean</span></span>|  
|<span data-ttu-id="45864-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-373">DATA_TYPE</span></span>|<span data-ttu-id="45864-374">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-374">Int32</span></span>|  
|<span data-ttu-id="45864-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-375">TYPE_GUID</span></span>|<span data-ttu-id="45864-376">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-376">Guid</span></span>|  
|<span data-ttu-id="45864-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="45864-378">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-378">Int64</span></span>|  
|<span data-ttu-id="45864-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="45864-380">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-380">Int64</span></span>|  
|<span data-ttu-id="45864-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="45864-382">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-382">Int32</span></span>|  
|<span data-ttu-id="45864-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="45864-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="45864-384">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-384">Int16</span></span>|  
|<span data-ttu-id="45864-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="45864-386">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-386">Int64</span></span>|  
|<span data-ttu-id="45864-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="45864-388">String</span><span class="sxs-lookup"><span data-stu-id="45864-388">String</span></span>|  
|<span data-ttu-id="45864-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="45864-390">String</span><span class="sxs-lookup"><span data-stu-id="45864-390">String</span></span>|  
|<span data-ttu-id="45864-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="45864-392">String</span><span class="sxs-lookup"><span data-stu-id="45864-392">String</span></span>|  
|<span data-ttu-id="45864-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="45864-394">String</span><span class="sxs-lookup"><span data-stu-id="45864-394">String</span></span>|  
|<span data-ttu-id="45864-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="45864-396">String</span><span class="sxs-lookup"><span data-stu-id="45864-396">String</span></span>|  
|<span data-ttu-id="45864-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-397">COLLATION_NAME</span></span>|<span data-ttu-id="45864-398">String</span><span class="sxs-lookup"><span data-stu-id="45864-398">String</span></span>|  
|<span data-ttu-id="45864-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="45864-400">String</span><span class="sxs-lookup"><span data-stu-id="45864-400">String</span></span>|  
|<span data-ttu-id="45864-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="45864-402">String</span><span class="sxs-lookup"><span data-stu-id="45864-402">String</span></span>|  
|<span data-ttu-id="45864-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-403">DOMAIN_NAME</span></span>|<span data-ttu-id="45864-404">String</span><span class="sxs-lookup"><span data-stu-id="45864-404">String</span></span>|  
|<span data-ttu-id="45864-405">描述</span><span class="sxs-lookup"><span data-stu-id="45864-405">DESCRIPTION</span></span>|<span data-ttu-id="45864-406">String</span><span class="sxs-lookup"><span data-stu-id="45864-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="45864-407">过程</span><span class="sxs-lookup"><span data-stu-id="45864-407">Procedures</span></span>  
  
|<span data-ttu-id="45864-408">列名</span><span class="sxs-lookup"><span data-stu-id="45864-408">ColumnName</span></span>|<span data-ttu-id="45864-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="45864-411">String</span><span class="sxs-lookup"><span data-stu-id="45864-411">String</span></span>|  
|<span data-ttu-id="45864-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="45864-413">String</span><span class="sxs-lookup"><span data-stu-id="45864-413">String</span></span>|  
|<span data-ttu-id="45864-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="45864-415">String</span><span class="sxs-lookup"><span data-stu-id="45864-415">String</span></span>|  
|<span data-ttu-id="45864-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="45864-417">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-417">Int16</span></span>|  
|<span data-ttu-id="45864-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="45864-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="45864-419">String</span><span class="sxs-lookup"><span data-stu-id="45864-419">String</span></span>|  
|<span data-ttu-id="45864-420">描述</span><span class="sxs-lookup"><span data-stu-id="45864-420">DESCRIPTION</span></span>|<span data-ttu-id="45864-421">String</span><span class="sxs-lookup"><span data-stu-id="45864-421">String</span></span>|  
|<span data-ttu-id="45864-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-422">DATE_CREATED</span></span>|<span data-ttu-id="45864-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-423">DateTime</span></span>|  
|<span data-ttu-id="45864-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-424">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="45864-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="45864-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="45864-427">列名</span><span class="sxs-lookup"><span data-stu-id="45864-427">ColumnName</span></span>|<span data-ttu-id="45864-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="45864-430">String</span><span class="sxs-lookup"><span data-stu-id="45864-430">String</span></span>|  
|<span data-ttu-id="45864-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="45864-432">String</span><span class="sxs-lookup"><span data-stu-id="45864-432">String</span></span>|  
|<span data-ttu-id="45864-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="45864-434">String</span><span class="sxs-lookup"><span data-stu-id="45864-434">String</span></span>|  
|<span data-ttu-id="45864-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-435">COLUMN_NAME</span></span>|<span data-ttu-id="45864-436">String</span><span class="sxs-lookup"><span data-stu-id="45864-436">String</span></span>|  
|<span data-ttu-id="45864-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-437">COLUMN_GUID</span></span>|<span data-ttu-id="45864-438">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-438">Guid</span></span>|  
|<span data-ttu-id="45864-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-439">COLUMN_PROPID</span></span>|<span data-ttu-id="45864-440">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-440">Int64</span></span>|  
|<span data-ttu-id="45864-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="45864-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="45864-442">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-442">Int64</span></span>|  
|<span data-ttu-id="45864-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-444">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-444">Int64</span></span>|  
|<span data-ttu-id="45864-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="45864-445">IS_NULLABLE</span></span>|<span data-ttu-id="45864-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-446">Boolean</span></span>|  
|<span data-ttu-id="45864-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-447">DATA_TYPE</span></span>|<span data-ttu-id="45864-448">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-448">Int32</span></span>|  
|<span data-ttu-id="45864-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-449">TYPE_GUID</span></span>|<span data-ttu-id="45864-450">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-450">Guid</span></span>|  
|<span data-ttu-id="45864-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="45864-452">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-452">Int64</span></span>|  
|<span data-ttu-id="45864-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="45864-454">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-454">Int64</span></span>|  
|<span data-ttu-id="45864-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="45864-456">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-456">Int32</span></span>|  
|<span data-ttu-id="45864-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="45864-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="45864-458">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-458">Int16</span></span>|  
|<span data-ttu-id="45864-459">描述</span><span class="sxs-lookup"><span data-stu-id="45864-459">DESCRIPTION</span></span>|<span data-ttu-id="45864-460">String</span><span class="sxs-lookup"><span data-stu-id="45864-460">String</span></span>|  
|<span data-ttu-id="45864-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="45864-461">OVERLOAD</span></span>|<span data-ttu-id="45864-462">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="45864-463">Views</span><span class="sxs-lookup"><span data-stu-id="45864-463">Views</span></span>  
  
|<span data-ttu-id="45864-464">列名</span><span class="sxs-lookup"><span data-stu-id="45864-464">ColumnName</span></span>|<span data-ttu-id="45864-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-466">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-467">String</span><span class="sxs-lookup"><span data-stu-id="45864-467">String</span></span>|  
|<span data-ttu-id="45864-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-469">String</span><span class="sxs-lookup"><span data-stu-id="45864-469">String</span></span>|  
|<span data-ttu-id="45864-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-470">TABLE_NAME</span></span>|<span data-ttu-id="45864-471">String</span><span class="sxs-lookup"><span data-stu-id="45864-471">String</span></span>|  
|<span data-ttu-id="45864-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="45864-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="45864-473">String</span><span class="sxs-lookup"><span data-stu-id="45864-473">String</span></span>|  
|<span data-ttu-id="45864-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="45864-474">CHECK_OPTION</span></span>|<span data-ttu-id="45864-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-475">Boolean</span></span>|  
|<span data-ttu-id="45864-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="45864-476">IS_UPDATABLE</span></span>|<span data-ttu-id="45864-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-477">Boolean</span></span>|  
|<span data-ttu-id="45864-478">描述</span><span class="sxs-lookup"><span data-stu-id="45864-478">DESCRIPTION</span></span>|<span data-ttu-id="45864-479">String</span><span class="sxs-lookup"><span data-stu-id="45864-479">String</span></span>|  
|<span data-ttu-id="45864-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-480">DATE_CREATED</span></span>|<span data-ttu-id="45864-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-481">DateTime</span></span>|  
|<span data-ttu-id="45864-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-482">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="45864-484">索引</span><span class="sxs-lookup"><span data-stu-id="45864-484">Indexes</span></span>  
  
|<span data-ttu-id="45864-485">列名</span><span class="sxs-lookup"><span data-stu-id="45864-485">ColumnName</span></span>|<span data-ttu-id="45864-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-487">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-488">String</span><span class="sxs-lookup"><span data-stu-id="45864-488">String</span></span>|  
|<span data-ttu-id="45864-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-490">String</span><span class="sxs-lookup"><span data-stu-id="45864-490">String</span></span>|  
|<span data-ttu-id="45864-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-491">TABLE_NAME</span></span>|<span data-ttu-id="45864-492">String</span><span class="sxs-lookup"><span data-stu-id="45864-492">String</span></span>|  
|<span data-ttu-id="45864-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-493">INDEX_CATALOG</span></span>|<span data-ttu-id="45864-494">String</span><span class="sxs-lookup"><span data-stu-id="45864-494">String</span></span>|  
|<span data-ttu-id="45864-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="45864-496">String</span><span class="sxs-lookup"><span data-stu-id="45864-496">String</span></span>|  
|<span data-ttu-id="45864-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-497">INDEX_NAME</span></span>|<span data-ttu-id="45864-498">String</span><span class="sxs-lookup"><span data-stu-id="45864-498">String</span></span>|  
|<span data-ttu-id="45864-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="45864-499">PRIMARY_KEY</span></span>|<span data-ttu-id="45864-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-500">Boolean</span></span>|  
|<span data-ttu-id="45864-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="45864-501">UNIQUE</span></span>|<span data-ttu-id="45864-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-502">Boolean</span></span>|  
|<span data-ttu-id="45864-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="45864-503">CLUSTERED</span></span>|<span data-ttu-id="45864-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-504">Boolean</span></span>|  
|<span data-ttu-id="45864-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-505">TYPE</span></span>|<span data-ttu-id="45864-506">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-506">Int32</span></span>|  
|<span data-ttu-id="45864-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="45864-507">FILL_FACTOR</span></span>|<span data-ttu-id="45864-508">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-508">Int32</span></span>|  
|<span data-ttu-id="45864-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="45864-509">INITIAL_SIZE</span></span>|<span data-ttu-id="45864-510">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-510">Int32</span></span>|  
|<span data-ttu-id="45864-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="45864-511">NULLS</span></span>|<span data-ttu-id="45864-512">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-512">Int32</span></span>|  
|<span data-ttu-id="45864-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="45864-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="45864-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-514">Boolean</span></span>|  
|<span data-ttu-id="45864-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="45864-515">AUTO_UPDATE</span></span>|<span data-ttu-id="45864-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-516">Boolean</span></span>|  
|<span data-ttu-id="45864-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="45864-517">NULL_COLLATION</span></span>|<span data-ttu-id="45864-518">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-518">Int32</span></span>|  
|<span data-ttu-id="45864-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-520">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-520">Int64</span></span>|  
|<span data-ttu-id="45864-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-521">COLUMN_NAME</span></span>|<span data-ttu-id="45864-522">String</span><span class="sxs-lookup"><span data-stu-id="45864-522">String</span></span>|  
|<span data-ttu-id="45864-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-523">COLUMN_GUID</span></span>|<span data-ttu-id="45864-524">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-524">Guid</span></span>|  
|<span data-ttu-id="45864-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-525">COLUMN_PROPID</span></span>|<span data-ttu-id="45864-526">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-526">Int64</span></span>|  
|<span data-ttu-id="45864-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="45864-527">COLLATION</span></span>|<span data-ttu-id="45864-528">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-528">Int16</span></span>|  
|<span data-ttu-id="45864-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="45864-529">CARDINALITY</span></span>|<span data-ttu-id="45864-530">十进制</span><span class="sxs-lookup"><span data-stu-id="45864-530">Decimal</span></span>|  
|<span data-ttu-id="45864-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="45864-531">PAGES</span></span>|<span data-ttu-id="45864-532">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-532">Int32</span></span>|  
|<span data-ttu-id="45864-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="45864-533">FILTER_CONDITION</span></span>|<span data-ttu-id="45864-534">String</span><span class="sxs-lookup"><span data-stu-id="45864-534">String</span></span>|  
|<span data-ttu-id="45864-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="45864-535">INTEGRATED</span></span>|<span data-ttu-id="45864-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="45864-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="45864-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="45864-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="45864-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="45864-539">表</span><span class="sxs-lookup"><span data-stu-id="45864-539">Tables</span></span>  
  
-   <span data-ttu-id="45864-540">列</span><span class="sxs-lookup"><span data-stu-id="45864-540">Columns</span></span>  
  
-   <span data-ttu-id="45864-541">过程</span><span class="sxs-lookup"><span data-stu-id="45864-541">Procedures</span></span>  
  
-   <span data-ttu-id="45864-542">Views</span><span class="sxs-lookup"><span data-stu-id="45864-542">Views</span></span>  
  
-   <span data-ttu-id="45864-543">索引</span><span class="sxs-lookup"><span data-stu-id="45864-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="45864-544">表</span><span class="sxs-lookup"><span data-stu-id="45864-544">Tables</span></span>  
  
|<span data-ttu-id="45864-545">列名</span><span class="sxs-lookup"><span data-stu-id="45864-545">ColumnName</span></span>|<span data-ttu-id="45864-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-547">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-548">String</span><span class="sxs-lookup"><span data-stu-id="45864-548">String</span></span>|  
|<span data-ttu-id="45864-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-550">String</span><span class="sxs-lookup"><span data-stu-id="45864-550">String</span></span>|  
|<span data-ttu-id="45864-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-551">TABLE_NAME</span></span>|<span data-ttu-id="45864-552">String</span><span class="sxs-lookup"><span data-stu-id="45864-552">String</span></span>|  
|<span data-ttu-id="45864-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-553">TABLE_TYPE</span></span>|<span data-ttu-id="45864-554">String</span><span class="sxs-lookup"><span data-stu-id="45864-554">String</span></span>|  
|<span data-ttu-id="45864-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-555">TABLE_GUID</span></span>|<span data-ttu-id="45864-556">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-556">Guid</span></span>|  
|<span data-ttu-id="45864-557">描述</span><span class="sxs-lookup"><span data-stu-id="45864-557">DESCRIPTION</span></span>|<span data-ttu-id="45864-558">String</span><span class="sxs-lookup"><span data-stu-id="45864-558">String</span></span>|  
|<span data-ttu-id="45864-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-559">TABLE_PROPID</span></span>|<span data-ttu-id="45864-560">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-560">Int64</span></span>|  
|<span data-ttu-id="45864-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-561">DATE_CREATED</span></span>|<span data-ttu-id="45864-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-562">DateTime</span></span>|  
|<span data-ttu-id="45864-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-563">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="45864-565">列</span><span class="sxs-lookup"><span data-stu-id="45864-565">Columns</span></span>  
  
|<span data-ttu-id="45864-566">列名</span><span class="sxs-lookup"><span data-stu-id="45864-566">ColumnName</span></span>|<span data-ttu-id="45864-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-568">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-569">String</span><span class="sxs-lookup"><span data-stu-id="45864-569">String</span></span>|  
|<span data-ttu-id="45864-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-571">String</span><span class="sxs-lookup"><span data-stu-id="45864-571">String</span></span>|  
|<span data-ttu-id="45864-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-572">TABLE_NAME</span></span>|<span data-ttu-id="45864-573">String</span><span class="sxs-lookup"><span data-stu-id="45864-573">String</span></span>|  
|<span data-ttu-id="45864-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-574">COLUMN_NAME</span></span>|<span data-ttu-id="45864-575">String</span><span class="sxs-lookup"><span data-stu-id="45864-575">String</span></span>|  
|<span data-ttu-id="45864-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-576">COLUMN_GUID</span></span>|<span data-ttu-id="45864-577">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-577">Guid</span></span>|  
|<span data-ttu-id="45864-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-578">COLUMN_PROPID</span></span>|<span data-ttu-id="45864-579">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-579">Int64</span></span>|  
|<span data-ttu-id="45864-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-581">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-581">Int64</span></span>|  
|<span data-ttu-id="45864-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="45864-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-583">Boolean</span></span>|  
|<span data-ttu-id="45864-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="45864-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="45864-585">String</span><span class="sxs-lookup"><span data-stu-id="45864-585">String</span></span>|  
|<span data-ttu-id="45864-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="45864-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="45864-587">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-587">Int64</span></span>|  
|<span data-ttu-id="45864-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="45864-588">IS_NULLABLE</span></span>|<span data-ttu-id="45864-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-589">Boolean</span></span>|  
|<span data-ttu-id="45864-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-590">DATA_TYPE</span></span>|<span data-ttu-id="45864-591">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-591">Int32</span></span>|  
|<span data-ttu-id="45864-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-592">TYPE_GUID</span></span>|<span data-ttu-id="45864-593">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-593">Guid</span></span>|  
|<span data-ttu-id="45864-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="45864-595">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-595">Int64</span></span>|  
|<span data-ttu-id="45864-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="45864-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="45864-597">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-597">Int64</span></span>|  
|<span data-ttu-id="45864-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="45864-599">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-599">Int32</span></span>|  
|<span data-ttu-id="45864-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="45864-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="45864-601">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-601">Int16</span></span>|  
|<span data-ttu-id="45864-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="45864-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="45864-603">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-603">Int64</span></span>|  
|<span data-ttu-id="45864-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="45864-605">String</span><span class="sxs-lookup"><span data-stu-id="45864-605">String</span></span>|  
|<span data-ttu-id="45864-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="45864-607">String</span><span class="sxs-lookup"><span data-stu-id="45864-607">String</span></span>|  
|<span data-ttu-id="45864-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="45864-609">String</span><span class="sxs-lookup"><span data-stu-id="45864-609">String</span></span>|  
|<span data-ttu-id="45864-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="45864-611">String</span><span class="sxs-lookup"><span data-stu-id="45864-611">String</span></span>|  
|<span data-ttu-id="45864-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="45864-613">String</span><span class="sxs-lookup"><span data-stu-id="45864-613">String</span></span>|  
|<span data-ttu-id="45864-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-614">COLLATION_NAME</span></span>|<span data-ttu-id="45864-615">String</span><span class="sxs-lookup"><span data-stu-id="45864-615">String</span></span>|  
|<span data-ttu-id="45864-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="45864-617">String</span><span class="sxs-lookup"><span data-stu-id="45864-617">String</span></span>|  
|<span data-ttu-id="45864-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="45864-619">String</span><span class="sxs-lookup"><span data-stu-id="45864-619">String</span></span>|  
|<span data-ttu-id="45864-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-620">DOMAIN_NAME</span></span>|<span data-ttu-id="45864-621">String</span><span class="sxs-lookup"><span data-stu-id="45864-621">String</span></span>|  
|<span data-ttu-id="45864-622">描述</span><span class="sxs-lookup"><span data-stu-id="45864-622">DESCRIPTION</span></span>|<span data-ttu-id="45864-623">String</span><span class="sxs-lookup"><span data-stu-id="45864-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="45864-624">过程</span><span class="sxs-lookup"><span data-stu-id="45864-624">Procedures</span></span>  
  
|<span data-ttu-id="45864-625">列名</span><span class="sxs-lookup"><span data-stu-id="45864-625">ColumnName</span></span>|<span data-ttu-id="45864-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="45864-628">String</span><span class="sxs-lookup"><span data-stu-id="45864-628">String</span></span>|  
|<span data-ttu-id="45864-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="45864-630">String</span><span class="sxs-lookup"><span data-stu-id="45864-630">String</span></span>|  
|<span data-ttu-id="45864-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="45864-632">String</span><span class="sxs-lookup"><span data-stu-id="45864-632">String</span></span>|  
|<span data-ttu-id="45864-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="45864-634">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-634">Int16</span></span>|  
|<span data-ttu-id="45864-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="45864-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="45864-636">String</span><span class="sxs-lookup"><span data-stu-id="45864-636">String</span></span>|  
|<span data-ttu-id="45864-637">描述</span><span class="sxs-lookup"><span data-stu-id="45864-637">DESCRIPTION</span></span>|<span data-ttu-id="45864-638">String</span><span class="sxs-lookup"><span data-stu-id="45864-638">String</span></span>|  
|<span data-ttu-id="45864-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-639">DATE_CREATED</span></span>|<span data-ttu-id="45864-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-640">DateTime</span></span>|  
|<span data-ttu-id="45864-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-641">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="45864-643">Views</span><span class="sxs-lookup"><span data-stu-id="45864-643">Views</span></span>  
  
|<span data-ttu-id="45864-644">列名</span><span class="sxs-lookup"><span data-stu-id="45864-644">ColumnName</span></span>|<span data-ttu-id="45864-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-646">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-647">String</span><span class="sxs-lookup"><span data-stu-id="45864-647">String</span></span>|  
|<span data-ttu-id="45864-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-649">String</span><span class="sxs-lookup"><span data-stu-id="45864-649">String</span></span>|  
|<span data-ttu-id="45864-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-650">TABLE_NAME</span></span>|<span data-ttu-id="45864-651">String</span><span class="sxs-lookup"><span data-stu-id="45864-651">String</span></span>|  
|<span data-ttu-id="45864-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="45864-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="45864-653">String</span><span class="sxs-lookup"><span data-stu-id="45864-653">String</span></span>|  
|<span data-ttu-id="45864-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="45864-654">CHECK_OPTION</span></span>|<span data-ttu-id="45864-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-655">Boolean</span></span>|  
|<span data-ttu-id="45864-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="45864-656">IS_UPDATABLE</span></span>|<span data-ttu-id="45864-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-657">Boolean</span></span>|  
|<span data-ttu-id="45864-658">描述</span><span class="sxs-lookup"><span data-stu-id="45864-658">DESCRIPTION</span></span>|<span data-ttu-id="45864-659">String</span><span class="sxs-lookup"><span data-stu-id="45864-659">String</span></span>|  
|<span data-ttu-id="45864-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="45864-660">DATE_CREATED</span></span>|<span data-ttu-id="45864-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-661">DateTime</span></span>|  
|<span data-ttu-id="45864-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="45864-662">DATE_MODIFIED</span></span>|<span data-ttu-id="45864-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="45864-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="45864-664">索引</span><span class="sxs-lookup"><span data-stu-id="45864-664">Indexes</span></span>  
  
|<span data-ttu-id="45864-665">列名</span><span class="sxs-lookup"><span data-stu-id="45864-665">ColumnName</span></span>|<span data-ttu-id="45864-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="45864-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="45864-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-667">TABLE_CATALOG</span></span>|<span data-ttu-id="45864-668">String</span><span class="sxs-lookup"><span data-stu-id="45864-668">String</span></span>|  
|<span data-ttu-id="45864-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="45864-670">String</span><span class="sxs-lookup"><span data-stu-id="45864-670">String</span></span>|  
|<span data-ttu-id="45864-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-671">TABLE_NAME</span></span>|<span data-ttu-id="45864-672">String</span><span class="sxs-lookup"><span data-stu-id="45864-672">String</span></span>|  
|<span data-ttu-id="45864-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45864-673">INDEX_CATALOG</span></span>|<span data-ttu-id="45864-674">String</span><span class="sxs-lookup"><span data-stu-id="45864-674">String</span></span>|  
|<span data-ttu-id="45864-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45864-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="45864-676">String</span><span class="sxs-lookup"><span data-stu-id="45864-676">String</span></span>|  
|<span data-ttu-id="45864-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-677">INDEX_NAME</span></span>|<span data-ttu-id="45864-678">String</span><span class="sxs-lookup"><span data-stu-id="45864-678">String</span></span>|  
|<span data-ttu-id="45864-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="45864-679">PRIMARY_KEY</span></span>|<span data-ttu-id="45864-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-680">Boolean</span></span>|  
|<span data-ttu-id="45864-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="45864-681">UNIQUE</span></span>|<span data-ttu-id="45864-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-682">Boolean</span></span>|  
|<span data-ttu-id="45864-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="45864-683">CLUSTERED</span></span>|<span data-ttu-id="45864-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-684">Boolean</span></span>|  
|<span data-ttu-id="45864-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="45864-685">TYPE</span></span>|<span data-ttu-id="45864-686">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-686">Int32</span></span>|  
|<span data-ttu-id="45864-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="45864-687">FILL_FACTOR</span></span>|<span data-ttu-id="45864-688">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-688">Int32</span></span>|  
|<span data-ttu-id="45864-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="45864-689">INITIAL_SIZE</span></span>|<span data-ttu-id="45864-690">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-690">Int32</span></span>|  
|<span data-ttu-id="45864-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="45864-691">NULLS</span></span>|<span data-ttu-id="45864-692">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-692">Int32</span></span>|  
|<span data-ttu-id="45864-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="45864-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="45864-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-694">Boolean</span></span>|  
|<span data-ttu-id="45864-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="45864-695">AUTO_UPDATE</span></span>|<span data-ttu-id="45864-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-696">Boolean</span></span>|  
|<span data-ttu-id="45864-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="45864-697">NULL_COLLATION</span></span>|<span data-ttu-id="45864-698">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-698">Int32</span></span>|  
|<span data-ttu-id="45864-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="45864-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="45864-700">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-700">Int64</span></span>|  
|<span data-ttu-id="45864-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45864-701">COLUMN_NAME</span></span>|<span data-ttu-id="45864-702">String</span><span class="sxs-lookup"><span data-stu-id="45864-702">String</span></span>|  
|<span data-ttu-id="45864-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="45864-703">COLUMN_GUID</span></span>|<span data-ttu-id="45864-704">GUID</span><span class="sxs-lookup"><span data-stu-id="45864-704">Guid</span></span>|  
|<span data-ttu-id="45864-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="45864-705">COLUMN_PROPID</span></span>|<span data-ttu-id="45864-706">Int64</span><span class="sxs-lookup"><span data-stu-id="45864-706">Int64</span></span>|  
|<span data-ttu-id="45864-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="45864-707">COLLATION</span></span>|<span data-ttu-id="45864-708">Int16</span><span class="sxs-lookup"><span data-stu-id="45864-708">Int16</span></span>|  
|<span data-ttu-id="45864-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="45864-709">CARDINALITY</span></span>|<span data-ttu-id="45864-710">十进制</span><span class="sxs-lookup"><span data-stu-id="45864-710">Decimal</span></span>|  
|<span data-ttu-id="45864-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="45864-711">PAGES</span></span>|<span data-ttu-id="45864-712">Int32</span><span class="sxs-lookup"><span data-stu-id="45864-712">Int32</span></span>|  
|<span data-ttu-id="45864-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="45864-713">FILTER_CONDITION</span></span>|<span data-ttu-id="45864-714">String</span><span class="sxs-lookup"><span data-stu-id="45864-714">String</span></span>|  
|<span data-ttu-id="45864-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="45864-715">INTEGRATED</span></span>|<span data-ttu-id="45864-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="45864-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45864-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="45864-717">See also</span></span>

- [<span data-ttu-id="45864-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="45864-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
