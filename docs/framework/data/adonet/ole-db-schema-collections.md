---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771990"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="4ef02-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="4ef02-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="4ef02-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="4ef02-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="4ef02-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="4ef02-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="4ef02-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="4ef02-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="4ef02-106">表</span><span class="sxs-lookup"><span data-stu-id="4ef02-106">Tables</span></span>  
  
- <span data-ttu-id="4ef02-107">列</span><span class="sxs-lookup"><span data-stu-id="4ef02-107">Columns</span></span>  
  
- <span data-ttu-id="4ef02-108">过程</span><span class="sxs-lookup"><span data-stu-id="4ef02-108">Procedures</span></span>  
  
- <span data-ttu-id="4ef02-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4ef02-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="4ef02-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="4ef02-110">Catalog</span></span>  
  
- <span data-ttu-id="4ef02-111">索引</span><span class="sxs-lookup"><span data-stu-id="4ef02-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="4ef02-112">表</span><span class="sxs-lookup"><span data-stu-id="4ef02-112">Tables</span></span>  
  
|<span data-ttu-id="4ef02-113">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-113">ColumnName</span></span>|<span data-ttu-id="4ef02-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-115">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-116">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-116">String</span></span>|  
|<span data-ttu-id="4ef02-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-118">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-118">String</span></span>|  
|<span data-ttu-id="4ef02-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-119">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-120">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-120">String</span></span>|  
|<span data-ttu-id="4ef02-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-121">TABLE_TYPE</span></span>|<span data-ttu-id="4ef02-122">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-122">String</span></span>|  
|<span data-ttu-id="4ef02-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-123">TABLE_GUID</span></span>|<span data-ttu-id="4ef02-124">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-124">Guid</span></span>|  
|<span data-ttu-id="4ef02-125">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-125">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-126">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-126">String</span></span>|  
|<span data-ttu-id="4ef02-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-127">TABLE_PROPID</span></span>|<span data-ttu-id="4ef02-128">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-128">Int64</span></span>|  
|<span data-ttu-id="4ef02-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-129">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-130">DateTime</span></span>|  
|<span data-ttu-id="4ef02-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-131">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4ef02-133">列</span><span class="sxs-lookup"><span data-stu-id="4ef02-133">Columns</span></span>  
  
|<span data-ttu-id="4ef02-134">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-134">ColumnName</span></span>|<span data-ttu-id="4ef02-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-136">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-137">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-137">String</span></span>|  
|<span data-ttu-id="4ef02-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-139">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-139">String</span></span>|  
|<span data-ttu-id="4ef02-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-140">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-141">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-141">String</span></span>|  
|<span data-ttu-id="4ef02-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-142">COLUMN_NAME</span></span>|<span data-ttu-id="4ef02-143">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-143">String</span></span>|  
|<span data-ttu-id="4ef02-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-144">COLUMN_GUID</span></span>|<span data-ttu-id="4ef02-145">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-145">Guid</span></span>|  
|<span data-ttu-id="4ef02-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-146">COLUMN_PROPID</span></span>|<span data-ttu-id="4ef02-147">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-147">Int64</span></span>|  
|<span data-ttu-id="4ef02-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-149">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-149">Int64</span></span>|  
|<span data-ttu-id="4ef02-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="4ef02-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-151">Boolean</span></span>|  
|<span data-ttu-id="4ef02-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="4ef02-153">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-153">String</span></span>|  
|<span data-ttu-id="4ef02-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="4ef02-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="4ef02-155">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-155">Int64</span></span>|  
|<span data-ttu-id="4ef02-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4ef02-156">IS_NULLABLE</span></span>|<span data-ttu-id="4ef02-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-157">Boolean</span></span>|  
|<span data-ttu-id="4ef02-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-158">DATA_TYPE</span></span>|<span data-ttu-id="4ef02-159">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-159">Int32</span></span>|  
|<span data-ttu-id="4ef02-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-160">TYPE_GUID</span></span>|<span data-ttu-id="4ef02-161">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-161">Guid</span></span>|  
|<span data-ttu-id="4ef02-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="4ef02-163">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-163">Int64</span></span>|  
|<span data-ttu-id="4ef02-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="4ef02-165">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-165">Int64</span></span>|  
|<span data-ttu-id="4ef02-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="4ef02-167">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-167">Int32</span></span>|  
|<span data-ttu-id="4ef02-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="4ef02-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="4ef02-169">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-169">Int16</span></span>|  
|<span data-ttu-id="4ef02-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="4ef02-171">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-171">Int64</span></span>|  
|<span data-ttu-id="4ef02-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="4ef02-173">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-173">String</span></span>|  
|<span data-ttu-id="4ef02-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="4ef02-175">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-175">String</span></span>|  
|<span data-ttu-id="4ef02-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="4ef02-177">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-177">String</span></span>|  
|<span data-ttu-id="4ef02-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="4ef02-179">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-179">String</span></span>|  
|<span data-ttu-id="4ef02-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="4ef02-181">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-181">String</span></span>|  
|<span data-ttu-id="4ef02-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-182">COLLATION_NAME</span></span>|<span data-ttu-id="4ef02-183">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-183">String</span></span>|  
|<span data-ttu-id="4ef02-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="4ef02-185">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-185">String</span></span>|  
|<span data-ttu-id="4ef02-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="4ef02-187">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-187">String</span></span>|  
|<span data-ttu-id="4ef02-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-188">DOMAIN_NAME</span></span>|<span data-ttu-id="4ef02-189">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-189">String</span></span>|  
|<span data-ttu-id="4ef02-190">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-190">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-191">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-191">String</span></span>|  
|<span data-ttu-id="4ef02-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="4ef02-192">COLUMN_LCID</span></span>|<span data-ttu-id="4ef02-193">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-193">Int32</span></span>|  
|<span data-ttu-id="4ef02-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="4ef02-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="4ef02-195">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-195">Int32</span></span>|  
|<span data-ttu-id="4ef02-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="4ef02-196">COLUMN_SORTID</span></span>|<span data-ttu-id="4ef02-197">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-197">Int32</span></span>|  
|<span data-ttu-id="4ef02-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="4ef02-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="4ef02-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="4ef02-199">Byte[]</span></span>|  
|<span data-ttu-id="4ef02-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="4ef02-200">IS_COMPUTED</span></span>|<span data-ttu-id="4ef02-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4ef02-202">过程</span><span class="sxs-lookup"><span data-stu-id="4ef02-202">Procedures</span></span>  
  
