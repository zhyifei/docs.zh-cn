---
title: "OLE DB 架构集合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33e794559abd7f619f7431683f06e59705b57d41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="467a8-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="467a8-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="467a8-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="467a8-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="467a8-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="467a8-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="467a8-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="467a8-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="467a8-106">表</span><span class="sxs-lookup"><span data-stu-id="467a8-106">Tables</span></span>  
  
-   <span data-ttu-id="467a8-107">Columns</span><span class="sxs-lookup"><span data-stu-id="467a8-107">Columns</span></span>  
  
-   <span data-ttu-id="467a8-108">过程</span><span class="sxs-lookup"><span data-stu-id="467a8-108">Procedures</span></span>  
  
-   <span data-ttu-id="467a8-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="467a8-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="467a8-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="467a8-110">Catalog</span></span>  
  
-   <span data-ttu-id="467a8-111">索引</span><span class="sxs-lookup"><span data-stu-id="467a8-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="467a8-112">表</span><span class="sxs-lookup"><span data-stu-id="467a8-112">Tables</span></span>  
  
|<span data-ttu-id="467a8-113">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-113">ColumnName</span></span>|<span data-ttu-id="467a8-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-115">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-116">String</span><span class="sxs-lookup"><span data-stu-id="467a8-116">String</span></span>|  
|<span data-ttu-id="467a8-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-118">String</span><span class="sxs-lookup"><span data-stu-id="467a8-118">String</span></span>|  
|<span data-ttu-id="467a8-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-119">TABLE_NAME</span></span>|<span data-ttu-id="467a8-120">String</span><span class="sxs-lookup"><span data-stu-id="467a8-120">String</span></span>|  
|<span data-ttu-id="467a8-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-121">TABLE_TYPE</span></span>|<span data-ttu-id="467a8-122">String</span><span class="sxs-lookup"><span data-stu-id="467a8-122">String</span></span>|  
|<span data-ttu-id="467a8-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-123">TABLE_GUID</span></span>|<span data-ttu-id="467a8-124">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-124">Guid</span></span>|  
|<span data-ttu-id="467a8-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-125">DESCRIPTION</span></span>|<span data-ttu-id="467a8-126">String</span><span class="sxs-lookup"><span data-stu-id="467a8-126">String</span></span>|  
|<span data-ttu-id="467a8-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-127">TABLE_PROPID</span></span>|<span data-ttu-id="467a8-128">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-128">Int64</span></span>|  
|<span data-ttu-id="467a8-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-129">DATE_CREATED</span></span>|<span data-ttu-id="467a8-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-130">DateTime</span></span>|  
|<span data-ttu-id="467a8-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-131">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="467a8-133">Columns</span><span class="sxs-lookup"><span data-stu-id="467a8-133">Columns</span></span>  
  
|<span data-ttu-id="467a8-134">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-134">ColumnName</span></span>|<span data-ttu-id="467a8-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-136">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-137">String</span><span class="sxs-lookup"><span data-stu-id="467a8-137">String</span></span>|  
|<span data-ttu-id="467a8-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-139">String</span><span class="sxs-lookup"><span data-stu-id="467a8-139">String</span></span>|  
|<span data-ttu-id="467a8-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-140">TABLE_NAME</span></span>|<span data-ttu-id="467a8-141">String</span><span class="sxs-lookup"><span data-stu-id="467a8-141">String</span></span>|  
|<span data-ttu-id="467a8-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-142">COLUMN_NAME</span></span>|<span data-ttu-id="467a8-143">String</span><span class="sxs-lookup"><span data-stu-id="467a8-143">String</span></span>|  
|<span data-ttu-id="467a8-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-144">COLUMN_GUID</span></span>|<span data-ttu-id="467a8-145">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-145">Guid</span></span>|  
|<span data-ttu-id="467a8-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-146">COLUMN_PROPID</span></span>|<span data-ttu-id="467a8-147">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-147">Int64</span></span>|  
|<span data-ttu-id="467a8-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-149">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-149">Int64</span></span>|  
|<span data-ttu-id="467a8-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="467a8-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-151">Boolean</span></span>|  
|<span data-ttu-id="467a8-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="467a8-153">String</span><span class="sxs-lookup"><span data-stu-id="467a8-153">String</span></span>|  
|<span data-ttu-id="467a8-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="467a8-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="467a8-155">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-155">Int64</span></span>|  
|<span data-ttu-id="467a8-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="467a8-156">IS_NULLABLE</span></span>|<span data-ttu-id="467a8-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-157">Boolean</span></span>|  
|<span data-ttu-id="467a8-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-158">DATA_TYPE</span></span>|<span data-ttu-id="467a8-159">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-159">Int32</span></span>|  
|<span data-ttu-id="467a8-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-160">TYPE_GUID</span></span>|<span data-ttu-id="467a8-161">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-161">Guid</span></span>|  
|<span data-ttu-id="467a8-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="467a8-163">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-163">Int64</span></span>|  
|<span data-ttu-id="467a8-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="467a8-165">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-165">Int64</span></span>|  
|<span data-ttu-id="467a8-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="467a8-167">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-167">Int32</span></span>|  
|<span data-ttu-id="467a8-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="467a8-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="467a8-169">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-169">Int16</span></span>|  
|<span data-ttu-id="467a8-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="467a8-171">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-171">Int64</span></span>|  
|<span data-ttu-id="467a8-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="467a8-173">String</span><span class="sxs-lookup"><span data-stu-id="467a8-173">String</span></span>|  
|<span data-ttu-id="467a8-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="467a8-175">String</span><span class="sxs-lookup"><span data-stu-id="467a8-175">String</span></span>|  
|<span data-ttu-id="467a8-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="467a8-177">String</span><span class="sxs-lookup"><span data-stu-id="467a8-177">String</span></span>|  
|<span data-ttu-id="467a8-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="467a8-179">String</span><span class="sxs-lookup"><span data-stu-id="467a8-179">String</span></span>|  
|<span data-ttu-id="467a8-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="467a8-181">String</span><span class="sxs-lookup"><span data-stu-id="467a8-181">String</span></span>|  
|<span data-ttu-id="467a8-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-182">COLLATION_NAME</span></span>|<span data-ttu-id="467a8-183">String</span><span class="sxs-lookup"><span data-stu-id="467a8-183">String</span></span>|  
|<span data-ttu-id="467a8-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="467a8-185">String</span><span class="sxs-lookup"><span data-stu-id="467a8-185">String</span></span>|  
|<span data-ttu-id="467a8-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="467a8-187">String</span><span class="sxs-lookup"><span data-stu-id="467a8-187">String</span></span>|  
|<span data-ttu-id="467a8-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-188">DOMAIN_NAME</span></span>|<span data-ttu-id="467a8-189">String</span><span class="sxs-lookup"><span data-stu-id="467a8-189">String</span></span>|  
|<span data-ttu-id="467a8-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-190">DESCRIPTION</span></span>|<span data-ttu-id="467a8-191">String</span><span class="sxs-lookup"><span data-stu-id="467a8-191">String</span></span>|  
|<span data-ttu-id="467a8-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="467a8-192">COLUMN_LCID</span></span>|<span data-ttu-id="467a8-193">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-193">Int32</span></span>|  
|<span data-ttu-id="467a8-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="467a8-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="467a8-195">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-195">Int32</span></span>|  
|<span data-ttu-id="467a8-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="467a8-196">COLUMN_SORTID</span></span>|<span data-ttu-id="467a8-197">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-197">Int32</span></span>|  
|<span data-ttu-id="467a8-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="467a8-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="467a8-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="467a8-199">Byte[]</span></span>|  
|<span data-ttu-id="467a8-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="467a8-200">IS_COMPUTED</span></span>|<span data-ttu-id="467a8-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="467a8-202">过程</span><span class="sxs-lookup"><span data-stu-id="467a8-202">Procedures</span></span>  
  
