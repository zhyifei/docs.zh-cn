---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 1ab6426875b73b400a59b7e4cf155615d7472d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514484"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="20e97-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="20e97-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="20e97-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="20e97-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="20e97-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="20e97-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="20e97-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="20e97-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="20e97-106">表</span><span class="sxs-lookup"><span data-stu-id="20e97-106">Tables</span></span>  
  
-   <span data-ttu-id="20e97-107">Columns</span><span class="sxs-lookup"><span data-stu-id="20e97-107">Columns</span></span>  
  
-   <span data-ttu-id="20e97-108">过程</span><span class="sxs-lookup"><span data-stu-id="20e97-108">Procedures</span></span>  
  
-   <span data-ttu-id="20e97-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="20e97-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="20e97-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="20e97-110">Catalog</span></span>  
  
-   <span data-ttu-id="20e97-111">索引</span><span class="sxs-lookup"><span data-stu-id="20e97-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="20e97-112">表</span><span class="sxs-lookup"><span data-stu-id="20e97-112">Tables</span></span>  
  
|<span data-ttu-id="20e97-113">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-113">ColumnName</span></span>|<span data-ttu-id="20e97-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-115">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-116">String</span><span class="sxs-lookup"><span data-stu-id="20e97-116">String</span></span>|  
|<span data-ttu-id="20e97-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-118">String</span><span class="sxs-lookup"><span data-stu-id="20e97-118">String</span></span>|  
|<span data-ttu-id="20e97-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-119">TABLE_NAME</span></span>|<span data-ttu-id="20e97-120">String</span><span class="sxs-lookup"><span data-stu-id="20e97-120">String</span></span>|  
|<span data-ttu-id="20e97-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-121">TABLE_TYPE</span></span>|<span data-ttu-id="20e97-122">String</span><span class="sxs-lookup"><span data-stu-id="20e97-122">String</span></span>|  
|<span data-ttu-id="20e97-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-123">TABLE_GUID</span></span>|<span data-ttu-id="20e97-124">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-124">Guid</span></span>|  
|<span data-ttu-id="20e97-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-125">DESCRIPTION</span></span>|<span data-ttu-id="20e97-126">String</span><span class="sxs-lookup"><span data-stu-id="20e97-126">String</span></span>|  
|<span data-ttu-id="20e97-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-127">TABLE_PROPID</span></span>|<span data-ttu-id="20e97-128">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-128">Int64</span></span>|  
|<span data-ttu-id="20e97-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-129">DATE_CREATED</span></span>|<span data-ttu-id="20e97-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-130">DateTime</span></span>|  
|<span data-ttu-id="20e97-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-131">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="20e97-133">Columns</span><span class="sxs-lookup"><span data-stu-id="20e97-133">Columns</span></span>  
  
|<span data-ttu-id="20e97-134">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-134">ColumnName</span></span>|<span data-ttu-id="20e97-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-136">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-137">String</span><span class="sxs-lookup"><span data-stu-id="20e97-137">String</span></span>|  
|<span data-ttu-id="20e97-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-139">String</span><span class="sxs-lookup"><span data-stu-id="20e97-139">String</span></span>|  
|<span data-ttu-id="20e97-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-140">TABLE_NAME</span></span>|<span data-ttu-id="20e97-141">String</span><span class="sxs-lookup"><span data-stu-id="20e97-141">String</span></span>|  
|<span data-ttu-id="20e97-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-142">COLUMN_NAME</span></span>|<span data-ttu-id="20e97-143">String</span><span class="sxs-lookup"><span data-stu-id="20e97-143">String</span></span>|  
|<span data-ttu-id="20e97-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-144">COLUMN_GUID</span></span>|<span data-ttu-id="20e97-145">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-145">Guid</span></span>|  
|<span data-ttu-id="20e97-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-146">COLUMN_PROPID</span></span>|<span data-ttu-id="20e97-147">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-147">Int64</span></span>|  
|<span data-ttu-id="20e97-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-149">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-149">Int64</span></span>|  
|<span data-ttu-id="20e97-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="20e97-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-151">Boolean</span></span>|  
|<span data-ttu-id="20e97-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="20e97-153">String</span><span class="sxs-lookup"><span data-stu-id="20e97-153">String</span></span>|  
|<span data-ttu-id="20e97-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="20e97-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="20e97-155">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-155">Int64</span></span>|  
|<span data-ttu-id="20e97-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="20e97-156">IS_NULLABLE</span></span>|<span data-ttu-id="20e97-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-157">Boolean</span></span>|  
|<span data-ttu-id="20e97-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-158">DATA_TYPE</span></span>|<span data-ttu-id="20e97-159">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-159">Int32</span></span>|  
|<span data-ttu-id="20e97-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-160">TYPE_GUID</span></span>|<span data-ttu-id="20e97-161">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-161">Guid</span></span>|  
|<span data-ttu-id="20e97-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="20e97-163">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-163">Int64</span></span>|  
|<span data-ttu-id="20e97-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="20e97-165">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-165">Int64</span></span>|  
|<span data-ttu-id="20e97-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="20e97-167">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-167">Int32</span></span>|  
|<span data-ttu-id="20e97-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="20e97-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="20e97-169">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-169">Int16</span></span>|  
|<span data-ttu-id="20e97-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="20e97-171">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-171">Int64</span></span>|  
|<span data-ttu-id="20e97-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="20e97-173">String</span><span class="sxs-lookup"><span data-stu-id="20e97-173">String</span></span>|  
|<span data-ttu-id="20e97-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="20e97-175">String</span><span class="sxs-lookup"><span data-stu-id="20e97-175">String</span></span>|  
|<span data-ttu-id="20e97-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="20e97-177">String</span><span class="sxs-lookup"><span data-stu-id="20e97-177">String</span></span>|  
|<span data-ttu-id="20e97-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="20e97-179">String</span><span class="sxs-lookup"><span data-stu-id="20e97-179">String</span></span>|  
|<span data-ttu-id="20e97-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="20e97-181">String</span><span class="sxs-lookup"><span data-stu-id="20e97-181">String</span></span>|  
|<span data-ttu-id="20e97-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-182">COLLATION_NAME</span></span>|<span data-ttu-id="20e97-183">String</span><span class="sxs-lookup"><span data-stu-id="20e97-183">String</span></span>|  
|<span data-ttu-id="20e97-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="20e97-185">String</span><span class="sxs-lookup"><span data-stu-id="20e97-185">String</span></span>|  
|<span data-ttu-id="20e97-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="20e97-187">String</span><span class="sxs-lookup"><span data-stu-id="20e97-187">String</span></span>|  
|<span data-ttu-id="20e97-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-188">DOMAIN_NAME</span></span>|<span data-ttu-id="20e97-189">String</span><span class="sxs-lookup"><span data-stu-id="20e97-189">String</span></span>|  
|<span data-ttu-id="20e97-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-190">DESCRIPTION</span></span>|<span data-ttu-id="20e97-191">String</span><span class="sxs-lookup"><span data-stu-id="20e97-191">String</span></span>|  
|<span data-ttu-id="20e97-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="20e97-192">COLUMN_LCID</span></span>|<span data-ttu-id="20e97-193">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-193">Int32</span></span>|  
|<span data-ttu-id="20e97-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="20e97-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="20e97-195">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-195">Int32</span></span>|  
|<span data-ttu-id="20e97-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="20e97-196">COLUMN_SORTID</span></span>|<span data-ttu-id="20e97-197">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-197">Int32</span></span>|  
|<span data-ttu-id="20e97-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="20e97-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="20e97-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="20e97-199">Byte[]</span></span>|  
|<span data-ttu-id="20e97-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="20e97-200">IS_COMPUTED</span></span>|<span data-ttu-id="20e97-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="20e97-202">过程</span><span class="sxs-lookup"><span data-stu-id="20e97-202">Procedures</span></span>  
  