|<span data-ttu-id="4ef02-203">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-203">ColumnName</span></span>|<span data-ttu-id="4ef02-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="4ef02-206">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-206">String</span></span>|  
|<span data-ttu-id="4ef02-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="4ef02-208">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-208">String</span></span>|  
|<span data-ttu-id="4ef02-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="4ef02-210">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-210">String</span></span>|  
|<span data-ttu-id="4ef02-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4ef02-212">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-212">Int16</span></span>|  
|<span data-ttu-id="4ef02-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="4ef02-214">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-214">String</span></span>|  
|<span data-ttu-id="4ef02-215">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-215">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-216">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-216">String</span></span>|  
|<span data-ttu-id="4ef02-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-217">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-218">DateTime</span></span>|  
|<span data-ttu-id="4ef02-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-219">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="4ef02-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4ef02-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="4ef02-222">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-222">ColumnName</span></span>|<span data-ttu-id="4ef02-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="4ef02-225">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-225">String</span></span>|  
|<span data-ttu-id="4ef02-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="4ef02-227">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-227">String</span></span>|  
|<span data-ttu-id="4ef02-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="4ef02-229">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-229">String</span></span>|  
|<span data-ttu-id="4ef02-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-230">PARAMETER_NAME</span></span>|<span data-ttu-id="4ef02-231">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-231">String</span></span>|  
|<span data-ttu-id="4ef02-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-233">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-233">Int32</span></span>|  
|<span data-ttu-id="4ef02-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="4ef02-235">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-235">Int32</span></span>|  
|<span data-ttu-id="4ef02-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="4ef02-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-237">Boolean</span></span>|  
|<span data-ttu-id="4ef02-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="4ef02-239">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-239">String</span></span>|  
|<span data-ttu-id="4ef02-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4ef02-240">IS_NULLABLE</span></span>|<span data-ttu-id="4ef02-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-241">Boolean</span></span>|  
|<span data-ttu-id="4ef02-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-242">DATA_TYPE</span></span>|<span data-ttu-id="4ef02-243">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-243">Int32</span></span>|  
|<span data-ttu-id="4ef02-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="4ef02-245">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-245">Int64</span></span>|  
|<span data-ttu-id="4ef02-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="4ef02-247">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-247">Int64</span></span>|  
|<span data-ttu-id="4ef02-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="4ef02-249">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-249">Int32</span></span>|  
|<span data-ttu-id="4ef02-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="4ef02-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="4ef02-251">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-251">Int16</span></span>|  
|<span data-ttu-id="4ef02-252">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-252">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-253">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-253">String</span></span>|  
|<span data-ttu-id="4ef02-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-254">TYPE_NAME</span></span>|<span data-ttu-id="4ef02-255">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-255">String</span></span>|  
|<span data-ttu-id="4ef02-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="4ef02-257">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="4ef02-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="4ef02-258">Catalog</span></span>  
  
|<span data-ttu-id="4ef02-259">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-259">ColumnName</span></span>|<span data-ttu-id="4ef02-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-261">CATALOG_NAME</span></span>|<span data-ttu-id="4ef02-262">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-262">String</span></span>|  
|<span data-ttu-id="4ef02-263">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-263">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-264">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="4ef02-265">索引</span><span class="sxs-lookup"><span data-stu-id="4ef02-265">Indexes</span></span>  
  