|<span data-ttu-id="467a8-203">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-203">ColumnName</span></span>|<span data-ttu-id="467a8-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="467a8-206">String</span><span class="sxs-lookup"><span data-stu-id="467a8-206">String</span></span>|  
|<span data-ttu-id="467a8-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="467a8-208">String</span><span class="sxs-lookup"><span data-stu-id="467a8-208">String</span></span>|  
|<span data-ttu-id="467a8-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="467a8-210">String</span><span class="sxs-lookup"><span data-stu-id="467a8-210">String</span></span>|  
|<span data-ttu-id="467a8-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="467a8-212">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-212">Int16</span></span>|  
|<span data-ttu-id="467a8-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="467a8-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="467a8-214">String</span><span class="sxs-lookup"><span data-stu-id="467a8-214">String</span></span>|  
|<span data-ttu-id="467a8-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-215">DESCRIPTION</span></span>|<span data-ttu-id="467a8-216">String</span><span class="sxs-lookup"><span data-stu-id="467a8-216">String</span></span>|  
|<span data-ttu-id="467a8-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-217">DATE_CREATED</span></span>|<span data-ttu-id="467a8-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-218">DateTime</span></span>|  
|<span data-ttu-id="467a8-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-219">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="467a8-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="467a8-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="467a8-222">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-222">ColumnName</span></span>|<span data-ttu-id="467a8-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="467a8-225">String</span><span class="sxs-lookup"><span data-stu-id="467a8-225">String</span></span>|  
|<span data-ttu-id="467a8-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="467a8-227">String</span><span class="sxs-lookup"><span data-stu-id="467a8-227">String</span></span>|  
|<span data-ttu-id="467a8-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="467a8-229">String</span><span class="sxs-lookup"><span data-stu-id="467a8-229">String</span></span>|  
|<span data-ttu-id="467a8-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-230">PARAMETER_NAME</span></span>|<span data-ttu-id="467a8-231">String</span><span class="sxs-lookup"><span data-stu-id="467a8-231">String</span></span>|  
|<span data-ttu-id="467a8-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-233">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-233">Int32</span></span>|  
|<span data-ttu-id="467a8-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="467a8-235">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-235">Int32</span></span>|  
|<span data-ttu-id="467a8-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="467a8-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-237">Boolean</span></span>|  
|<span data-ttu-id="467a8-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="467a8-239">String</span><span class="sxs-lookup"><span data-stu-id="467a8-239">String</span></span>|  
|<span data-ttu-id="467a8-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="467a8-240">IS_NULLABLE</span></span>|<span data-ttu-id="467a8-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-241">Boolean</span></span>|  
|<span data-ttu-id="467a8-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-242">DATA_TYPE</span></span>|<span data-ttu-id="467a8-243">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-243">Int32</span></span>|  
|<span data-ttu-id="467a8-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="467a8-245">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-245">Int64</span></span>|  
|<span data-ttu-id="467a8-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="467a8-247">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-247">Int64</span></span>|  
|<span data-ttu-id="467a8-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="467a8-249">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-249">Int32</span></span>|  
|<span data-ttu-id="467a8-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="467a8-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="467a8-251">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-251">Int16</span></span>|  
|<span data-ttu-id="467a8-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-252">DESCRIPTION</span></span>|<span data-ttu-id="467a8-253">String</span><span class="sxs-lookup"><span data-stu-id="467a8-253">String</span></span>|  
|<span data-ttu-id="467a8-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-254">TYPE_NAME</span></span>|<span data-ttu-id="467a8-255">String</span><span class="sxs-lookup"><span data-stu-id="467a8-255">String</span></span>|  
|<span data-ttu-id="467a8-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="467a8-257">String</span><span class="sxs-lookup"><span data-stu-id="467a8-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="467a8-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="467a8-258">Catalog</span></span>  
  
|<span data-ttu-id="467a8-259">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-259">ColumnName</span></span>|<span data-ttu-id="467a8-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-261">CATALOG_NAME</span></span>|<span data-ttu-id="467a8-262">String</span><span class="sxs-lookup"><span data-stu-id="467a8-262">String</span></span>|  
|<span data-ttu-id="467a8-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-263">DESCRIPTION</span></span>|<span data-ttu-id="467a8-264">String</span><span class="sxs-lookup"><span data-stu-id="467a8-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="467a8-265">索引</span><span class="sxs-lookup"><span data-stu-id="467a8-265">Indexes</span></span>  
  