|<span data-ttu-id="20e97-203">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-203">ColumnName</span></span>|<span data-ttu-id="20e97-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="20e97-206">String</span><span class="sxs-lookup"><span data-stu-id="20e97-206">String</span></span>|  
|<span data-ttu-id="20e97-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="20e97-208">String</span><span class="sxs-lookup"><span data-stu-id="20e97-208">String</span></span>|  
|<span data-ttu-id="20e97-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="20e97-210">String</span><span class="sxs-lookup"><span data-stu-id="20e97-210">String</span></span>|  
|<span data-ttu-id="20e97-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="20e97-212">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-212">Int16</span></span>|  
|<span data-ttu-id="20e97-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="20e97-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="20e97-214">String</span><span class="sxs-lookup"><span data-stu-id="20e97-214">String</span></span>|  
|<span data-ttu-id="20e97-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-215">DESCRIPTION</span></span>|<span data-ttu-id="20e97-216">String</span><span class="sxs-lookup"><span data-stu-id="20e97-216">String</span></span>|  
|<span data-ttu-id="20e97-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-217">DATE_CREATED</span></span>|<span data-ttu-id="20e97-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-218">DateTime</span></span>|  
|<span data-ttu-id="20e97-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-219">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="20e97-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="20e97-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="20e97-222">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-222">ColumnName</span></span>|<span data-ttu-id="20e97-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="20e97-225">String</span><span class="sxs-lookup"><span data-stu-id="20e97-225">String</span></span>|  
|<span data-ttu-id="20e97-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="20e97-227">String</span><span class="sxs-lookup"><span data-stu-id="20e97-227">String</span></span>|  
|<span data-ttu-id="20e97-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="20e97-229">String</span><span class="sxs-lookup"><span data-stu-id="20e97-229">String</span></span>|  
|<span data-ttu-id="20e97-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-230">PARAMETER_NAME</span></span>|<span data-ttu-id="20e97-231">String</span><span class="sxs-lookup"><span data-stu-id="20e97-231">String</span></span>|  
|<span data-ttu-id="20e97-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-233">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-233">Int32</span></span>|  
|<span data-ttu-id="20e97-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="20e97-235">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-235">Int32</span></span>|  
|<span data-ttu-id="20e97-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="20e97-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-237">Boolean</span></span>|  
|<span data-ttu-id="20e97-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="20e97-239">String</span><span class="sxs-lookup"><span data-stu-id="20e97-239">String</span></span>|  
|<span data-ttu-id="20e97-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="20e97-240">IS_NULLABLE</span></span>|<span data-ttu-id="20e97-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-241">Boolean</span></span>|  
|<span data-ttu-id="20e97-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-242">DATA_TYPE</span></span>|<span data-ttu-id="20e97-243">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-243">Int32</span></span>|  
|<span data-ttu-id="20e97-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="20e97-245">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-245">Int64</span></span>|  
|<span data-ttu-id="20e97-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="20e97-247">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-247">Int64</span></span>|  
|<span data-ttu-id="20e97-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="20e97-249">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-249">Int32</span></span>|  
|<span data-ttu-id="20e97-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="20e97-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="20e97-251">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-251">Int16</span></span>|  
|<span data-ttu-id="20e97-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-252">DESCRIPTION</span></span>|<span data-ttu-id="20e97-253">String</span><span class="sxs-lookup"><span data-stu-id="20e97-253">String</span></span>|  
|<span data-ttu-id="20e97-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-254">TYPE_NAME</span></span>|<span data-ttu-id="20e97-255">String</span><span class="sxs-lookup"><span data-stu-id="20e97-255">String</span></span>|  
|<span data-ttu-id="20e97-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="20e97-257">String</span><span class="sxs-lookup"><span data-stu-id="20e97-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="20e97-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="20e97-258">Catalog</span></span>  
  
|<span data-ttu-id="20e97-259">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-259">ColumnName</span></span>|<span data-ttu-id="20e97-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-261">CATALOG_NAME</span></span>|<span data-ttu-id="20e97-262">String</span><span class="sxs-lookup"><span data-stu-id="20e97-262">String</span></span>|  
|<span data-ttu-id="20e97-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-263">DESCRIPTION</span></span>|<span data-ttu-id="20e97-264">String</span><span class="sxs-lookup"><span data-stu-id="20e97-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="20e97-265">索引</span><span class="sxs-lookup"><span data-stu-id="20e97-265">Indexes</span></span>  
  