|<span data-ttu-id="4ef02-266">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-266">ColumnName</span></span>|<span data-ttu-id="4ef02-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-268">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-269">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-269">String</span></span>|  
|<span data-ttu-id="4ef02-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-271">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-271">String</span></span>|  
|<span data-ttu-id="4ef02-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-272">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-273">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-273">String</span></span>|  
|<span data-ttu-id="4ef02-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-274">INDEX_CATALOG</span></span>|<span data-ttu-id="4ef02-275">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-275">String</span></span>|  
|<span data-ttu-id="4ef02-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="4ef02-277">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-277">String</span></span>|  
|<span data-ttu-id="4ef02-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-278">INDEX_NAME</span></span>|<span data-ttu-id="4ef02-279">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-279">String</span></span>|  
|<span data-ttu-id="4ef02-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="4ef02-280">PRIMARY_KEY</span></span>|<span data-ttu-id="4ef02-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-281">Boolean</span></span>|  
|<span data-ttu-id="4ef02-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="4ef02-282">UNIQUE</span></span>|<span data-ttu-id="4ef02-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-283">Boolean</span></span>|  
|<span data-ttu-id="4ef02-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="4ef02-284">CLUSTERED</span></span>|<span data-ttu-id="4ef02-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-285">Boolean</span></span>|  
|<span data-ttu-id="4ef02-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-286">TYPE</span></span>|<span data-ttu-id="4ef02-287">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-287">Int32</span></span>|  
|<span data-ttu-id="4ef02-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="4ef02-288">FILL_FACTOR</span></span>|<span data-ttu-id="4ef02-289">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-289">Int32</span></span>|  
|<span data-ttu-id="4ef02-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="4ef02-290">INITIAL_SIZE</span></span>|<span data-ttu-id="4ef02-291">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-291">Int32</span></span>|  
|<span data-ttu-id="4ef02-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="4ef02-292">NULLS</span></span>|<span data-ttu-id="4ef02-293">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-293">Int32</span></span>|  
|<span data-ttu-id="4ef02-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="4ef02-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="4ef02-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-295">Boolean</span></span>|  
|<span data-ttu-id="4ef02-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="4ef02-296">AUTO_UPDATE</span></span>|<span data-ttu-id="4ef02-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-297">Boolean</span></span>|  
|<span data-ttu-id="4ef02-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="4ef02-298">NULL_COLLATION</span></span>|<span data-ttu-id="4ef02-299">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-299">Int32</span></span>|  
|<span data-ttu-id="4ef02-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-301">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-301">Int64</span></span>|  
|<span data-ttu-id="4ef02-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-302">COLUMN_NAME</span></span>|<span data-ttu-id="4ef02-303">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-303">String</span></span>|  
|<span data-ttu-id="4ef02-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-304">COLUMN_GUID</span></span>|<span data-ttu-id="4ef02-305">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-305">Guid</span></span>|  
|<span data-ttu-id="4ef02-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-306">COLUMN_PROPID</span></span>|<span data-ttu-id="4ef02-307">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-307">Int64</span></span>|  
|<span data-ttu-id="4ef02-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="4ef02-308">COLLATION</span></span>|<span data-ttu-id="4ef02-309">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-309">Int16</span></span>|  
|<span data-ttu-id="4ef02-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="4ef02-310">CARDINALITY</span></span>|<span data-ttu-id="4ef02-311">十进制</span><span class="sxs-lookup"><span data-stu-id="4ef02-311">Decimal</span></span>|  
|<span data-ttu-id="4ef02-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="4ef02-312">PAGES</span></span>|<span data-ttu-id="4ef02-313">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-313">Int32</span></span>|  
|<span data-ttu-id="4ef02-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-314">FILTER_CONDITION</span></span>|<span data-ttu-id="4ef02-315">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-315">String</span></span>|  
|<span data-ttu-id="4ef02-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-316">INTEGRATED</span></span>|<span data-ttu-id="4ef02-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="4ef02-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="4ef02-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="4ef02-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="4ef02-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="4ef02-320">表</span><span class="sxs-lookup"><span data-stu-id="4ef02-320">Tables</span></span>  
  
- <span data-ttu-id="4ef02-321">列</span><span class="sxs-lookup"><span data-stu-id="4ef02-321">Columns</span></span>  
  
- <span data-ttu-id="4ef02-322">过程</span><span class="sxs-lookup"><span data-stu-id="4ef02-322">Procedures</span></span>  
  
- <span data-ttu-id="4ef02-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4ef02-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="4ef02-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4ef02-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="4ef02-325">Views</span><span class="sxs-lookup"><span data-stu-id="4ef02-325">Views</span></span>  
  
- <span data-ttu-id="4ef02-326">索引</span><span class="sxs-lookup"><span data-stu-id="4ef02-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="4ef02-327">表</span><span class="sxs-lookup"><span data-stu-id="4ef02-327">Tables</span></span>  
  