|<span data-ttu-id="467a8-266">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-266">ColumnName</span></span>|<span data-ttu-id="467a8-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-268">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-269">String</span><span class="sxs-lookup"><span data-stu-id="467a8-269">String</span></span>|  
|<span data-ttu-id="467a8-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-271">String</span><span class="sxs-lookup"><span data-stu-id="467a8-271">String</span></span>|  
|<span data-ttu-id="467a8-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-272">TABLE_NAME</span></span>|<span data-ttu-id="467a8-273">String</span><span class="sxs-lookup"><span data-stu-id="467a8-273">String</span></span>|  
|<span data-ttu-id="467a8-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-274">INDEX_CATALOG</span></span>|<span data-ttu-id="467a8-275">String</span><span class="sxs-lookup"><span data-stu-id="467a8-275">String</span></span>|  
|<span data-ttu-id="467a8-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="467a8-277">String</span><span class="sxs-lookup"><span data-stu-id="467a8-277">String</span></span>|  
|<span data-ttu-id="467a8-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-278">INDEX_NAME</span></span>|<span data-ttu-id="467a8-279">String</span><span class="sxs-lookup"><span data-stu-id="467a8-279">String</span></span>|  
|<span data-ttu-id="467a8-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="467a8-280">PRIMARY_KEY</span></span>|<span data-ttu-id="467a8-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-281">Boolean</span></span>|  
|<span data-ttu-id="467a8-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="467a8-282">UNIQUE</span></span>|<span data-ttu-id="467a8-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-283">Boolean</span></span>|  
|<span data-ttu-id="467a8-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="467a8-284">CLUSTERED</span></span>|<span data-ttu-id="467a8-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-285">Boolean</span></span>|  
|<span data-ttu-id="467a8-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-286">TYPE</span></span>|<span data-ttu-id="467a8-287">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-287">Int32</span></span>|  
|<span data-ttu-id="467a8-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="467a8-288">FILL_FACTOR</span></span>|<span data-ttu-id="467a8-289">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-289">Int32</span></span>|  
|<span data-ttu-id="467a8-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="467a8-290">INITIAL_SIZE</span></span>|<span data-ttu-id="467a8-291">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-291">Int32</span></span>|  
|<span data-ttu-id="467a8-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="467a8-292">NULLS</span></span>|<span data-ttu-id="467a8-293">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-293">Int32</span></span>|  
|<span data-ttu-id="467a8-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="467a8-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="467a8-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-295">Boolean</span></span>|  
|<span data-ttu-id="467a8-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="467a8-296">AUTO_UPDATE</span></span>|<span data-ttu-id="467a8-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-297">Boolean</span></span>|  
|<span data-ttu-id="467a8-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="467a8-298">NULL_COLLATION</span></span>|<span data-ttu-id="467a8-299">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-299">Int32</span></span>|  
|<span data-ttu-id="467a8-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-301">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-301">Int64</span></span>|  
|<span data-ttu-id="467a8-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-302">COLUMN_NAME</span></span>|<span data-ttu-id="467a8-303">String</span><span class="sxs-lookup"><span data-stu-id="467a8-303">String</span></span>|  
|<span data-ttu-id="467a8-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-304">COLUMN_GUID</span></span>|<span data-ttu-id="467a8-305">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-305">Guid</span></span>|  
|<span data-ttu-id="467a8-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-306">COLUMN_PROPID</span></span>|<span data-ttu-id="467a8-307">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-307">Int64</span></span>|  
|<span data-ttu-id="467a8-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="467a8-308">COLLATION</span></span>|<span data-ttu-id="467a8-309">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-309">Int16</span></span>|  
|<span data-ttu-id="467a8-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="467a8-310">CARDINALITY</span></span>|<span data-ttu-id="467a8-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="467a8-311">Decimal</span></span>|  
|<span data-ttu-id="467a8-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="467a8-312">PAGES</span></span>|<span data-ttu-id="467a8-313">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-313">Int32</span></span>|  
|<span data-ttu-id="467a8-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="467a8-314">FILTER_CONDITION</span></span>|<span data-ttu-id="467a8-315">String</span><span class="sxs-lookup"><span data-stu-id="467a8-315">String</span></span>|  
|<span data-ttu-id="467a8-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="467a8-316">INTEGRATED</span></span>|<span data-ttu-id="467a8-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="467a8-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="467a8-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="467a8-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="467a8-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="467a8-320">表</span><span class="sxs-lookup"><span data-stu-id="467a8-320">Tables</span></span>  
  
-   <span data-ttu-id="467a8-321">Columns</span><span class="sxs-lookup"><span data-stu-id="467a8-321">Columns</span></span>  
  
-   <span data-ttu-id="467a8-322">过程</span><span class="sxs-lookup"><span data-stu-id="467a8-322">Procedures</span></span>  
  
-   <span data-ttu-id="467a8-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="467a8-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="467a8-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="467a8-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="467a8-325">视图</span><span class="sxs-lookup"><span data-stu-id="467a8-325">Views</span></span>  
  
-   <span data-ttu-id="467a8-326">索引</span><span class="sxs-lookup"><span data-stu-id="467a8-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="467a8-327">表</span><span class="sxs-lookup"><span data-stu-id="467a8-327">Tables</span></span>  
  