|<span data-ttu-id="20e97-266">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-266">ColumnName</span></span>|<span data-ttu-id="20e97-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-268">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-269">String</span><span class="sxs-lookup"><span data-stu-id="20e97-269">String</span></span>|  
|<span data-ttu-id="20e97-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-271">String</span><span class="sxs-lookup"><span data-stu-id="20e97-271">String</span></span>|  
|<span data-ttu-id="20e97-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-272">TABLE_NAME</span></span>|<span data-ttu-id="20e97-273">String</span><span class="sxs-lookup"><span data-stu-id="20e97-273">String</span></span>|  
|<span data-ttu-id="20e97-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-274">INDEX_CATALOG</span></span>|<span data-ttu-id="20e97-275">String</span><span class="sxs-lookup"><span data-stu-id="20e97-275">String</span></span>|  
|<span data-ttu-id="20e97-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="20e97-277">String</span><span class="sxs-lookup"><span data-stu-id="20e97-277">String</span></span>|  
|<span data-ttu-id="20e97-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-278">INDEX_NAME</span></span>|<span data-ttu-id="20e97-279">String</span><span class="sxs-lookup"><span data-stu-id="20e97-279">String</span></span>|  
|<span data-ttu-id="20e97-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="20e97-280">PRIMARY_KEY</span></span>|<span data-ttu-id="20e97-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-281">Boolean</span></span>|  
|<span data-ttu-id="20e97-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="20e97-282">UNIQUE</span></span>|<span data-ttu-id="20e97-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-283">Boolean</span></span>|  
|<span data-ttu-id="20e97-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="20e97-284">CLUSTERED</span></span>|<span data-ttu-id="20e97-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-285">Boolean</span></span>|  
|<span data-ttu-id="20e97-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-286">TYPE</span></span>|<span data-ttu-id="20e97-287">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-287">Int32</span></span>|  
|<span data-ttu-id="20e97-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="20e97-288">FILL_FACTOR</span></span>|<span data-ttu-id="20e97-289">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-289">Int32</span></span>|  
|<span data-ttu-id="20e97-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="20e97-290">INITIAL_SIZE</span></span>|<span data-ttu-id="20e97-291">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-291">Int32</span></span>|  
|<span data-ttu-id="20e97-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="20e97-292">NULLS</span></span>|<span data-ttu-id="20e97-293">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-293">Int32</span></span>|  
|<span data-ttu-id="20e97-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="20e97-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="20e97-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-295">Boolean</span></span>|  
|<span data-ttu-id="20e97-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="20e97-296">AUTO_UPDATE</span></span>|<span data-ttu-id="20e97-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-297">Boolean</span></span>|  
|<span data-ttu-id="20e97-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="20e97-298">NULL_COLLATION</span></span>|<span data-ttu-id="20e97-299">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-299">Int32</span></span>|  
|<span data-ttu-id="20e97-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-301">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-301">Int64</span></span>|  
|<span data-ttu-id="20e97-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-302">COLUMN_NAME</span></span>|<span data-ttu-id="20e97-303">String</span><span class="sxs-lookup"><span data-stu-id="20e97-303">String</span></span>|  
|<span data-ttu-id="20e97-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-304">COLUMN_GUID</span></span>|<span data-ttu-id="20e97-305">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-305">Guid</span></span>|  
|<span data-ttu-id="20e97-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-306">COLUMN_PROPID</span></span>|<span data-ttu-id="20e97-307">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-307">Int64</span></span>|  
|<span data-ttu-id="20e97-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="20e97-308">COLLATION</span></span>|<span data-ttu-id="20e97-309">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-309">Int16</span></span>|  
|<span data-ttu-id="20e97-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="20e97-310">CARDINALITY</span></span>|<span data-ttu-id="20e97-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="20e97-311">Decimal</span></span>|  
|<span data-ttu-id="20e97-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="20e97-312">PAGES</span></span>|<span data-ttu-id="20e97-313">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-313">Int32</span></span>|  
|<span data-ttu-id="20e97-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="20e97-314">FILTER_CONDITION</span></span>|<span data-ttu-id="20e97-315">String</span><span class="sxs-lookup"><span data-stu-id="20e97-315">String</span></span>|  
|<span data-ttu-id="20e97-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="20e97-316">INTEGRATED</span></span>|<span data-ttu-id="20e97-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="20e97-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="20e97-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="20e97-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="20e97-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="20e97-320">表</span><span class="sxs-lookup"><span data-stu-id="20e97-320">Tables</span></span>  
  
-   <span data-ttu-id="20e97-321">Columns</span><span class="sxs-lookup"><span data-stu-id="20e97-321">Columns</span></span>  
  
-   <span data-ttu-id="20e97-322">过程</span><span class="sxs-lookup"><span data-stu-id="20e97-322">Procedures</span></span>  
  
-   <span data-ttu-id="20e97-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="20e97-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="20e97-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="20e97-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="20e97-325">视图</span><span class="sxs-lookup"><span data-stu-id="20e97-325">Views</span></span>  
  
-   <span data-ttu-id="20e97-326">索引</span><span class="sxs-lookup"><span data-stu-id="20e97-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="20e97-327">表</span><span class="sxs-lookup"><span data-stu-id="20e97-327">Tables</span></span>  
  