|<span data-ttu-id="4ef02-328">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-328">ColumnName</span></span>|<span data-ttu-id="4ef02-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-330">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-331">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-331">String</span></span>|  
|<span data-ttu-id="4ef02-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-333">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-333">String</span></span>|  
|<span data-ttu-id="4ef02-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-334">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-335">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-335">String</span></span>|  
|<span data-ttu-id="4ef02-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-336">TABLE_TYPE</span></span>|<span data-ttu-id="4ef02-337">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-337">String</span></span>|  
|<span data-ttu-id="4ef02-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-338">TABLE_GUID</span></span>|<span data-ttu-id="4ef02-339">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-339">Guid</span></span>|  
|<span data-ttu-id="4ef02-340">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-340">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-341">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-341">String</span></span>|  
|<span data-ttu-id="4ef02-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-342">TABLE_PROPID</span></span>|<span data-ttu-id="4ef02-343">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-343">Int64</span></span>|  
|<span data-ttu-id="4ef02-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-344">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-345">DateTime</span></span>|  
|<span data-ttu-id="4ef02-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-346">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4ef02-348">列</span><span class="sxs-lookup"><span data-stu-id="4ef02-348">Columns</span></span>  
  
|<span data-ttu-id="4ef02-349">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-349">ColumnName</span></span>|<span data-ttu-id="4ef02-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-351">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-352">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-352">String</span></span>|  
|<span data-ttu-id="4ef02-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-354">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-354">String</span></span>|  
|<span data-ttu-id="4ef02-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-355">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-356">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-356">String</span></span>|  
|<span data-ttu-id="4ef02-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-357">COLUMN_NAME</span></span>|<span data-ttu-id="4ef02-358">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-358">String</span></span>|  
|<span data-ttu-id="4ef02-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-359">COLUMN_GUID</span></span>|<span data-ttu-id="4ef02-360">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-360">Guid</span></span>|  
|<span data-ttu-id="4ef02-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-361">COLUMN_PROPID</span></span>|<span data-ttu-id="4ef02-362">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-362">Int64</span></span>|  
|<span data-ttu-id="4ef02-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-364">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-364">Int64</span></span>|  
|<span data-ttu-id="4ef02-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="4ef02-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-366">Boolean</span></span>|  
|<span data-ttu-id="4ef02-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="4ef02-368">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-368">String</span></span>|  
|<span data-ttu-id="4ef02-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="4ef02-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="4ef02-370">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-370">Int64</span></span>|  
|<span data-ttu-id="4ef02-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4ef02-371">IS_NULLABLE</span></span>|<span data-ttu-id="4ef02-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-372">Boolean</span></span>|  
|<span data-ttu-id="4ef02-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-373">DATA_TYPE</span></span>|<span data-ttu-id="4ef02-374">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-374">Int32</span></span>|  
|<span data-ttu-id="4ef02-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-375">TYPE_GUID</span></span>|<span data-ttu-id="4ef02-376">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-376">Guid</span></span>|  
|<span data-ttu-id="4ef02-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="4ef02-378">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-378">Int64</span></span>|  
|<span data-ttu-id="4ef02-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="4ef02-380">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-380">Int64</span></span>|  
|<span data-ttu-id="4ef02-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="4ef02-382">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-382">Int32</span></span>|  
|<span data-ttu-id="4ef02-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="4ef02-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="4ef02-384">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-384">Int16</span></span>|  
|<span data-ttu-id="4ef02-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="4ef02-386">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-386">Int64</span></span>|  
|<span data-ttu-id="4ef02-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="4ef02-388">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-388">String</span></span>|  
|<span data-ttu-id="4ef02-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="4ef02-390">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-390">String</span></span>|  
|<span data-ttu-id="4ef02-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="4ef02-392">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-392">String</span></span>|  
|<span data-ttu-id="4ef02-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="4ef02-394">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-394">String</span></span>|  
|<span data-ttu-id="4ef02-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="4ef02-396">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-396">String</span></span>|  
|<span data-ttu-id="4ef02-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-397">COLLATION_NAME</span></span>|<span data-ttu-id="4ef02-398">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-398">String</span></span>|  
|<span data-ttu-id="4ef02-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="4ef02-400">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-400">String</span></span>|  
|<span data-ttu-id="4ef02-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="4ef02-402">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-402">String</span></span>|  
|<span data-ttu-id="4ef02-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-403">DOMAIN_NAME</span></span>|<span data-ttu-id="4ef02-404">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-404">String</span></span>|  
|<span data-ttu-id="4ef02-405">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-405">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-406">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4ef02-407">过程</span><span class="sxs-lookup"><span data-stu-id="4ef02-407">Procedures</span></span>  
  