|<span data-ttu-id="467a8-328">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-328">ColumnName</span></span>|<span data-ttu-id="467a8-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-330">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-331">String</span><span class="sxs-lookup"><span data-stu-id="467a8-331">String</span></span>|  
|<span data-ttu-id="467a8-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-333">String</span><span class="sxs-lookup"><span data-stu-id="467a8-333">String</span></span>|  
|<span data-ttu-id="467a8-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-334">TABLE_NAME</span></span>|<span data-ttu-id="467a8-335">String</span><span class="sxs-lookup"><span data-stu-id="467a8-335">String</span></span>|  
|<span data-ttu-id="467a8-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-336">TABLE_TYPE</span></span>|<span data-ttu-id="467a8-337">String</span><span class="sxs-lookup"><span data-stu-id="467a8-337">String</span></span>|  
|<span data-ttu-id="467a8-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-338">TABLE_GUID</span></span>|<span data-ttu-id="467a8-339">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-339">Guid</span></span>|  
|<span data-ttu-id="467a8-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-340">DESCRIPTION</span></span>|<span data-ttu-id="467a8-341">String</span><span class="sxs-lookup"><span data-stu-id="467a8-341">String</span></span>|  
|<span data-ttu-id="467a8-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-342">TABLE_PROPID</span></span>|<span data-ttu-id="467a8-343">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-343">Int64</span></span>|  
|<span data-ttu-id="467a8-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-344">DATE_CREATED</span></span>|<span data-ttu-id="467a8-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-345">DateTime</span></span>|  
|<span data-ttu-id="467a8-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-346">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="467a8-348">Columns</span><span class="sxs-lookup"><span data-stu-id="467a8-348">Columns</span></span>  
  
|<span data-ttu-id="467a8-349">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-349">ColumnName</span></span>|<span data-ttu-id="467a8-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-351">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-352">String</span><span class="sxs-lookup"><span data-stu-id="467a8-352">String</span></span>|  
|<span data-ttu-id="467a8-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-354">String</span><span class="sxs-lookup"><span data-stu-id="467a8-354">String</span></span>|  
|<span data-ttu-id="467a8-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-355">TABLE_NAME</span></span>|<span data-ttu-id="467a8-356">String</span><span class="sxs-lookup"><span data-stu-id="467a8-356">String</span></span>|  
|<span data-ttu-id="467a8-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-357">COLUMN_NAME</span></span>|<span data-ttu-id="467a8-358">String</span><span class="sxs-lookup"><span data-stu-id="467a8-358">String</span></span>|  
|<span data-ttu-id="467a8-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-359">COLUMN_GUID</span></span>|<span data-ttu-id="467a8-360">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-360">Guid</span></span>|  
|<span data-ttu-id="467a8-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-361">COLUMN_PROPID</span></span>|<span data-ttu-id="467a8-362">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-362">Int64</span></span>|  
|<span data-ttu-id="467a8-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-364">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-364">Int64</span></span>|  
|<span data-ttu-id="467a8-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="467a8-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-366">Boolean</span></span>|  
|<span data-ttu-id="467a8-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="467a8-368">String</span><span class="sxs-lookup"><span data-stu-id="467a8-368">String</span></span>|  
|<span data-ttu-id="467a8-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="467a8-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="467a8-370">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-370">Int64</span></span>|  
|<span data-ttu-id="467a8-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="467a8-371">IS_NULLABLE</span></span>|<span data-ttu-id="467a8-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-372">Boolean</span></span>|  
|<span data-ttu-id="467a8-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-373">DATA_TYPE</span></span>|<span data-ttu-id="467a8-374">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-374">Int32</span></span>|  
|<span data-ttu-id="467a8-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-375">TYPE_GUID</span></span>|<span data-ttu-id="467a8-376">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-376">Guid</span></span>|  
|<span data-ttu-id="467a8-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="467a8-378">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-378">Int64</span></span>|  
|<span data-ttu-id="467a8-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="467a8-380">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-380">Int64</span></span>|  
|<span data-ttu-id="467a8-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="467a8-382">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-382">Int32</span></span>|  
|<span data-ttu-id="467a8-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="467a8-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="467a8-384">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-384">Int16</span></span>|  
|<span data-ttu-id="467a8-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="467a8-386">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-386">Int64</span></span>|  
|<span data-ttu-id="467a8-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="467a8-388">String</span><span class="sxs-lookup"><span data-stu-id="467a8-388">String</span></span>|  
|<span data-ttu-id="467a8-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="467a8-390">String</span><span class="sxs-lookup"><span data-stu-id="467a8-390">String</span></span>|  
|<span data-ttu-id="467a8-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="467a8-392">String</span><span class="sxs-lookup"><span data-stu-id="467a8-392">String</span></span>|  
|<span data-ttu-id="467a8-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="467a8-394">String</span><span class="sxs-lookup"><span data-stu-id="467a8-394">String</span></span>|  
|<span data-ttu-id="467a8-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="467a8-396">String</span><span class="sxs-lookup"><span data-stu-id="467a8-396">String</span></span>|  
|<span data-ttu-id="467a8-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-397">COLLATION_NAME</span></span>|<span data-ttu-id="467a8-398">String</span><span class="sxs-lookup"><span data-stu-id="467a8-398">String</span></span>|  
|<span data-ttu-id="467a8-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="467a8-400">String</span><span class="sxs-lookup"><span data-stu-id="467a8-400">String</span></span>|  
|<span data-ttu-id="467a8-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="467a8-402">String</span><span class="sxs-lookup"><span data-stu-id="467a8-402">String</span></span>|  
|<span data-ttu-id="467a8-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-403">DOMAIN_NAME</span></span>|<span data-ttu-id="467a8-404">String</span><span class="sxs-lookup"><span data-stu-id="467a8-404">String</span></span>|  
|<span data-ttu-id="467a8-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-405">DESCRIPTION</span></span>|<span data-ttu-id="467a8-406">String</span><span class="sxs-lookup"><span data-stu-id="467a8-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="467a8-407">过程</span><span class="sxs-lookup"><span data-stu-id="467a8-407">Procedures</span></span>  
  