|<span data-ttu-id="20e97-328">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-328">ColumnName</span></span>|<span data-ttu-id="20e97-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-330">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-331">String</span><span class="sxs-lookup"><span data-stu-id="20e97-331">String</span></span>|  
|<span data-ttu-id="20e97-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-333">String</span><span class="sxs-lookup"><span data-stu-id="20e97-333">String</span></span>|  
|<span data-ttu-id="20e97-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-334">TABLE_NAME</span></span>|<span data-ttu-id="20e97-335">String</span><span class="sxs-lookup"><span data-stu-id="20e97-335">String</span></span>|  
|<span data-ttu-id="20e97-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-336">TABLE_TYPE</span></span>|<span data-ttu-id="20e97-337">String</span><span class="sxs-lookup"><span data-stu-id="20e97-337">String</span></span>|  
|<span data-ttu-id="20e97-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-338">TABLE_GUID</span></span>|<span data-ttu-id="20e97-339">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-339">Guid</span></span>|  
|<span data-ttu-id="20e97-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-340">DESCRIPTION</span></span>|<span data-ttu-id="20e97-341">String</span><span class="sxs-lookup"><span data-stu-id="20e97-341">String</span></span>|  
|<span data-ttu-id="20e97-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-342">TABLE_PROPID</span></span>|<span data-ttu-id="20e97-343">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-343">Int64</span></span>|  
|<span data-ttu-id="20e97-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-344">DATE_CREATED</span></span>|<span data-ttu-id="20e97-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-345">DateTime</span></span>|  
|<span data-ttu-id="20e97-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-346">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="20e97-348">Columns</span><span class="sxs-lookup"><span data-stu-id="20e97-348">Columns</span></span>  
  
|<span data-ttu-id="20e97-349">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-349">ColumnName</span></span>|<span data-ttu-id="20e97-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-351">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-352">String</span><span class="sxs-lookup"><span data-stu-id="20e97-352">String</span></span>|  
|<span data-ttu-id="20e97-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-354">String</span><span class="sxs-lookup"><span data-stu-id="20e97-354">String</span></span>|  
|<span data-ttu-id="20e97-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-355">TABLE_NAME</span></span>|<span data-ttu-id="20e97-356">String</span><span class="sxs-lookup"><span data-stu-id="20e97-356">String</span></span>|  
|<span data-ttu-id="20e97-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-357">COLUMN_NAME</span></span>|<span data-ttu-id="20e97-358">String</span><span class="sxs-lookup"><span data-stu-id="20e97-358">String</span></span>|  
|<span data-ttu-id="20e97-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-359">COLUMN_GUID</span></span>|<span data-ttu-id="20e97-360">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-360">Guid</span></span>|  
|<span data-ttu-id="20e97-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-361">COLUMN_PROPID</span></span>|<span data-ttu-id="20e97-362">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-362">Int64</span></span>|  
|<span data-ttu-id="20e97-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-364">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-364">Int64</span></span>|  
|<span data-ttu-id="20e97-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="20e97-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-366">Boolean</span></span>|  
|<span data-ttu-id="20e97-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="20e97-368">String</span><span class="sxs-lookup"><span data-stu-id="20e97-368">String</span></span>|  
|<span data-ttu-id="20e97-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="20e97-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="20e97-370">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-370">Int64</span></span>|  
|<span data-ttu-id="20e97-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="20e97-371">IS_NULLABLE</span></span>|<span data-ttu-id="20e97-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-372">Boolean</span></span>|  
|<span data-ttu-id="20e97-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-373">DATA_TYPE</span></span>|<span data-ttu-id="20e97-374">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-374">Int32</span></span>|  
|<span data-ttu-id="20e97-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-375">TYPE_GUID</span></span>|<span data-ttu-id="20e97-376">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-376">Guid</span></span>|  
|<span data-ttu-id="20e97-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="20e97-378">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-378">Int64</span></span>|  
|<span data-ttu-id="20e97-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="20e97-380">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-380">Int64</span></span>|  
|<span data-ttu-id="20e97-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="20e97-382">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-382">Int32</span></span>|  
|<span data-ttu-id="20e97-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="20e97-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="20e97-384">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-384">Int16</span></span>|  
|<span data-ttu-id="20e97-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="20e97-386">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-386">Int64</span></span>|  
|<span data-ttu-id="20e97-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="20e97-388">String</span><span class="sxs-lookup"><span data-stu-id="20e97-388">String</span></span>|  
|<span data-ttu-id="20e97-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="20e97-390">String</span><span class="sxs-lookup"><span data-stu-id="20e97-390">String</span></span>|  
|<span data-ttu-id="20e97-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="20e97-392">String</span><span class="sxs-lookup"><span data-stu-id="20e97-392">String</span></span>|  
|<span data-ttu-id="20e97-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="20e97-394">String</span><span class="sxs-lookup"><span data-stu-id="20e97-394">String</span></span>|  
|<span data-ttu-id="20e97-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="20e97-396">String</span><span class="sxs-lookup"><span data-stu-id="20e97-396">String</span></span>|  
|<span data-ttu-id="20e97-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-397">COLLATION_NAME</span></span>|<span data-ttu-id="20e97-398">String</span><span class="sxs-lookup"><span data-stu-id="20e97-398">String</span></span>|  
|<span data-ttu-id="20e97-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="20e97-400">String</span><span class="sxs-lookup"><span data-stu-id="20e97-400">String</span></span>|  
|<span data-ttu-id="20e97-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="20e97-402">String</span><span class="sxs-lookup"><span data-stu-id="20e97-402">String</span></span>|  
|<span data-ttu-id="20e97-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-403">DOMAIN_NAME</span></span>|<span data-ttu-id="20e97-404">String</span><span class="sxs-lookup"><span data-stu-id="20e97-404">String</span></span>|  
|<span data-ttu-id="20e97-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-405">DESCRIPTION</span></span>|<span data-ttu-id="20e97-406">String</span><span class="sxs-lookup"><span data-stu-id="20e97-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="20e97-407">过程</span><span class="sxs-lookup"><span data-stu-id="20e97-407">Procedures</span></span>  
  