|<span data-ttu-id="4ef02-408">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-408">ColumnName</span></span>|<span data-ttu-id="4ef02-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="4ef02-411">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-411">String</span></span>|  
|<span data-ttu-id="4ef02-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="4ef02-413">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-413">String</span></span>|  
|<span data-ttu-id="4ef02-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="4ef02-415">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-415">String</span></span>|  
|<span data-ttu-id="4ef02-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4ef02-417">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-417">Int16</span></span>|  
|<span data-ttu-id="4ef02-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="4ef02-419">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-419">String</span></span>|  
|<span data-ttu-id="4ef02-420">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-420">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-421">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-421">String</span></span>|  
|<span data-ttu-id="4ef02-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-422">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-423">DateTime</span></span>|  
|<span data-ttu-id="4ef02-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-424">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="4ef02-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="4ef02-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="4ef02-427">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-427">ColumnName</span></span>|<span data-ttu-id="4ef02-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="4ef02-430">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-430">String</span></span>|  
|<span data-ttu-id="4ef02-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="4ef02-432">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-432">String</span></span>|  
|<span data-ttu-id="4ef02-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="4ef02-434">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-434">String</span></span>|  
|<span data-ttu-id="4ef02-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-435">COLUMN_NAME</span></span>|<span data-ttu-id="4ef02-436">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-436">String</span></span>|  
|<span data-ttu-id="4ef02-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-437">COLUMN_GUID</span></span>|<span data-ttu-id="4ef02-438">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-438">Guid</span></span>|  
|<span data-ttu-id="4ef02-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-439">COLUMN_PROPID</span></span>|<span data-ttu-id="4ef02-440">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-440">Int64</span></span>|  
|<span data-ttu-id="4ef02-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="4ef02-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="4ef02-442">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-442">Int64</span></span>|  
|<span data-ttu-id="4ef02-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-444">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-444">Int64</span></span>|  
|<span data-ttu-id="4ef02-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4ef02-445">IS_NULLABLE</span></span>|<span data-ttu-id="4ef02-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-446">Boolean</span></span>|  
|<span data-ttu-id="4ef02-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-447">DATA_TYPE</span></span>|<span data-ttu-id="4ef02-448">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-448">Int32</span></span>|  
|<span data-ttu-id="4ef02-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-449">TYPE_GUID</span></span>|<span data-ttu-id="4ef02-450">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-450">Guid</span></span>|  
|<span data-ttu-id="4ef02-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="4ef02-452">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-452">Int64</span></span>|  
|<span data-ttu-id="4ef02-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="4ef02-454">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-454">Int64</span></span>|  
|<span data-ttu-id="4ef02-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="4ef02-456">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-456">Int32</span></span>|  
|<span data-ttu-id="4ef02-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="4ef02-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="4ef02-458">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-458">Int16</span></span>|  
|<span data-ttu-id="4ef02-459">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-459">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-460">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-460">String</span></span>|  
|<span data-ttu-id="4ef02-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="4ef02-461">OVERLOAD</span></span>|<span data-ttu-id="4ef02-462">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="4ef02-463">Views</span><span class="sxs-lookup"><span data-stu-id="4ef02-463">Views</span></span>  
  
|<span data-ttu-id="4ef02-464">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-464">ColumnName</span></span>|<span data-ttu-id="4ef02-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-466">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-467">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-467">String</span></span>|  
|<span data-ttu-id="4ef02-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-469">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-469">String</span></span>|  
|<span data-ttu-id="4ef02-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-470">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-471">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-471">String</span></span>|  
|<span data-ttu-id="4ef02-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="4ef02-473">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-473">String</span></span>|  
|<span data-ttu-id="4ef02-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="4ef02-474">CHECK_OPTION</span></span>|<span data-ttu-id="4ef02-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-475">Boolean</span></span>|  
|<span data-ttu-id="4ef02-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="4ef02-476">IS_UPDATABLE</span></span>|<span data-ttu-id="4ef02-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-477">Boolean</span></span>|  
|<span data-ttu-id="4ef02-478">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-478">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-479">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-479">String</span></span>|  
|<span data-ttu-id="4ef02-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-480">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-481">DateTime</span></span>|  
|<span data-ttu-id="4ef02-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-482">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="4ef02-484">索引</span><span class="sxs-lookup"><span data-stu-id="4ef02-484">Indexes</span></span>  
  