|<span data-ttu-id="467a8-408">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-408">ColumnName</span></span>|<span data-ttu-id="467a8-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="467a8-411">String</span><span class="sxs-lookup"><span data-stu-id="467a8-411">String</span></span>|  
|<span data-ttu-id="467a8-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="467a8-413">String</span><span class="sxs-lookup"><span data-stu-id="467a8-413">String</span></span>|  
|<span data-ttu-id="467a8-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="467a8-415">String</span><span class="sxs-lookup"><span data-stu-id="467a8-415">String</span></span>|  
|<span data-ttu-id="467a8-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="467a8-417">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-417">Int16</span></span>|  
|<span data-ttu-id="467a8-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="467a8-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="467a8-419">String</span><span class="sxs-lookup"><span data-stu-id="467a8-419">String</span></span>|  
|<span data-ttu-id="467a8-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-420">DESCRIPTION</span></span>|<span data-ttu-id="467a8-421">String</span><span class="sxs-lookup"><span data-stu-id="467a8-421">String</span></span>|  
|<span data-ttu-id="467a8-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-422">DATE_CREATED</span></span>|<span data-ttu-id="467a8-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-423">DateTime</span></span>|  
|<span data-ttu-id="467a8-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-424">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="467a8-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="467a8-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="467a8-427">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-427">ColumnName</span></span>|<span data-ttu-id="467a8-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="467a8-430">String</span><span class="sxs-lookup"><span data-stu-id="467a8-430">String</span></span>|  
|<span data-ttu-id="467a8-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="467a8-432">String</span><span class="sxs-lookup"><span data-stu-id="467a8-432">String</span></span>|  
|<span data-ttu-id="467a8-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="467a8-434">String</span><span class="sxs-lookup"><span data-stu-id="467a8-434">String</span></span>|  
|<span data-ttu-id="467a8-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-435">COLUMN_NAME</span></span>|<span data-ttu-id="467a8-436">String</span><span class="sxs-lookup"><span data-stu-id="467a8-436">String</span></span>|  
|<span data-ttu-id="467a8-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-437">COLUMN_GUID</span></span>|<span data-ttu-id="467a8-438">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-438">Guid</span></span>|  
|<span data-ttu-id="467a8-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-439">COLUMN_PROPID</span></span>|<span data-ttu-id="467a8-440">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-440">Int64</span></span>|  
|<span data-ttu-id="467a8-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="467a8-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="467a8-442">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-442">Int64</span></span>|  
|<span data-ttu-id="467a8-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-444">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-444">Int64</span></span>|  
|<span data-ttu-id="467a8-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="467a8-445">IS_NULLABLE</span></span>|<span data-ttu-id="467a8-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-446">Boolean</span></span>|  
|<span data-ttu-id="467a8-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-447">DATA_TYPE</span></span>|<span data-ttu-id="467a8-448">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-448">Int32</span></span>|  
|<span data-ttu-id="467a8-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-449">TYPE_GUID</span></span>|<span data-ttu-id="467a8-450">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-450">Guid</span></span>|  
|<span data-ttu-id="467a8-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="467a8-452">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-452">Int64</span></span>|  
|<span data-ttu-id="467a8-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="467a8-454">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-454">Int64</span></span>|  
|<span data-ttu-id="467a8-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="467a8-456">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-456">Int32</span></span>|  
|<span data-ttu-id="467a8-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="467a8-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="467a8-458">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-458">Int16</span></span>|  
|<span data-ttu-id="467a8-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-459">DESCRIPTION</span></span>|<span data-ttu-id="467a8-460">String</span><span class="sxs-lookup"><span data-stu-id="467a8-460">String</span></span>|  
|<span data-ttu-id="467a8-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="467a8-461">OVERLOAD</span></span>|<span data-ttu-id="467a8-462">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="467a8-463">视图</span><span class="sxs-lookup"><span data-stu-id="467a8-463">Views</span></span>  
  
|<span data-ttu-id="467a8-464">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-464">ColumnName</span></span>|<span data-ttu-id="467a8-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-466">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-467">String</span><span class="sxs-lookup"><span data-stu-id="467a8-467">String</span></span>|  
|<span data-ttu-id="467a8-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-469">String</span><span class="sxs-lookup"><span data-stu-id="467a8-469">String</span></span>|  
|<span data-ttu-id="467a8-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-470">TABLE_NAME</span></span>|<span data-ttu-id="467a8-471">String</span><span class="sxs-lookup"><span data-stu-id="467a8-471">String</span></span>|  
|<span data-ttu-id="467a8-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="467a8-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="467a8-473">String</span><span class="sxs-lookup"><span data-stu-id="467a8-473">String</span></span>|  
|<span data-ttu-id="467a8-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-474">CHECK_OPTION</span></span>|<span data-ttu-id="467a8-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-475">Boolean</span></span>|  
|<span data-ttu-id="467a8-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="467a8-476">IS_UPDATABLE</span></span>|<span data-ttu-id="467a8-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-477">Boolean</span></span>|  
|<span data-ttu-id="467a8-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-478">DESCRIPTION</span></span>|<span data-ttu-id="467a8-479">String</span><span class="sxs-lookup"><span data-stu-id="467a8-479">String</span></span>|  
|<span data-ttu-id="467a8-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-480">DATE_CREATED</span></span>|<span data-ttu-id="467a8-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-481">DateTime</span></span>|  
|<span data-ttu-id="467a8-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-482">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="467a8-484">索引</span><span class="sxs-lookup"><span data-stu-id="467a8-484">Indexes</span></span>  
  