|<span data-ttu-id="20e97-408">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-408">ColumnName</span></span>|<span data-ttu-id="20e97-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="20e97-411">String</span><span class="sxs-lookup"><span data-stu-id="20e97-411">String</span></span>|  
|<span data-ttu-id="20e97-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="20e97-413">String</span><span class="sxs-lookup"><span data-stu-id="20e97-413">String</span></span>|  
|<span data-ttu-id="20e97-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="20e97-415">String</span><span class="sxs-lookup"><span data-stu-id="20e97-415">String</span></span>|  
|<span data-ttu-id="20e97-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="20e97-417">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-417">Int16</span></span>|  
|<span data-ttu-id="20e97-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="20e97-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="20e97-419">String</span><span class="sxs-lookup"><span data-stu-id="20e97-419">String</span></span>|  
|<span data-ttu-id="20e97-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-420">DESCRIPTION</span></span>|<span data-ttu-id="20e97-421">String</span><span class="sxs-lookup"><span data-stu-id="20e97-421">String</span></span>|  
|<span data-ttu-id="20e97-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-422">DATE_CREATED</span></span>|<span data-ttu-id="20e97-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-423">DateTime</span></span>|  
|<span data-ttu-id="20e97-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-424">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="20e97-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="20e97-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="20e97-427">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-427">ColumnName</span></span>|<span data-ttu-id="20e97-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="20e97-430">String</span><span class="sxs-lookup"><span data-stu-id="20e97-430">String</span></span>|  
|<span data-ttu-id="20e97-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="20e97-432">String</span><span class="sxs-lookup"><span data-stu-id="20e97-432">String</span></span>|  
|<span data-ttu-id="20e97-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="20e97-434">String</span><span class="sxs-lookup"><span data-stu-id="20e97-434">String</span></span>|  
|<span data-ttu-id="20e97-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-435">COLUMN_NAME</span></span>|<span data-ttu-id="20e97-436">String</span><span class="sxs-lookup"><span data-stu-id="20e97-436">String</span></span>|  
|<span data-ttu-id="20e97-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-437">COLUMN_GUID</span></span>|<span data-ttu-id="20e97-438">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-438">Guid</span></span>|  
|<span data-ttu-id="20e97-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-439">COLUMN_PROPID</span></span>|<span data-ttu-id="20e97-440">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-440">Int64</span></span>|  
|<span data-ttu-id="20e97-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="20e97-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="20e97-442">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-442">Int64</span></span>|  
|<span data-ttu-id="20e97-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-444">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-444">Int64</span></span>|  
|<span data-ttu-id="20e97-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="20e97-445">IS_NULLABLE</span></span>|<span data-ttu-id="20e97-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-446">Boolean</span></span>|  
|<span data-ttu-id="20e97-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-447">DATA_TYPE</span></span>|<span data-ttu-id="20e97-448">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-448">Int32</span></span>|  
|<span data-ttu-id="20e97-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-449">TYPE_GUID</span></span>|<span data-ttu-id="20e97-450">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-450">Guid</span></span>|  
|<span data-ttu-id="20e97-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="20e97-452">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-452">Int64</span></span>|  
|<span data-ttu-id="20e97-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="20e97-454">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-454">Int64</span></span>|  
|<span data-ttu-id="20e97-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="20e97-456">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-456">Int32</span></span>|  
|<span data-ttu-id="20e97-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="20e97-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="20e97-458">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-458">Int16</span></span>|  
|<span data-ttu-id="20e97-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-459">DESCRIPTION</span></span>|<span data-ttu-id="20e97-460">String</span><span class="sxs-lookup"><span data-stu-id="20e97-460">String</span></span>|  
|<span data-ttu-id="20e97-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="20e97-461">OVERLOAD</span></span>|<span data-ttu-id="20e97-462">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="20e97-463">视图</span><span class="sxs-lookup"><span data-stu-id="20e97-463">Views</span></span>  
  
|<span data-ttu-id="20e97-464">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-464">ColumnName</span></span>|<span data-ttu-id="20e97-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-466">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-467">String</span><span class="sxs-lookup"><span data-stu-id="20e97-467">String</span></span>|  
|<span data-ttu-id="20e97-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-469">String</span><span class="sxs-lookup"><span data-stu-id="20e97-469">String</span></span>|  
|<span data-ttu-id="20e97-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-470">TABLE_NAME</span></span>|<span data-ttu-id="20e97-471">String</span><span class="sxs-lookup"><span data-stu-id="20e97-471">String</span></span>|  
|<span data-ttu-id="20e97-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="20e97-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="20e97-473">String</span><span class="sxs-lookup"><span data-stu-id="20e97-473">String</span></span>|  
|<span data-ttu-id="20e97-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-474">CHECK_OPTION</span></span>|<span data-ttu-id="20e97-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-475">Boolean</span></span>|  
|<span data-ttu-id="20e97-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="20e97-476">IS_UPDATABLE</span></span>|<span data-ttu-id="20e97-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-477">Boolean</span></span>|  
|<span data-ttu-id="20e97-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-478">DESCRIPTION</span></span>|<span data-ttu-id="20e97-479">String</span><span class="sxs-lookup"><span data-stu-id="20e97-479">String</span></span>|  
|<span data-ttu-id="20e97-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-480">DATE_CREATED</span></span>|<span data-ttu-id="20e97-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-481">DateTime</span></span>|  
|<span data-ttu-id="20e97-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-482">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="20e97-484">索引</span><span class="sxs-lookup"><span data-stu-id="20e97-484">Indexes</span></span>  
  