|<span data-ttu-id="4ef02-485">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-485">ColumnName</span></span>|<span data-ttu-id="4ef02-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-487">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-488">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-488">String</span></span>|  
|<span data-ttu-id="4ef02-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-490">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-490">String</span></span>|  
|<span data-ttu-id="4ef02-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-491">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-492">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-492">String</span></span>|  
|<span data-ttu-id="4ef02-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-493">INDEX_CATALOG</span></span>|<span data-ttu-id="4ef02-494">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-494">String</span></span>|  
|<span data-ttu-id="4ef02-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="4ef02-496">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-496">String</span></span>|  
|<span data-ttu-id="4ef02-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-497">INDEX_NAME</span></span>|<span data-ttu-id="4ef02-498">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-498">String</span></span>|  
|<span data-ttu-id="4ef02-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="4ef02-499">PRIMARY_KEY</span></span>|<span data-ttu-id="4ef02-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-500">Boolean</span></span>|  
|<span data-ttu-id="4ef02-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="4ef02-501">UNIQUE</span></span>|<span data-ttu-id="4ef02-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-502">Boolean</span></span>|  
|<span data-ttu-id="4ef02-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="4ef02-503">CLUSTERED</span></span>|<span data-ttu-id="4ef02-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-504">Boolean</span></span>|  
|<span data-ttu-id="4ef02-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-505">TYPE</span></span>|<span data-ttu-id="4ef02-506">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-506">Int32</span></span>|  
|<span data-ttu-id="4ef02-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="4ef02-507">FILL_FACTOR</span></span>|<span data-ttu-id="4ef02-508">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-508">Int32</span></span>|  
|<span data-ttu-id="4ef02-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="4ef02-509">INITIAL_SIZE</span></span>|<span data-ttu-id="4ef02-510">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-510">Int32</span></span>|  
|<span data-ttu-id="4ef02-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="4ef02-511">NULLS</span></span>|<span data-ttu-id="4ef02-512">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-512">Int32</span></span>|  
|<span data-ttu-id="4ef02-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="4ef02-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="4ef02-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-514">Boolean</span></span>|  
|<span data-ttu-id="4ef02-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="4ef02-515">AUTO_UPDATE</span></span>|<span data-ttu-id="4ef02-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-516">Boolean</span></span>|  
|<span data-ttu-id="4ef02-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="4ef02-517">NULL_COLLATION</span></span>|<span data-ttu-id="4ef02-518">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-518">Int32</span></span>|  
|<span data-ttu-id="4ef02-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-520">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-520">Int64</span></span>|  
|<span data-ttu-id="4ef02-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-521">COLUMN_NAME</span></span>|<span data-ttu-id="4ef02-522">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-522">String</span></span>|  
|<span data-ttu-id="4ef02-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-523">COLUMN_GUID</span></span>|<span data-ttu-id="4ef02-524">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-524">Guid</span></span>|  
|<span data-ttu-id="4ef02-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-525">COLUMN_PROPID</span></span>|<span data-ttu-id="4ef02-526">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-526">Int64</span></span>|  
|<span data-ttu-id="4ef02-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="4ef02-527">COLLATION</span></span>|<span data-ttu-id="4ef02-528">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-528">Int16</span></span>|  
|<span data-ttu-id="4ef02-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="4ef02-529">CARDINALITY</span></span>|<span data-ttu-id="4ef02-530">十进制</span><span class="sxs-lookup"><span data-stu-id="4ef02-530">Decimal</span></span>|  
|<span data-ttu-id="4ef02-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="4ef02-531">PAGES</span></span>|<span data-ttu-id="4ef02-532">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-532">Int32</span></span>|  
|<span data-ttu-id="4ef02-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-533">FILTER_CONDITION</span></span>|<span data-ttu-id="4ef02-534">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-534">String</span></span>|  
|<span data-ttu-id="4ef02-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-535">INTEGRATED</span></span>|<span data-ttu-id="4ef02-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="4ef02-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="4ef02-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="4ef02-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="4ef02-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="4ef02-539">表</span><span class="sxs-lookup"><span data-stu-id="4ef02-539">Tables</span></span>  
  
- <span data-ttu-id="4ef02-540">列</span><span class="sxs-lookup"><span data-stu-id="4ef02-540">Columns</span></span>  
  
- <span data-ttu-id="4ef02-541">过程</span><span class="sxs-lookup"><span data-stu-id="4ef02-541">Procedures</span></span>  
  
- <span data-ttu-id="4ef02-542">Views</span><span class="sxs-lookup"><span data-stu-id="4ef02-542">Views</span></span>  
  
- <span data-ttu-id="4ef02-543">索引</span><span class="sxs-lookup"><span data-stu-id="4ef02-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="4ef02-544">表</span><span class="sxs-lookup"><span data-stu-id="4ef02-544">Tables</span></span>  
  
|<span data-ttu-id="4ef02-545">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-545">ColumnName</span></span>|<span data-ttu-id="4ef02-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-547">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-548">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-548">String</span></span>|  
|<span data-ttu-id="4ef02-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-550">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-550">String</span></span>|  
|<span data-ttu-id="4ef02-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-551">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-552">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-552">String</span></span>|  
|<span data-ttu-id="4ef02-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-553">TABLE_TYPE</span></span>|<span data-ttu-id="4ef02-554">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-554">String</span></span>|  
|<span data-ttu-id="4ef02-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-555">TABLE_GUID</span></span>|<span data-ttu-id="4ef02-556">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-556">Guid</span></span>|  
|<span data-ttu-id="4ef02-557">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-557">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-558">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-558">String</span></span>|  
|<span data-ttu-id="4ef02-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-559">TABLE_PROPID</span></span>|<span data-ttu-id="4ef02-560">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-560">Int64</span></span>|  
|<span data-ttu-id="4ef02-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-561">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-562">DateTime</span></span>|  
|<span data-ttu-id="4ef02-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-563">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4ef02-565">列</span><span class="sxs-lookup"><span data-stu-id="4ef02-565">Columns</span></span>  
  