|<span data-ttu-id="467a8-485">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-485">ColumnName</span></span>|<span data-ttu-id="467a8-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-487">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-488">String</span><span class="sxs-lookup"><span data-stu-id="467a8-488">String</span></span>|  
|<span data-ttu-id="467a8-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-490">String</span><span class="sxs-lookup"><span data-stu-id="467a8-490">String</span></span>|  
|<span data-ttu-id="467a8-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-491">TABLE_NAME</span></span>|<span data-ttu-id="467a8-492">String</span><span class="sxs-lookup"><span data-stu-id="467a8-492">String</span></span>|  
|<span data-ttu-id="467a8-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-493">INDEX_CATALOG</span></span>|<span data-ttu-id="467a8-494">String</span><span class="sxs-lookup"><span data-stu-id="467a8-494">String</span></span>|  
|<span data-ttu-id="467a8-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="467a8-496">String</span><span class="sxs-lookup"><span data-stu-id="467a8-496">String</span></span>|  
|<span data-ttu-id="467a8-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-497">INDEX_NAME</span></span>|<span data-ttu-id="467a8-498">String</span><span class="sxs-lookup"><span data-stu-id="467a8-498">String</span></span>|  
|<span data-ttu-id="467a8-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="467a8-499">PRIMARY_KEY</span></span>|<span data-ttu-id="467a8-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-500">Boolean</span></span>|  
|<span data-ttu-id="467a8-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="467a8-501">UNIQUE</span></span>|<span data-ttu-id="467a8-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-502">Boolean</span></span>|  
|<span data-ttu-id="467a8-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="467a8-503">CLUSTERED</span></span>|<span data-ttu-id="467a8-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-504">Boolean</span></span>|  
|<span data-ttu-id="467a8-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-505">TYPE</span></span>|<span data-ttu-id="467a8-506">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-506">Int32</span></span>|  
|<span data-ttu-id="467a8-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="467a8-507">FILL_FACTOR</span></span>|<span data-ttu-id="467a8-508">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-508">Int32</span></span>|  
|<span data-ttu-id="467a8-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="467a8-509">INITIAL_SIZE</span></span>|<span data-ttu-id="467a8-510">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-510">Int32</span></span>|  
|<span data-ttu-id="467a8-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="467a8-511">NULLS</span></span>|<span data-ttu-id="467a8-512">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-512">Int32</span></span>|  
|<span data-ttu-id="467a8-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="467a8-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="467a8-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-514">Boolean</span></span>|  
|<span data-ttu-id="467a8-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="467a8-515">AUTO_UPDATE</span></span>|<span data-ttu-id="467a8-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-516">Boolean</span></span>|  
|<span data-ttu-id="467a8-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="467a8-517">NULL_COLLATION</span></span>|<span data-ttu-id="467a8-518">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-518">Int32</span></span>|  
|<span data-ttu-id="467a8-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-520">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-520">Int64</span></span>|  
|<span data-ttu-id="467a8-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-521">COLUMN_NAME</span></span>|<span data-ttu-id="467a8-522">String</span><span class="sxs-lookup"><span data-stu-id="467a8-522">String</span></span>|  
|<span data-ttu-id="467a8-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-523">COLUMN_GUID</span></span>|<span data-ttu-id="467a8-524">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-524">Guid</span></span>|  
|<span data-ttu-id="467a8-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-525">COLUMN_PROPID</span></span>|<span data-ttu-id="467a8-526">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-526">Int64</span></span>|  
|<span data-ttu-id="467a8-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="467a8-527">COLLATION</span></span>|<span data-ttu-id="467a8-528">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-528">Int16</span></span>|  
|<span data-ttu-id="467a8-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="467a8-529">CARDINALITY</span></span>|<span data-ttu-id="467a8-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="467a8-530">Decimal</span></span>|  
|<span data-ttu-id="467a8-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="467a8-531">PAGES</span></span>|<span data-ttu-id="467a8-532">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-532">Int32</span></span>|  
|<span data-ttu-id="467a8-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="467a8-533">FILTER_CONDITION</span></span>|<span data-ttu-id="467a8-534">String</span><span class="sxs-lookup"><span data-stu-id="467a8-534">String</span></span>|  
|<span data-ttu-id="467a8-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="467a8-535">INTEGRATED</span></span>|<span data-ttu-id="467a8-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="467a8-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="467a8-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="467a8-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="467a8-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="467a8-539">表</span><span class="sxs-lookup"><span data-stu-id="467a8-539">Tables</span></span>  
  
-   <span data-ttu-id="467a8-540">Columns</span><span class="sxs-lookup"><span data-stu-id="467a8-540">Columns</span></span>  
  
-   <span data-ttu-id="467a8-541">过程</span><span class="sxs-lookup"><span data-stu-id="467a8-541">Procedures</span></span>  
  
-   <span data-ttu-id="467a8-542">视图</span><span class="sxs-lookup"><span data-stu-id="467a8-542">Views</span></span>  
  
-   <span data-ttu-id="467a8-543">索引</span><span class="sxs-lookup"><span data-stu-id="467a8-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="467a8-544">表</span><span class="sxs-lookup"><span data-stu-id="467a8-544">Tables</span></span>  
  
|<span data-ttu-id="467a8-545">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-545">ColumnName</span></span>|<span data-ttu-id="467a8-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-547">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-548">String</span><span class="sxs-lookup"><span data-stu-id="467a8-548">String</span></span>|  
|<span data-ttu-id="467a8-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-550">String</span><span class="sxs-lookup"><span data-stu-id="467a8-550">String</span></span>|  
|<span data-ttu-id="467a8-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-551">TABLE_NAME</span></span>|<span data-ttu-id="467a8-552">String</span><span class="sxs-lookup"><span data-stu-id="467a8-552">String</span></span>|  
|<span data-ttu-id="467a8-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-553">TABLE_TYPE</span></span>|<span data-ttu-id="467a8-554">String</span><span class="sxs-lookup"><span data-stu-id="467a8-554">String</span></span>|  
|<span data-ttu-id="467a8-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-555">TABLE_GUID</span></span>|<span data-ttu-id="467a8-556">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-556">Guid</span></span>|  
|<span data-ttu-id="467a8-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-557">DESCRIPTION</span></span>|<span data-ttu-id="467a8-558">String</span><span class="sxs-lookup"><span data-stu-id="467a8-558">String</span></span>|  
|<span data-ttu-id="467a8-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-559">TABLE_PROPID</span></span>|<span data-ttu-id="467a8-560">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-560">Int64</span></span>|  
|<span data-ttu-id="467a8-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-561">DATE_CREATED</span></span>|<span data-ttu-id="467a8-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-562">DateTime</span></span>|  
|<span data-ttu-id="467a8-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-563">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="467a8-565">Columns</span><span class="sxs-lookup"><span data-stu-id="467a8-565">Columns</span></span>  
  