|<span data-ttu-id="20e97-485">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-485">ColumnName</span></span>|<span data-ttu-id="20e97-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-487">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-488">String</span><span class="sxs-lookup"><span data-stu-id="20e97-488">String</span></span>|  
|<span data-ttu-id="20e97-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-490">String</span><span class="sxs-lookup"><span data-stu-id="20e97-490">String</span></span>|  
|<span data-ttu-id="20e97-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-491">TABLE_NAME</span></span>|<span data-ttu-id="20e97-492">String</span><span class="sxs-lookup"><span data-stu-id="20e97-492">String</span></span>|  
|<span data-ttu-id="20e97-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-493">INDEX_CATALOG</span></span>|<span data-ttu-id="20e97-494">String</span><span class="sxs-lookup"><span data-stu-id="20e97-494">String</span></span>|  
|<span data-ttu-id="20e97-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="20e97-496">String</span><span class="sxs-lookup"><span data-stu-id="20e97-496">String</span></span>|  
|<span data-ttu-id="20e97-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-497">INDEX_NAME</span></span>|<span data-ttu-id="20e97-498">String</span><span class="sxs-lookup"><span data-stu-id="20e97-498">String</span></span>|  
|<span data-ttu-id="20e97-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="20e97-499">PRIMARY_KEY</span></span>|<span data-ttu-id="20e97-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-500">Boolean</span></span>|  
|<span data-ttu-id="20e97-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="20e97-501">UNIQUE</span></span>|<span data-ttu-id="20e97-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-502">Boolean</span></span>|  
|<span data-ttu-id="20e97-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="20e97-503">CLUSTERED</span></span>|<span data-ttu-id="20e97-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-504">Boolean</span></span>|  
|<span data-ttu-id="20e97-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-505">TYPE</span></span>|<span data-ttu-id="20e97-506">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-506">Int32</span></span>|  
|<span data-ttu-id="20e97-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="20e97-507">FILL_FACTOR</span></span>|<span data-ttu-id="20e97-508">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-508">Int32</span></span>|  
|<span data-ttu-id="20e97-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="20e97-509">INITIAL_SIZE</span></span>|<span data-ttu-id="20e97-510">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-510">Int32</span></span>|  
|<span data-ttu-id="20e97-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="20e97-511">NULLS</span></span>|<span data-ttu-id="20e97-512">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-512">Int32</span></span>|  
|<span data-ttu-id="20e97-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="20e97-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="20e97-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-514">Boolean</span></span>|  
|<span data-ttu-id="20e97-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="20e97-515">AUTO_UPDATE</span></span>|<span data-ttu-id="20e97-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-516">Boolean</span></span>|  
|<span data-ttu-id="20e97-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="20e97-517">NULL_COLLATION</span></span>|<span data-ttu-id="20e97-518">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-518">Int32</span></span>|  
|<span data-ttu-id="20e97-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-520">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-520">Int64</span></span>|  
|<span data-ttu-id="20e97-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-521">COLUMN_NAME</span></span>|<span data-ttu-id="20e97-522">String</span><span class="sxs-lookup"><span data-stu-id="20e97-522">String</span></span>|  
|<span data-ttu-id="20e97-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-523">COLUMN_GUID</span></span>|<span data-ttu-id="20e97-524">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-524">Guid</span></span>|  
|<span data-ttu-id="20e97-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-525">COLUMN_PROPID</span></span>|<span data-ttu-id="20e97-526">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-526">Int64</span></span>|  
|<span data-ttu-id="20e97-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="20e97-527">COLLATION</span></span>|<span data-ttu-id="20e97-528">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-528">Int16</span></span>|  
|<span data-ttu-id="20e97-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="20e97-529">CARDINALITY</span></span>|<span data-ttu-id="20e97-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="20e97-530">Decimal</span></span>|  
|<span data-ttu-id="20e97-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="20e97-531">PAGES</span></span>|<span data-ttu-id="20e97-532">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-532">Int32</span></span>|  
|<span data-ttu-id="20e97-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="20e97-533">FILTER_CONDITION</span></span>|<span data-ttu-id="20e97-534">String</span><span class="sxs-lookup"><span data-stu-id="20e97-534">String</span></span>|  
|<span data-ttu-id="20e97-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="20e97-535">INTEGRATED</span></span>|<span data-ttu-id="20e97-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="20e97-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="20e97-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="20e97-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="20e97-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="20e97-539">表</span><span class="sxs-lookup"><span data-stu-id="20e97-539">Tables</span></span>  
  
-   <span data-ttu-id="20e97-540">Columns</span><span class="sxs-lookup"><span data-stu-id="20e97-540">Columns</span></span>  
  
-   <span data-ttu-id="20e97-541">过程</span><span class="sxs-lookup"><span data-stu-id="20e97-541">Procedures</span></span>  
  
-   <span data-ttu-id="20e97-542">视图</span><span class="sxs-lookup"><span data-stu-id="20e97-542">Views</span></span>  
  
-   <span data-ttu-id="20e97-543">索引</span><span class="sxs-lookup"><span data-stu-id="20e97-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="20e97-544">表</span><span class="sxs-lookup"><span data-stu-id="20e97-544">Tables</span></span>  
  
|<span data-ttu-id="20e97-545">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-545">ColumnName</span></span>|<span data-ttu-id="20e97-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-547">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-548">String</span><span class="sxs-lookup"><span data-stu-id="20e97-548">String</span></span>|  
|<span data-ttu-id="20e97-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-550">String</span><span class="sxs-lookup"><span data-stu-id="20e97-550">String</span></span>|  
|<span data-ttu-id="20e97-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-551">TABLE_NAME</span></span>|<span data-ttu-id="20e97-552">String</span><span class="sxs-lookup"><span data-stu-id="20e97-552">String</span></span>|  
|<span data-ttu-id="20e97-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-553">TABLE_TYPE</span></span>|<span data-ttu-id="20e97-554">String</span><span class="sxs-lookup"><span data-stu-id="20e97-554">String</span></span>|  
|<span data-ttu-id="20e97-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-555">TABLE_GUID</span></span>|<span data-ttu-id="20e97-556">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-556">Guid</span></span>|  
|<span data-ttu-id="20e97-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-557">DESCRIPTION</span></span>|<span data-ttu-id="20e97-558">String</span><span class="sxs-lookup"><span data-stu-id="20e97-558">String</span></span>|  
|<span data-ttu-id="20e97-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-559">TABLE_PROPID</span></span>|<span data-ttu-id="20e97-560">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-560">Int64</span></span>|  
|<span data-ttu-id="20e97-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-561">DATE_CREATED</span></span>|<span data-ttu-id="20e97-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-562">DateTime</span></span>|  
|<span data-ttu-id="20e97-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-563">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="20e97-565">Columns</span><span class="sxs-lookup"><span data-stu-id="20e97-565">Columns</span></span>  
  