|<span data-ttu-id="4ef02-566">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-566">ColumnName</span></span>|<span data-ttu-id="4ef02-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-568">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-569">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-569">String</span></span>|  
|<span data-ttu-id="4ef02-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-571">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-571">String</span></span>|  
|<span data-ttu-id="4ef02-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-572">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-573">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-573">String</span></span>|  
|<span data-ttu-id="4ef02-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-574">COLUMN_NAME</span></span>|<span data-ttu-id="4ef02-575">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-575">String</span></span>|  
|<span data-ttu-id="4ef02-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-576">COLUMN_GUID</span></span>|<span data-ttu-id="4ef02-577">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-577">Guid</span></span>|  
|<span data-ttu-id="4ef02-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-578">COLUMN_PROPID</span></span>|<span data-ttu-id="4ef02-579">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-579">Int64</span></span>|  
|<span data-ttu-id="4ef02-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-581">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-581">Int64</span></span>|  
|<span data-ttu-id="4ef02-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="4ef02-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-583">Boolean</span></span>|  
|<span data-ttu-id="4ef02-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="4ef02-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="4ef02-585">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-585">String</span></span>|  
|<span data-ttu-id="4ef02-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="4ef02-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="4ef02-587">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-587">Int64</span></span>|  
|<span data-ttu-id="4ef02-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="4ef02-588">IS_NULLABLE</span></span>|<span data-ttu-id="4ef02-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-589">Boolean</span></span>|  
|<span data-ttu-id="4ef02-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-590">DATA_TYPE</span></span>|<span data-ttu-id="4ef02-591">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-591">Int32</span></span>|  
|<span data-ttu-id="4ef02-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-592">TYPE_GUID</span></span>|<span data-ttu-id="4ef02-593">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-593">Guid</span></span>|  
|<span data-ttu-id="4ef02-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="4ef02-595">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-595">Int64</span></span>|  
|<span data-ttu-id="4ef02-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4ef02-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="4ef02-597">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-597">Int64</span></span>|  
|<span data-ttu-id="4ef02-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="4ef02-599">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-599">Int32</span></span>|  
|<span data-ttu-id="4ef02-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="4ef02-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="4ef02-601">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-601">Int16</span></span>|  
|<span data-ttu-id="4ef02-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4ef02-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="4ef02-603">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-603">Int64</span></span>|  
|<span data-ttu-id="4ef02-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="4ef02-605">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-605">String</span></span>|  
|<span data-ttu-id="4ef02-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="4ef02-607">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-607">String</span></span>|  
|<span data-ttu-id="4ef02-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="4ef02-609">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-609">String</span></span>|  
|<span data-ttu-id="4ef02-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="4ef02-611">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-611">String</span></span>|  
|<span data-ttu-id="4ef02-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="4ef02-613">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-613">String</span></span>|  
|<span data-ttu-id="4ef02-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-614">COLLATION_NAME</span></span>|<span data-ttu-id="4ef02-615">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-615">String</span></span>|  
|<span data-ttu-id="4ef02-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="4ef02-617">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-617">String</span></span>|  
|<span data-ttu-id="4ef02-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="4ef02-619">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-619">String</span></span>|  
|<span data-ttu-id="4ef02-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-620">DOMAIN_NAME</span></span>|<span data-ttu-id="4ef02-621">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-621">String</span></span>|  
|<span data-ttu-id="4ef02-622">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-622">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-623">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4ef02-624">过程</span><span class="sxs-lookup"><span data-stu-id="4ef02-624">Procedures</span></span>  
  
|<span data-ttu-id="4ef02-625">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-625">ColumnName</span></span>|<span data-ttu-id="4ef02-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="4ef02-628">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-628">String</span></span>|  
|<span data-ttu-id="4ef02-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="4ef02-630">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-630">String</span></span>|  
|<span data-ttu-id="4ef02-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="4ef02-632">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-632">String</span></span>|  
|<span data-ttu-id="4ef02-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="4ef02-634">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-634">Int16</span></span>|  
|<span data-ttu-id="4ef02-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="4ef02-636">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-636">String</span></span>|  
|<span data-ttu-id="4ef02-637">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-637">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-638">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-638">String</span></span>|  
|<span data-ttu-id="4ef02-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-639">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-640">DateTime</span></span>|  
|<span data-ttu-id="4ef02-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-641">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="4ef02-643">Views</span><span class="sxs-lookup"><span data-stu-id="4ef02-643">Views</span></span>  
  
|<span data-ttu-id="4ef02-644">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-644">ColumnName</span></span>|<span data-ttu-id="4ef02-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-646">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-647">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-647">String</span></span>|  
|<span data-ttu-id="4ef02-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-649">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-649">String</span></span>|  
|<span data-ttu-id="4ef02-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-650">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-651">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-651">String</span></span>|  
|<span data-ttu-id="4ef02-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="4ef02-653">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-653">String</span></span>|  
|<span data-ttu-id="4ef02-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="4ef02-654">CHECK_OPTION</span></span>|<span data-ttu-id="4ef02-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-655">Boolean</span></span>|  
|<span data-ttu-id="4ef02-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="4ef02-656">IS_UPDATABLE</span></span>|<span data-ttu-id="4ef02-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-657">Boolean</span></span>|  
|<span data-ttu-id="4ef02-658">描述</span><span class="sxs-lookup"><span data-stu-id="4ef02-658">DESCRIPTION</span></span>|<span data-ttu-id="4ef02-659">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-659">String</span></span>|  
|<span data-ttu-id="4ef02-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-660">DATE_CREATED</span></span>|<span data-ttu-id="4ef02-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-661">DateTime</span></span>|  
|<span data-ttu-id="4ef02-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="4ef02-662">DATE_MODIFIED</span></span>|<span data-ttu-id="4ef02-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ef02-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="4ef02-664">索引</span><span class="sxs-lookup"><span data-stu-id="4ef02-664">Indexes</span></span>  
  