|<span data-ttu-id="467a8-566">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-566">ColumnName</span></span>|<span data-ttu-id="467a8-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-568">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-569">String</span><span class="sxs-lookup"><span data-stu-id="467a8-569">String</span></span>|  
|<span data-ttu-id="467a8-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-571">String</span><span class="sxs-lookup"><span data-stu-id="467a8-571">String</span></span>|  
|<span data-ttu-id="467a8-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-572">TABLE_NAME</span></span>|<span data-ttu-id="467a8-573">String</span><span class="sxs-lookup"><span data-stu-id="467a8-573">String</span></span>|  
|<span data-ttu-id="467a8-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-574">COLUMN_NAME</span></span>|<span data-ttu-id="467a8-575">String</span><span class="sxs-lookup"><span data-stu-id="467a8-575">String</span></span>|  
|<span data-ttu-id="467a8-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-576">COLUMN_GUID</span></span>|<span data-ttu-id="467a8-577">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-577">Guid</span></span>|  
|<span data-ttu-id="467a8-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-578">COLUMN_PROPID</span></span>|<span data-ttu-id="467a8-579">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-579">Int64</span></span>|  
|<span data-ttu-id="467a8-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-581">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-581">Int64</span></span>|  
|<span data-ttu-id="467a8-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="467a8-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-583">Boolean</span></span>|  
|<span data-ttu-id="467a8-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="467a8-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="467a8-585">String</span><span class="sxs-lookup"><span data-stu-id="467a8-585">String</span></span>|  
|<span data-ttu-id="467a8-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="467a8-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="467a8-587">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-587">Int64</span></span>|  
|<span data-ttu-id="467a8-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="467a8-588">IS_NULLABLE</span></span>|<span data-ttu-id="467a8-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-589">Boolean</span></span>|  
|<span data-ttu-id="467a8-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-590">DATA_TYPE</span></span>|<span data-ttu-id="467a8-591">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-591">Int32</span></span>|  
|<span data-ttu-id="467a8-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-592">TYPE_GUID</span></span>|<span data-ttu-id="467a8-593">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-593">Guid</span></span>|  
|<span data-ttu-id="467a8-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="467a8-595">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-595">Int64</span></span>|  
|<span data-ttu-id="467a8-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="467a8-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="467a8-597">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-597">Int64</span></span>|  
|<span data-ttu-id="467a8-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="467a8-599">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-599">Int32</span></span>|  
|<span data-ttu-id="467a8-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="467a8-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="467a8-601">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-601">Int16</span></span>|  
|<span data-ttu-id="467a8-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="467a8-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="467a8-603">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-603">Int64</span></span>|  
|<span data-ttu-id="467a8-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="467a8-605">String</span><span class="sxs-lookup"><span data-stu-id="467a8-605">String</span></span>|  
|<span data-ttu-id="467a8-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="467a8-607">String</span><span class="sxs-lookup"><span data-stu-id="467a8-607">String</span></span>|  
|<span data-ttu-id="467a8-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="467a8-609">String</span><span class="sxs-lookup"><span data-stu-id="467a8-609">String</span></span>|  
|<span data-ttu-id="467a8-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="467a8-611">String</span><span class="sxs-lookup"><span data-stu-id="467a8-611">String</span></span>|  
|<span data-ttu-id="467a8-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="467a8-613">String</span><span class="sxs-lookup"><span data-stu-id="467a8-613">String</span></span>|  
|<span data-ttu-id="467a8-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-614">COLLATION_NAME</span></span>|<span data-ttu-id="467a8-615">String</span><span class="sxs-lookup"><span data-stu-id="467a8-615">String</span></span>|  
|<span data-ttu-id="467a8-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="467a8-617">String</span><span class="sxs-lookup"><span data-stu-id="467a8-617">String</span></span>|  
|<span data-ttu-id="467a8-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="467a8-619">String</span><span class="sxs-lookup"><span data-stu-id="467a8-619">String</span></span>|  
|<span data-ttu-id="467a8-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-620">DOMAIN_NAME</span></span>|<span data-ttu-id="467a8-621">String</span><span class="sxs-lookup"><span data-stu-id="467a8-621">String</span></span>|  
|<span data-ttu-id="467a8-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-622">DESCRIPTION</span></span>|<span data-ttu-id="467a8-623">String</span><span class="sxs-lookup"><span data-stu-id="467a8-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="467a8-624">过程</span><span class="sxs-lookup"><span data-stu-id="467a8-624">Procedures</span></span>  
  
|<span data-ttu-id="467a8-625">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-625">ColumnName</span></span>|<span data-ttu-id="467a8-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="467a8-628">String</span><span class="sxs-lookup"><span data-stu-id="467a8-628">String</span></span>|  
|<span data-ttu-id="467a8-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="467a8-630">String</span><span class="sxs-lookup"><span data-stu-id="467a8-630">String</span></span>|  
|<span data-ttu-id="467a8-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="467a8-632">String</span><span class="sxs-lookup"><span data-stu-id="467a8-632">String</span></span>|  
|<span data-ttu-id="467a8-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="467a8-634">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-634">Int16</span></span>|  
|<span data-ttu-id="467a8-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="467a8-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="467a8-636">String</span><span class="sxs-lookup"><span data-stu-id="467a8-636">String</span></span>|  
|<span data-ttu-id="467a8-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-637">DESCRIPTION</span></span>|<span data-ttu-id="467a8-638">String</span><span class="sxs-lookup"><span data-stu-id="467a8-638">String</span></span>|  
|<span data-ttu-id="467a8-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-639">DATE_CREATED</span></span>|<span data-ttu-id="467a8-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-640">DateTime</span></span>|  
|<span data-ttu-id="467a8-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-641">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="467a8-643">视图</span><span class="sxs-lookup"><span data-stu-id="467a8-643">Views</span></span>  
  