|<span data-ttu-id="20e97-566">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-566">ColumnName</span></span>|<span data-ttu-id="20e97-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-568">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-569">String</span><span class="sxs-lookup"><span data-stu-id="20e97-569">String</span></span>|  
|<span data-ttu-id="20e97-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-571">String</span><span class="sxs-lookup"><span data-stu-id="20e97-571">String</span></span>|  
|<span data-ttu-id="20e97-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-572">TABLE_NAME</span></span>|<span data-ttu-id="20e97-573">String</span><span class="sxs-lookup"><span data-stu-id="20e97-573">String</span></span>|  
|<span data-ttu-id="20e97-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-574">COLUMN_NAME</span></span>|<span data-ttu-id="20e97-575">String</span><span class="sxs-lookup"><span data-stu-id="20e97-575">String</span></span>|  
|<span data-ttu-id="20e97-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-576">COLUMN_GUID</span></span>|<span data-ttu-id="20e97-577">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-577">Guid</span></span>|  
|<span data-ttu-id="20e97-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-578">COLUMN_PROPID</span></span>|<span data-ttu-id="20e97-579">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-579">Int64</span></span>|  
|<span data-ttu-id="20e97-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-581">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-581">Int64</span></span>|  
|<span data-ttu-id="20e97-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="20e97-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-583">Boolean</span></span>|  
|<span data-ttu-id="20e97-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="20e97-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="20e97-585">String</span><span class="sxs-lookup"><span data-stu-id="20e97-585">String</span></span>|  
|<span data-ttu-id="20e97-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="20e97-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="20e97-587">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-587">Int64</span></span>|  
|<span data-ttu-id="20e97-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="20e97-588">IS_NULLABLE</span></span>|<span data-ttu-id="20e97-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-589">Boolean</span></span>|  
|<span data-ttu-id="20e97-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-590">DATA_TYPE</span></span>|<span data-ttu-id="20e97-591">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-591">Int32</span></span>|  
|<span data-ttu-id="20e97-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-592">TYPE_GUID</span></span>|<span data-ttu-id="20e97-593">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-593">Guid</span></span>|  
|<span data-ttu-id="20e97-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="20e97-595">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-595">Int64</span></span>|  
|<span data-ttu-id="20e97-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="20e97-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="20e97-597">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-597">Int64</span></span>|  
|<span data-ttu-id="20e97-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="20e97-599">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-599">Int32</span></span>|  
|<span data-ttu-id="20e97-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="20e97-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="20e97-601">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-601">Int16</span></span>|  
|<span data-ttu-id="20e97-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="20e97-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="20e97-603">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-603">Int64</span></span>|  
|<span data-ttu-id="20e97-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="20e97-605">String</span><span class="sxs-lookup"><span data-stu-id="20e97-605">String</span></span>|  
|<span data-ttu-id="20e97-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="20e97-607">String</span><span class="sxs-lookup"><span data-stu-id="20e97-607">String</span></span>|  
|<span data-ttu-id="20e97-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="20e97-609">String</span><span class="sxs-lookup"><span data-stu-id="20e97-609">String</span></span>|  
|<span data-ttu-id="20e97-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="20e97-611">String</span><span class="sxs-lookup"><span data-stu-id="20e97-611">String</span></span>|  
|<span data-ttu-id="20e97-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="20e97-613">String</span><span class="sxs-lookup"><span data-stu-id="20e97-613">String</span></span>|  
|<span data-ttu-id="20e97-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-614">COLLATION_NAME</span></span>|<span data-ttu-id="20e97-615">String</span><span class="sxs-lookup"><span data-stu-id="20e97-615">String</span></span>|  
|<span data-ttu-id="20e97-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="20e97-617">String</span><span class="sxs-lookup"><span data-stu-id="20e97-617">String</span></span>|  
|<span data-ttu-id="20e97-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="20e97-619">String</span><span class="sxs-lookup"><span data-stu-id="20e97-619">String</span></span>|  
|<span data-ttu-id="20e97-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-620">DOMAIN_NAME</span></span>|<span data-ttu-id="20e97-621">String</span><span class="sxs-lookup"><span data-stu-id="20e97-621">String</span></span>|  
|<span data-ttu-id="20e97-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-622">DESCRIPTION</span></span>|<span data-ttu-id="20e97-623">String</span><span class="sxs-lookup"><span data-stu-id="20e97-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="20e97-624">过程</span><span class="sxs-lookup"><span data-stu-id="20e97-624">Procedures</span></span>  
  
|<span data-ttu-id="20e97-625">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-625">ColumnName</span></span>|<span data-ttu-id="20e97-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="20e97-628">String</span><span class="sxs-lookup"><span data-stu-id="20e97-628">String</span></span>|  
|<span data-ttu-id="20e97-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="20e97-630">String</span><span class="sxs-lookup"><span data-stu-id="20e97-630">String</span></span>|  
|<span data-ttu-id="20e97-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="20e97-632">String</span><span class="sxs-lookup"><span data-stu-id="20e97-632">String</span></span>|  
|<span data-ttu-id="20e97-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="20e97-634">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-634">Int16</span></span>|  
|<span data-ttu-id="20e97-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="20e97-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="20e97-636">String</span><span class="sxs-lookup"><span data-stu-id="20e97-636">String</span></span>|  
|<span data-ttu-id="20e97-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-637">DESCRIPTION</span></span>|<span data-ttu-id="20e97-638">String</span><span class="sxs-lookup"><span data-stu-id="20e97-638">String</span></span>|  
|<span data-ttu-id="20e97-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-639">DATE_CREATED</span></span>|<span data-ttu-id="20e97-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-640">DateTime</span></span>|  
|<span data-ttu-id="20e97-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-641">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="20e97-643">视图</span><span class="sxs-lookup"><span data-stu-id="20e97-643">Views</span></span>  
  