|<span data-ttu-id="4ef02-665">列名</span><span class="sxs-lookup"><span data-stu-id="4ef02-665">ColumnName</span></span>|<span data-ttu-id="4ef02-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ef02-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="4ef02-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-667">TABLE_CATALOG</span></span>|<span data-ttu-id="4ef02-668">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-668">String</span></span>|  
|<span data-ttu-id="4ef02-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="4ef02-670">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-670">String</span></span>|  
|<span data-ttu-id="4ef02-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-671">TABLE_NAME</span></span>|<span data-ttu-id="4ef02-672">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-672">String</span></span>|  
|<span data-ttu-id="4ef02-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4ef02-673">INDEX_CATALOG</span></span>|<span data-ttu-id="4ef02-674">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-674">String</span></span>|  
|<span data-ttu-id="4ef02-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4ef02-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="4ef02-676">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-676">String</span></span>|  
|<span data-ttu-id="4ef02-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-677">INDEX_NAME</span></span>|<span data-ttu-id="4ef02-678">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-678">String</span></span>|  
|<span data-ttu-id="4ef02-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="4ef02-679">PRIMARY_KEY</span></span>|<span data-ttu-id="4ef02-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-680">Boolean</span></span>|  
|<span data-ttu-id="4ef02-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="4ef02-681">UNIQUE</span></span>|<span data-ttu-id="4ef02-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-682">Boolean</span></span>|  
|<span data-ttu-id="4ef02-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="4ef02-683">CLUSTERED</span></span>|<span data-ttu-id="4ef02-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-684">Boolean</span></span>|  
|<span data-ttu-id="4ef02-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="4ef02-685">TYPE</span></span>|<span data-ttu-id="4ef02-686">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-686">Int32</span></span>|  
|<span data-ttu-id="4ef02-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="4ef02-687">FILL_FACTOR</span></span>|<span data-ttu-id="4ef02-688">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-688">Int32</span></span>|  
|<span data-ttu-id="4ef02-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="4ef02-689">INITIAL_SIZE</span></span>|<span data-ttu-id="4ef02-690">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-690">Int32</span></span>|  
|<span data-ttu-id="4ef02-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="4ef02-691">NULLS</span></span>|<span data-ttu-id="4ef02-692">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-692">Int32</span></span>|  
|<span data-ttu-id="4ef02-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="4ef02-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="4ef02-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-694">Boolean</span></span>|  
|<span data-ttu-id="4ef02-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="4ef02-695">AUTO_UPDATE</span></span>|<span data-ttu-id="4ef02-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-696">Boolean</span></span>|  
|<span data-ttu-id="4ef02-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="4ef02-697">NULL_COLLATION</span></span>|<span data-ttu-id="4ef02-698">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-698">Int32</span></span>|  
|<span data-ttu-id="4ef02-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="4ef02-700">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-700">Int64</span></span>|  
|<span data-ttu-id="4ef02-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4ef02-701">COLUMN_NAME</span></span>|<span data-ttu-id="4ef02-702">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-702">String</span></span>|  
|<span data-ttu-id="4ef02-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-703">COLUMN_GUID</span></span>|<span data-ttu-id="4ef02-704">GUID</span><span class="sxs-lookup"><span data-stu-id="4ef02-704">Guid</span></span>|  
|<span data-ttu-id="4ef02-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="4ef02-705">COLUMN_PROPID</span></span>|<span data-ttu-id="4ef02-706">Int64</span><span class="sxs-lookup"><span data-stu-id="4ef02-706">Int64</span></span>|  
|<span data-ttu-id="4ef02-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="4ef02-707">COLLATION</span></span>|<span data-ttu-id="4ef02-708">Int16</span><span class="sxs-lookup"><span data-stu-id="4ef02-708">Int16</span></span>|  
|<span data-ttu-id="4ef02-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="4ef02-709">CARDINALITY</span></span>|<span data-ttu-id="4ef02-710">十进制</span><span class="sxs-lookup"><span data-stu-id="4ef02-710">Decimal</span></span>|  
|<span data-ttu-id="4ef02-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="4ef02-711">PAGES</span></span>|<span data-ttu-id="4ef02-712">Int32</span><span class="sxs-lookup"><span data-stu-id="4ef02-712">Int32</span></span>|  
|<span data-ttu-id="4ef02-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="4ef02-713">FILTER_CONDITION</span></span>|<span data-ttu-id="4ef02-714">String</span><span class="sxs-lookup"><span data-stu-id="4ef02-714">String</span></span>|  
|<span data-ttu-id="4ef02-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="4ef02-715">INTEGRATED</span></span>|<span data-ttu-id="4ef02-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="4ef02-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ef02-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ef02-717">See also</span></span>

- [<span data-ttu-id="4ef02-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="4ef02-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