|<span data-ttu-id="467a8-644">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-644">ColumnName</span></span>|<span data-ttu-id="467a8-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-646">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-647">String</span><span class="sxs-lookup"><span data-stu-id="467a8-647">String</span></span>|  
|<span data-ttu-id="467a8-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-649">String</span><span class="sxs-lookup"><span data-stu-id="467a8-649">String</span></span>|  
|<span data-ttu-id="467a8-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-650">TABLE_NAME</span></span>|<span data-ttu-id="467a8-651">String</span><span class="sxs-lookup"><span data-stu-id="467a8-651">String</span></span>|  
|<span data-ttu-id="467a8-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="467a8-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="467a8-653">String</span><span class="sxs-lookup"><span data-stu-id="467a8-653">String</span></span>|  
|<span data-ttu-id="467a8-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-654">CHECK_OPTION</span></span>|<span data-ttu-id="467a8-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-655">Boolean</span></span>|  
|<span data-ttu-id="467a8-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="467a8-656">IS_UPDATABLE</span></span>|<span data-ttu-id="467a8-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-657">Boolean</span></span>|  
|<span data-ttu-id="467a8-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="467a8-658">DESCRIPTION</span></span>|<span data-ttu-id="467a8-659">String</span><span class="sxs-lookup"><span data-stu-id="467a8-659">String</span></span>|  
|<span data-ttu-id="467a8-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="467a8-660">DATE_CREATED</span></span>|<span data-ttu-id="467a8-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-661">DateTime</span></span>|  
|<span data-ttu-id="467a8-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="467a8-662">DATE_MODIFIED</span></span>|<span data-ttu-id="467a8-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="467a8-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="467a8-664">索引</span><span class="sxs-lookup"><span data-stu-id="467a8-664">Indexes</span></span>  
  
|<span data-ttu-id="467a8-665">列名</span><span class="sxs-lookup"><span data-stu-id="467a8-665">ColumnName</span></span>|<span data-ttu-id="467a8-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="467a8-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="467a8-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-667">TABLE_CATALOG</span></span>|<span data-ttu-id="467a8-668">String</span><span class="sxs-lookup"><span data-stu-id="467a8-668">String</span></span>|  
|<span data-ttu-id="467a8-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="467a8-670">String</span><span class="sxs-lookup"><span data-stu-id="467a8-670">String</span></span>|  
|<span data-ttu-id="467a8-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-671">TABLE_NAME</span></span>|<span data-ttu-id="467a8-672">String</span><span class="sxs-lookup"><span data-stu-id="467a8-672">String</span></span>|  
|<span data-ttu-id="467a8-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="467a8-673">INDEX_CATALOG</span></span>|<span data-ttu-id="467a8-674">String</span><span class="sxs-lookup"><span data-stu-id="467a8-674">String</span></span>|  
|<span data-ttu-id="467a8-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="467a8-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="467a8-676">String</span><span class="sxs-lookup"><span data-stu-id="467a8-676">String</span></span>|  
|<span data-ttu-id="467a8-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-677">INDEX_NAME</span></span>|<span data-ttu-id="467a8-678">String</span><span class="sxs-lookup"><span data-stu-id="467a8-678">String</span></span>|  
|<span data-ttu-id="467a8-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="467a8-679">PRIMARY_KEY</span></span>|<span data-ttu-id="467a8-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-680">Boolean</span></span>|  
|<span data-ttu-id="467a8-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="467a8-681">UNIQUE</span></span>|<span data-ttu-id="467a8-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-682">Boolean</span></span>|  
|<span data-ttu-id="467a8-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="467a8-683">CLUSTERED</span></span>|<span data-ttu-id="467a8-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-684">Boolean</span></span>|  
|<span data-ttu-id="467a8-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="467a8-685">TYPE</span></span>|<span data-ttu-id="467a8-686">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-686">Int32</span></span>|  
|<span data-ttu-id="467a8-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="467a8-687">FILL_FACTOR</span></span>|<span data-ttu-id="467a8-688">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-688">Int32</span></span>|  
|<span data-ttu-id="467a8-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="467a8-689">INITIAL_SIZE</span></span>|<span data-ttu-id="467a8-690">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-690">Int32</span></span>|  
|<span data-ttu-id="467a8-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="467a8-691">NULLS</span></span>|<span data-ttu-id="467a8-692">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-692">Int32</span></span>|  
|<span data-ttu-id="467a8-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="467a8-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="467a8-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-694">Boolean</span></span>|  
|<span data-ttu-id="467a8-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="467a8-695">AUTO_UPDATE</span></span>|<span data-ttu-id="467a8-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-696">Boolean</span></span>|  
|<span data-ttu-id="467a8-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="467a8-697">NULL_COLLATION</span></span>|<span data-ttu-id="467a8-698">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-698">Int32</span></span>|  
|<span data-ttu-id="467a8-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="467a8-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="467a8-700">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-700">Int64</span></span>|  
|<span data-ttu-id="467a8-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="467a8-701">COLUMN_NAME</span></span>|<span data-ttu-id="467a8-702">String</span><span class="sxs-lookup"><span data-stu-id="467a8-702">String</span></span>|  
|<span data-ttu-id="467a8-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="467a8-703">COLUMN_GUID</span></span>|<span data-ttu-id="467a8-704">Guid</span><span class="sxs-lookup"><span data-stu-id="467a8-704">Guid</span></span>|  
|<span data-ttu-id="467a8-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="467a8-705">COLUMN_PROPID</span></span>|<span data-ttu-id="467a8-706">Int64</span><span class="sxs-lookup"><span data-stu-id="467a8-706">Int64</span></span>|  
|<span data-ttu-id="467a8-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="467a8-707">COLLATION</span></span>|<span data-ttu-id="467a8-708">Int16</span><span class="sxs-lookup"><span data-stu-id="467a8-708">Int16</span></span>|  
|<span data-ttu-id="467a8-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="467a8-709">CARDINALITY</span></span>|<span data-ttu-id="467a8-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="467a8-710">Decimal</span></span>|  
|<span data-ttu-id="467a8-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="467a8-711">PAGES</span></span>|<span data-ttu-id="467a8-712">Int32</span><span class="sxs-lookup"><span data-stu-id="467a8-712">Int32</span></span>|  
|<span data-ttu-id="467a8-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="467a8-713">FILTER_CONDITION</span></span>|<span data-ttu-id="467a8-714">String</span><span class="sxs-lookup"><span data-stu-id="467a8-714">String</span></span>|  
|<span data-ttu-id="467a8-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="467a8-715">INTEGRATED</span></span>|<span data-ttu-id="467a8-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="467a8-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="467a8-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="467a8-717">See Also</span></span>  
 [<span data-ttu-id="467a8-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="467a8-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