|<span data-ttu-id="20e97-644">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-644">ColumnName</span></span>|<span data-ttu-id="20e97-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-646">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-647">String</span><span class="sxs-lookup"><span data-stu-id="20e97-647">String</span></span>|  
|<span data-ttu-id="20e97-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-649">String</span><span class="sxs-lookup"><span data-stu-id="20e97-649">String</span></span>|  
|<span data-ttu-id="20e97-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-650">TABLE_NAME</span></span>|<span data-ttu-id="20e97-651">String</span><span class="sxs-lookup"><span data-stu-id="20e97-651">String</span></span>|  
|<span data-ttu-id="20e97-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="20e97-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="20e97-653">String</span><span class="sxs-lookup"><span data-stu-id="20e97-653">String</span></span>|  
|<span data-ttu-id="20e97-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-654">CHECK_OPTION</span></span>|<span data-ttu-id="20e97-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-655">Boolean</span></span>|  
|<span data-ttu-id="20e97-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="20e97-656">IS_UPDATABLE</span></span>|<span data-ttu-id="20e97-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-657">Boolean</span></span>|  
|<span data-ttu-id="20e97-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20e97-658">DESCRIPTION</span></span>|<span data-ttu-id="20e97-659">String</span><span class="sxs-lookup"><span data-stu-id="20e97-659">String</span></span>|  
|<span data-ttu-id="20e97-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="20e97-660">DATE_CREATED</span></span>|<span data-ttu-id="20e97-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-661">DateTime</span></span>|  
|<span data-ttu-id="20e97-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="20e97-662">DATE_MODIFIED</span></span>|<span data-ttu-id="20e97-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="20e97-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="20e97-664">索引</span><span class="sxs-lookup"><span data-stu-id="20e97-664">Indexes</span></span>  
  
|<span data-ttu-id="20e97-665">列名</span><span class="sxs-lookup"><span data-stu-id="20e97-665">ColumnName</span></span>|<span data-ttu-id="20e97-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="20e97-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="20e97-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-667">TABLE_CATALOG</span></span>|<span data-ttu-id="20e97-668">String</span><span class="sxs-lookup"><span data-stu-id="20e97-668">String</span></span>|  
|<span data-ttu-id="20e97-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="20e97-670">String</span><span class="sxs-lookup"><span data-stu-id="20e97-670">String</span></span>|  
|<span data-ttu-id="20e97-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-671">TABLE_NAME</span></span>|<span data-ttu-id="20e97-672">String</span><span class="sxs-lookup"><span data-stu-id="20e97-672">String</span></span>|  
|<span data-ttu-id="20e97-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="20e97-673">INDEX_CATALOG</span></span>|<span data-ttu-id="20e97-674">String</span><span class="sxs-lookup"><span data-stu-id="20e97-674">String</span></span>|  
|<span data-ttu-id="20e97-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="20e97-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="20e97-676">String</span><span class="sxs-lookup"><span data-stu-id="20e97-676">String</span></span>|  
|<span data-ttu-id="20e97-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-677">INDEX_NAME</span></span>|<span data-ttu-id="20e97-678">String</span><span class="sxs-lookup"><span data-stu-id="20e97-678">String</span></span>|  
|<span data-ttu-id="20e97-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="20e97-679">PRIMARY_KEY</span></span>|<span data-ttu-id="20e97-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-680">Boolean</span></span>|  
|<span data-ttu-id="20e97-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="20e97-681">UNIQUE</span></span>|<span data-ttu-id="20e97-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-682">Boolean</span></span>|  
|<span data-ttu-id="20e97-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="20e97-683">CLUSTERED</span></span>|<span data-ttu-id="20e97-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-684">Boolean</span></span>|  
|<span data-ttu-id="20e97-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="20e97-685">TYPE</span></span>|<span data-ttu-id="20e97-686">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-686">Int32</span></span>|  
|<span data-ttu-id="20e97-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="20e97-687">FILL_FACTOR</span></span>|<span data-ttu-id="20e97-688">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-688">Int32</span></span>|  
|<span data-ttu-id="20e97-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="20e97-689">INITIAL_SIZE</span></span>|<span data-ttu-id="20e97-690">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-690">Int32</span></span>|  
|<span data-ttu-id="20e97-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="20e97-691">NULLS</span></span>|<span data-ttu-id="20e97-692">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-692">Int32</span></span>|  
|<span data-ttu-id="20e97-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="20e97-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="20e97-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-694">Boolean</span></span>|  
|<span data-ttu-id="20e97-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="20e97-695">AUTO_UPDATE</span></span>|<span data-ttu-id="20e97-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-696">Boolean</span></span>|  
|<span data-ttu-id="20e97-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="20e97-697">NULL_COLLATION</span></span>|<span data-ttu-id="20e97-698">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-698">Int32</span></span>|  
|<span data-ttu-id="20e97-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="20e97-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="20e97-700">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-700">Int64</span></span>|  
|<span data-ttu-id="20e97-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="20e97-701">COLUMN_NAME</span></span>|<span data-ttu-id="20e97-702">String</span><span class="sxs-lookup"><span data-stu-id="20e97-702">String</span></span>|  
|<span data-ttu-id="20e97-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="20e97-703">COLUMN_GUID</span></span>|<span data-ttu-id="20e97-704">Guid</span><span class="sxs-lookup"><span data-stu-id="20e97-704">Guid</span></span>|  
|<span data-ttu-id="20e97-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="20e97-705">COLUMN_PROPID</span></span>|<span data-ttu-id="20e97-706">Int64</span><span class="sxs-lookup"><span data-stu-id="20e97-706">Int64</span></span>|  
|<span data-ttu-id="20e97-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="20e97-707">COLLATION</span></span>|<span data-ttu-id="20e97-708">Int16</span><span class="sxs-lookup"><span data-stu-id="20e97-708">Int16</span></span>|  
|<span data-ttu-id="20e97-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="20e97-709">CARDINALITY</span></span>|<span data-ttu-id="20e97-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="20e97-710">Decimal</span></span>|  
|<span data-ttu-id="20e97-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="20e97-711">PAGES</span></span>|<span data-ttu-id="20e97-712">Int32</span><span class="sxs-lookup"><span data-stu-id="20e97-712">Int32</span></span>|  
|<span data-ttu-id="20e97-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="20e97-713">FILTER_CONDITION</span></span>|<span data-ttu-id="20e97-714">String</span><span class="sxs-lookup"><span data-stu-id="20e97-714">String</span></span>|  
|<span data-ttu-id="20e97-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="20e97-715">INTEGRATED</span></span>|<span data-ttu-id="20e97-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="20e97-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20e97-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="20e97-717">See Also</span></span>  
 [<span data-ttu-id="20e97-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="20e97-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
