---
title: "ODBC 架构集合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 45cfed80decc2336c5a2bacf24fd075c2b81c531
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="e4722-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="e4722-102">ODBC Schema Collections</span></span>
<span data-ttu-id="e4722-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="e4722-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="e4722-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="e4722-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="e4722-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="e4722-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e4722-106">表</span><span class="sxs-lookup"><span data-stu-id="e4722-106">Tables</span></span>  
  
-   <span data-ttu-id="e4722-107">索引</span><span class="sxs-lookup"><span data-stu-id="e4722-107">Indexes</span></span>  
  
-   <span data-ttu-id="e4722-108">Columns</span><span class="sxs-lookup"><span data-stu-id="e4722-108">Columns</span></span>  
  
-   <span data-ttu-id="e4722-109">过程</span><span class="sxs-lookup"><span data-stu-id="e4722-109">Procedures</span></span>  
  
-   <span data-ttu-id="e4722-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e4722-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e4722-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e4722-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e4722-112">视图</span><span class="sxs-lookup"><span data-stu-id="e4722-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e4722-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="e4722-113">Tables and Views</span></span>  
  
|<span data-ttu-id="e4722-114">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-114">ColumnName</span></span>|<span data-ttu-id="e4722-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e4722-116">TABLE_CAT</span></span>|<span data-ttu-id="e4722-117">String</span><span class="sxs-lookup"><span data-stu-id="e4722-117">String</span></span>|  
|<span data-ttu-id="e4722-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e4722-118">TABLE_SCHEM</span></span>|<span data-ttu-id="e4722-119">String</span><span class="sxs-lookup"><span data-stu-id="e4722-119">String</span></span>|  
|<span data-ttu-id="e4722-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-120">TABLE_NAME</span></span>|<span data-ttu-id="e4722-121">String</span><span class="sxs-lookup"><span data-stu-id="e4722-121">String</span></span>|  
|<span data-ttu-id="e4722-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-122">TABLE_TYPE</span></span>|<span data-ttu-id="e4722-123">String</span><span class="sxs-lookup"><span data-stu-id="e4722-123">String</span></span>|  
|<span data-ttu-id="e4722-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-124">REMARKS</span></span>|<span data-ttu-id="e4722-125">String</span><span class="sxs-lookup"><span data-stu-id="e4722-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e4722-126">索引</span><span class="sxs-lookup"><span data-stu-id="e4722-126">Indexes</span></span>  
  
|<span data-ttu-id="e4722-127">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-127">ColumnName</span></span>|<span data-ttu-id="e4722-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e4722-129">TABLE_CAT</span></span>|<span data-ttu-id="e4722-130">String</span><span class="sxs-lookup"><span data-stu-id="e4722-130">String</span></span>|  
|<span data-ttu-id="e4722-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e4722-131">TABLE_SCHEM</span></span>|<span data-ttu-id="e4722-132">String</span><span class="sxs-lookup"><span data-stu-id="e4722-132">String</span></span>|  
|<span data-ttu-id="e4722-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-133">TABLE_NAME</span></span>|<span data-ttu-id="e4722-134">String</span><span class="sxs-lookup"><span data-stu-id="e4722-134">String</span></span>|  
|<span data-ttu-id="e4722-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e4722-135">NON_UNIQUE</span></span>|<span data-ttu-id="e4722-136">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-136">Int16</span></span>|  
|<span data-ttu-id="e4722-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="e4722-138">String</span><span class="sxs-lookup"><span data-stu-id="e4722-138">String</span></span>|  
|<span data-ttu-id="e4722-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-139">INDEX_NAME</span></span>|<span data-ttu-id="e4722-140">String</span><span class="sxs-lookup"><span data-stu-id="e4722-140">String</span></span>|  
|<span data-ttu-id="e4722-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-141">TYPE</span></span>|<span data-ttu-id="e4722-142">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-142">Int16</span></span>|  
|<span data-ttu-id="e4722-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-144">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-144">Int16</span></span>|  
|<span data-ttu-id="e4722-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-145">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-146">String</span><span class="sxs-lookup"><span data-stu-id="e4722-146">String</span></span>|  
|<span data-ttu-id="e4722-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="e4722-147">ASC_OR_DESC</span></span>|<span data-ttu-id="e4722-148">String</span><span class="sxs-lookup"><span data-stu-id="e4722-148">String</span></span>|  
|<span data-ttu-id="e4722-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="e4722-149">CARDINATLITY</span></span>|<span data-ttu-id="e4722-150">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-150">Int32</span></span>|  
|<span data-ttu-id="e4722-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="e4722-151">PAGES</span></span>|<span data-ttu-id="e4722-152">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-152">Int32</span></span>|  
|<span data-ttu-id="e4722-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e4722-153">FILTER_CONDITION</span></span>|<span data-ttu-id="e4722-154">String</span><span class="sxs-lookup"><span data-stu-id="e4722-154">String</span></span>|  
|<span data-ttu-id="e4722-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e4722-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e4722-156">String</span><span class="sxs-lookup"><span data-stu-id="e4722-156">String</span></span>|  
|<span data-ttu-id="e4722-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="e4722-158">Byte</span><span class="sxs-lookup"><span data-stu-id="e4722-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e4722-159">Columns</span><span class="sxs-lookup"><span data-stu-id="e4722-159">Columns</span></span>  
  
|<span data-ttu-id="e4722-160">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-160">ColumnName</span></span>|<span data-ttu-id="e4722-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e4722-162">TABLE_CAT</span></span>|<span data-ttu-id="e4722-163">String</span><span class="sxs-lookup"><span data-stu-id="e4722-163">String</span></span>|  
|<span data-ttu-id="e4722-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e4722-164">TABLE_SCHEM</span></span>|<span data-ttu-id="e4722-165">String</span><span class="sxs-lookup"><span data-stu-id="e4722-165">String</span></span>|  
|<span data-ttu-id="e4722-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-166">TABLE_NAME</span></span>|<span data-ttu-id="e4722-167">String</span><span class="sxs-lookup"><span data-stu-id="e4722-167">String</span></span>|  
|<span data-ttu-id="e4722-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-168">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-169">String</span><span class="sxs-lookup"><span data-stu-id="e4722-169">String</span></span>|  
|<span data-ttu-id="e4722-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-170">DATA_TYPE</span></span>|<span data-ttu-id="e4722-171">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-171">Int16</span></span>|  
|<span data-ttu-id="e4722-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-172">TYPE_NAME</span></span>|<span data-ttu-id="e4722-173">String</span><span class="sxs-lookup"><span data-stu-id="e4722-173">String</span></span>|  
|<span data-ttu-id="e4722-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e4722-174">COLUMN_SIZE</span></span>|<span data-ttu-id="e4722-175">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-175">Int32</span></span>|  
|<span data-ttu-id="e4722-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="e4722-177">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-177">Int32</span></span>|  
|<span data-ttu-id="e4722-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e4722-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e4722-179">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-179">Int16</span></span>|  
|<span data-ttu-id="e4722-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e4722-181">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-181">Int16</span></span>|  
|<span data-ttu-id="e4722-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-182">NULLABLE</span></span>|<span data-ttu-id="e4722-183">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-183">Int16</span></span>|  
|<span data-ttu-id="e4722-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-184">REMARKS</span></span>|<span data-ttu-id="e4722-185">String</span><span class="sxs-lookup"><span data-stu-id="e4722-185">String</span></span>|  
|<span data-ttu-id="e4722-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e4722-186">COLUMN_DEF</span></span>|<span data-ttu-id="e4722-187">String</span><span class="sxs-lookup"><span data-stu-id="e4722-187">String</span></span>|  
|<span data-ttu-id="e4722-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e4722-189">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-189">Int16</span></span>|  
|<span data-ttu-id="e4722-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e4722-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e4722-191">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-191">Int16</span></span>|  
|<span data-ttu-id="e4722-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e4722-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-193">Int32</span></span>|  
|<span data-ttu-id="e4722-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-195">Int32</span></span>|  
|<span data-ttu-id="e4722-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-196">IS_NULLABLE</span></span>|<span data-ttu-id="e4722-197">String</span><span class="sxs-lookup"><span data-stu-id="e4722-197">String</span></span>|  
|<span data-ttu-id="e4722-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e4722-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e4722-199">String</span><span class="sxs-lookup"><span data-stu-id="e4722-199">String</span></span>|  
|<span data-ttu-id="e4722-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e4722-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e4722-201">String</span><span class="sxs-lookup"><span data-stu-id="e4722-201">String</span></span>|  
|<span data-ttu-id="e4722-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="e4722-203">Byte</span><span class="sxs-lookup"><span data-stu-id="e4722-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e4722-204">过程</span><span class="sxs-lookup"><span data-stu-id="e4722-204">Procedures</span></span>  
  
|<span data-ttu-id="e4722-205">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-205">ColumnName</span></span>|<span data-ttu-id="e4722-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e4722-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="e4722-208">String</span><span class="sxs-lookup"><span data-stu-id="e4722-208">String</span></span>|  
|<span data-ttu-id="e4722-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e4722-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e4722-210">String</span><span class="sxs-lookup"><span data-stu-id="e4722-210">String</span></span>|  
|<span data-ttu-id="e4722-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-212">String</span><span class="sxs-lookup"><span data-stu-id="e4722-212">String</span></span>|  
|<span data-ttu-id="e4722-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e4722-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e4722-214">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-214">Int32</span></span>|  
|<span data-ttu-id="e4722-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e4722-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e4722-216">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-216">Int32</span></span>|  
|<span data-ttu-id="e4722-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e4722-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e4722-218">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-218">Int32</span></span>|  
|<span data-ttu-id="e4722-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-219">REMARKS</span></span>|<span data-ttu-id="e4722-220">String</span><span class="sxs-lookup"><span data-stu-id="e4722-220">String</span></span>|  
|<span data-ttu-id="e4722-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e4722-222">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e4722-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e4722-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e4722-224">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-224">ColumnName</span></span>|<span data-ttu-id="e4722-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e4722-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="e4722-227">String</span><span class="sxs-lookup"><span data-stu-id="e4722-227">String</span></span>|  
|<span data-ttu-id="e4722-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e4722-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e4722-229">String</span><span class="sxs-lookup"><span data-stu-id="e4722-229">String</span></span>|  
|<span data-ttu-id="e4722-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-231">String</span><span class="sxs-lookup"><span data-stu-id="e4722-231">String</span></span>|  
|<span data-ttu-id="e4722-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-232">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-233">String</span><span class="sxs-lookup"><span data-stu-id="e4722-233">String</span></span>|  
|<span data-ttu-id="e4722-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-234">COLUMN_TYPE</span></span>|<span data-ttu-id="e4722-235">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-235">Int16</span></span>|  
|<span data-ttu-id="e4722-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-236">DATA_TYPE</span></span>|<span data-ttu-id="e4722-237">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-237">Int16</span></span>|  
|<span data-ttu-id="e4722-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-238">TYPE_NAME</span></span>|<span data-ttu-id="e4722-239">String</span><span class="sxs-lookup"><span data-stu-id="e4722-239">String</span></span>|  
|<span data-ttu-id="e4722-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e4722-240">COLUMN_SIZE</span></span>|<span data-ttu-id="e4722-241">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-241">Int32</span></span>|  
|<span data-ttu-id="e4722-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="e4722-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-243">Int32</span></span>|  
|<span data-ttu-id="e4722-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e4722-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e4722-245">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-245">Int16</span></span>|  
|<span data-ttu-id="e4722-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e4722-247">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-247">Int16</span></span>|  
|<span data-ttu-id="e4722-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-248">NULLABLE</span></span>|<span data-ttu-id="e4722-249">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-249">Int16</span></span>|  
|<span data-ttu-id="e4722-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-250">REMARKS</span></span>|<span data-ttu-id="e4722-251">String</span><span class="sxs-lookup"><span data-stu-id="e4722-251">String</span></span>|  
|<span data-ttu-id="e4722-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e4722-252">COLUMN_DEF</span></span>|<span data-ttu-id="e4722-253">String</span><span class="sxs-lookup"><span data-stu-id="e4722-253">String</span></span>|  
|<span data-ttu-id="e4722-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e4722-255">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-255">Int16</span></span>|  
|<span data-ttu-id="e4722-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e4722-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e4722-257">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-257">Int16</span></span>|  
|<span data-ttu-id="e4722-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e4722-259">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-259">Int32</span></span>|  
|<span data-ttu-id="e4722-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-261">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-261">Int32</span></span>|  
|<span data-ttu-id="e4722-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-262">IS_NULLABLE</span></span>|<span data-ttu-id="e4722-263">String</span><span class="sxs-lookup"><span data-stu-id="e4722-263">String</span></span>|  
|<span data-ttu-id="e4722-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e4722-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e4722-265">String</span><span class="sxs-lookup"><span data-stu-id="e4722-265">String</span></span>|  
|<span data-ttu-id="e4722-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e4722-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e4722-267">String</span><span class="sxs-lookup"><span data-stu-id="e4722-267">String</span></span>|  
|<span data-ttu-id="e4722-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="e4722-269">Byte</span><span class="sxs-lookup"><span data-stu-id="e4722-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e4722-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e4722-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e4722-271">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-271">ColumnName</span></span>|<span data-ttu-id="e4722-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e4722-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="e4722-274">String</span><span class="sxs-lookup"><span data-stu-id="e4722-274">String</span></span>|  
|<span data-ttu-id="e4722-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e4722-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e4722-276">String</span><span class="sxs-lookup"><span data-stu-id="e4722-276">String</span></span>|  
|<span data-ttu-id="e4722-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-278">String</span><span class="sxs-lookup"><span data-stu-id="e4722-278">String</span></span>|  
|<span data-ttu-id="e4722-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-279">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-280">String</span><span class="sxs-lookup"><span data-stu-id="e4722-280">String</span></span>|  
|<span data-ttu-id="e4722-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-281">COLUMN_TYPE</span></span>|<span data-ttu-id="e4722-282">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-282">Int16</span></span>|  
|<span data-ttu-id="e4722-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-283">DATA_TYPE</span></span>|<span data-ttu-id="e4722-284">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-284">Int16</span></span>|  
|<span data-ttu-id="e4722-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-285">TYPE_NAME</span></span>|<span data-ttu-id="e4722-286">String</span><span class="sxs-lookup"><span data-stu-id="e4722-286">String</span></span>|  
|<span data-ttu-id="e4722-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e4722-287">COLUMN_SIZE</span></span>|<span data-ttu-id="e4722-288">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-288">Int32</span></span>|  
|<span data-ttu-id="e4722-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="e4722-290">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-290">Int32</span></span>|  
|<span data-ttu-id="e4722-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e4722-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e4722-292">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-292">Int16</span></span>|  
|<span data-ttu-id="e4722-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e4722-294">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-294">Int16</span></span>|  
|<span data-ttu-id="e4722-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-295">NULLABLE</span></span>|<span data-ttu-id="e4722-296">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-296">Int16</span></span>|  
|<span data-ttu-id="e4722-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-297">REMARKS</span></span>|<span data-ttu-id="e4722-298">String</span><span class="sxs-lookup"><span data-stu-id="e4722-298">String</span></span>|  
|<span data-ttu-id="e4722-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e4722-299">COLUMN_DEF</span></span>|<span data-ttu-id="e4722-300">String</span><span class="sxs-lookup"><span data-stu-id="e4722-300">String</span></span>|  
|<span data-ttu-id="e4722-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e4722-302">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-302">Int16</span></span>|  
|<span data-ttu-id="e4722-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e4722-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e4722-304">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-304">Int16</span></span>|  
|<span data-ttu-id="e4722-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e4722-306">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-306">Int32</span></span>|  
|<span data-ttu-id="e4722-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-308">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-308">Int32</span></span>|  
|<span data-ttu-id="e4722-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-309">IS_NULLABLE</span></span>|<span data-ttu-id="e4722-310">String</span><span class="sxs-lookup"><span data-stu-id="e4722-310">String</span></span>|  
|<span data-ttu-id="e4722-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e4722-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e4722-312">String</span><span class="sxs-lookup"><span data-stu-id="e4722-312">String</span></span>|  
|<span data-ttu-id="e4722-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e4722-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e4722-314">String</span><span class="sxs-lookup"><span data-stu-id="e4722-314">String</span></span>|  
|<span data-ttu-id="e4722-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="e4722-316">Byte</span><span class="sxs-lookup"><span data-stu-id="e4722-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="e4722-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="e4722-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="e4722-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="e4722-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e4722-319">表</span><span class="sxs-lookup"><span data-stu-id="e4722-319">Tables</span></span>  
  
-   <span data-ttu-id="e4722-320">Columns</span><span class="sxs-lookup"><span data-stu-id="e4722-320">Columns</span></span>  
  
-   <span data-ttu-id="e4722-321">过程</span><span class="sxs-lookup"><span data-stu-id="e4722-321">Procedures</span></span>  
  
-   <span data-ttu-id="e4722-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e4722-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e4722-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e4722-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e4722-324">视图</span><span class="sxs-lookup"><span data-stu-id="e4722-324">Views</span></span>  
  
-   <span data-ttu-id="e4722-325">索引</span><span class="sxs-lookup"><span data-stu-id="e4722-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e4722-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="e4722-326">Tables and Views</span></span>  
  
|<span data-ttu-id="e4722-327">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-327">ColumnName</span></span>|<span data-ttu-id="e4722-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e4722-330">String</span><span class="sxs-lookup"><span data-stu-id="e4722-330">String</span></span>|  
|<span data-ttu-id="e4722-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-331">TABLE_OWNER</span></span>|<span data-ttu-id="e4722-332">String</span><span class="sxs-lookup"><span data-stu-id="e4722-332">String</span></span>|  
|<span data-ttu-id="e4722-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-333">TABLE_NAME</span></span>|<span data-ttu-id="e4722-334">String</span><span class="sxs-lookup"><span data-stu-id="e4722-334">String</span></span>|  
|<span data-ttu-id="e4722-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-335">TABLE_TYPE</span></span>|<span data-ttu-id="e4722-336">String</span><span class="sxs-lookup"><span data-stu-id="e4722-336">String</span></span>|  
|<span data-ttu-id="e4722-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-337">REMARKS</span></span>|<span data-ttu-id="e4722-338">String</span><span class="sxs-lookup"><span data-stu-id="e4722-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e4722-339">Columns</span><span class="sxs-lookup"><span data-stu-id="e4722-339">Columns</span></span>  
  
|<span data-ttu-id="e4722-340">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-340">ColumnName</span></span>|<span data-ttu-id="e4722-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e4722-343">String</span><span class="sxs-lookup"><span data-stu-id="e4722-343">String</span></span>|  
|<span data-ttu-id="e4722-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-344">TABLE_OWNER</span></span>|<span data-ttu-id="e4722-345">String</span><span class="sxs-lookup"><span data-stu-id="e4722-345">String</span></span>|  
|<span data-ttu-id="e4722-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-346">TABLE_NAME</span></span>|<span data-ttu-id="e4722-347">String</span><span class="sxs-lookup"><span data-stu-id="e4722-347">String</span></span>|  
|<span data-ttu-id="e4722-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-348">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-349">String</span><span class="sxs-lookup"><span data-stu-id="e4722-349">String</span></span>|  
|<span data-ttu-id="e4722-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-350">DATA_TYPE</span></span>|<span data-ttu-id="e4722-351">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-351">Int16</span></span>|  
|<span data-ttu-id="e4722-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-352">TYPE_NAME</span></span>|<span data-ttu-id="e4722-353">String</span><span class="sxs-lookup"><span data-stu-id="e4722-353">String</span></span>|  
|<span data-ttu-id="e4722-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e4722-354">PRECISION</span></span>|<span data-ttu-id="e4722-355">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-355">Int32</span></span>|  
|<span data-ttu-id="e4722-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-356">LENGTH</span></span>|<span data-ttu-id="e4722-357">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-357">Int32</span></span>|  
|<span data-ttu-id="e4722-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="e4722-358">SCALE</span></span>|<span data-ttu-id="e4722-359">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-359">Int16</span></span>|  
|<span data-ttu-id="e4722-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-360">RADIX</span></span>|<span data-ttu-id="e4722-361">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-361">Int16</span></span>|  
|<span data-ttu-id="e4722-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-362">NULLABLE</span></span>|<span data-ttu-id="e4722-363">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-363">Int16</span></span>|  
|<span data-ttu-id="e4722-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-364">REMARKS</span></span>|<span data-ttu-id="e4722-365">String</span><span class="sxs-lookup"><span data-stu-id="e4722-365">String</span></span>|  
|<span data-ttu-id="e4722-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-367">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e4722-368">过程</span><span class="sxs-lookup"><span data-stu-id="e4722-368">Procedures</span></span>  
  
|<span data-ttu-id="e4722-369">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-369">ColumnName</span></span>|<span data-ttu-id="e4722-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e4722-372">String</span><span class="sxs-lookup"><span data-stu-id="e4722-372">String</span></span>|  
|<span data-ttu-id="e4722-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e4722-374">String</span><span class="sxs-lookup"><span data-stu-id="e4722-374">String</span></span>|  
|<span data-ttu-id="e4722-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-376">String</span><span class="sxs-lookup"><span data-stu-id="e4722-376">String</span></span>|  
|<span data-ttu-id="e4722-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e4722-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e4722-378">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-378">Int16</span></span>|  
|<span data-ttu-id="e4722-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e4722-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e4722-380">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-380">Int16</span></span>|  
|<span data-ttu-id="e4722-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e4722-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e4722-382">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-382">Int16</span></span>|  
|<span data-ttu-id="e4722-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-383">REMARKS</span></span>|<span data-ttu-id="e4722-384">String</span><span class="sxs-lookup"><span data-stu-id="e4722-384">String</span></span>|  
|<span data-ttu-id="e4722-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e4722-386">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e4722-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e4722-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e4722-388">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-388">ColumnName</span></span>|<span data-ttu-id="e4722-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e4722-391">String</span><span class="sxs-lookup"><span data-stu-id="e4722-391">String</span></span>|  
|<span data-ttu-id="e4722-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e4722-393">String</span><span class="sxs-lookup"><span data-stu-id="e4722-393">String</span></span>|  
|<span data-ttu-id="e4722-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-395">String</span><span class="sxs-lookup"><span data-stu-id="e4722-395">String</span></span>|  
|<span data-ttu-id="e4722-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-396">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-397">String</span><span class="sxs-lookup"><span data-stu-id="e4722-397">String</span></span>|  
|<span data-ttu-id="e4722-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-398">COLUMN_TYPE</span></span>|<span data-ttu-id="e4722-399">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-399">Int16</span></span>|  
|<span data-ttu-id="e4722-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-400">DATA_TYPE</span></span>|<span data-ttu-id="e4722-401">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-401">Int16</span></span>|  
|<span data-ttu-id="e4722-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-402">TYPE_NAME</span></span>|<span data-ttu-id="e4722-403">String</span><span class="sxs-lookup"><span data-stu-id="e4722-403">String</span></span>|  
|<span data-ttu-id="e4722-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e4722-404">PRECISION</span></span>|<span data-ttu-id="e4722-405">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-405">Int32</span></span>|  
|<span data-ttu-id="e4722-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-406">LENGTH</span></span>|<span data-ttu-id="e4722-407">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-407">Int32</span></span>|  
|<span data-ttu-id="e4722-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="e4722-408">SCALE</span></span>|<span data-ttu-id="e4722-409">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-409">Int16</span></span>|  
|<span data-ttu-id="e4722-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-410">RADIX</span></span>|<span data-ttu-id="e4722-411">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-411">Int16</span></span>|  
|<span data-ttu-id="e4722-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-412">NULLABLE</span></span>|<span data-ttu-id="e4722-413">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-413">Int16</span></span>|  
|<span data-ttu-id="e4722-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-414">REMARKS</span></span>|<span data-ttu-id="e4722-415">String</span><span class="sxs-lookup"><span data-stu-id="e4722-415">String</span></span>|  
|<span data-ttu-id="e4722-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e4722-416">OVERLOAD</span></span>|<span data-ttu-id="e4722-417">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-417">Int32</span></span>|  
|<span data-ttu-id="e4722-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-419">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="e4722-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="e4722-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="e4722-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="e4722-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e4722-422">表</span><span class="sxs-lookup"><span data-stu-id="e4722-422">Tables</span></span>  
  
-   <span data-ttu-id="e4722-423">索引</span><span class="sxs-lookup"><span data-stu-id="e4722-423">Indexes</span></span>  
  
-   <span data-ttu-id="e4722-424">Columns</span><span class="sxs-lookup"><span data-stu-id="e4722-424">Columns</span></span>  
  
-   <span data-ttu-id="e4722-425">过程</span><span class="sxs-lookup"><span data-stu-id="e4722-425">Procedures</span></span>  
  
-   <span data-ttu-id="e4722-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e4722-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e4722-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e4722-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e4722-428">视图</span><span class="sxs-lookup"><span data-stu-id="e4722-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e4722-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="e4722-429">Tables and Views</span></span>  
  
|<span data-ttu-id="e4722-430">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-430">ColumnName</span></span>|<span data-ttu-id="e4722-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e4722-433">String</span><span class="sxs-lookup"><span data-stu-id="e4722-433">String</span></span>|  
|<span data-ttu-id="e4722-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-434">TABLE_OWNER</span></span>|<span data-ttu-id="e4722-435">String</span><span class="sxs-lookup"><span data-stu-id="e4722-435">String</span></span>|  
|<span data-ttu-id="e4722-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-436">TABLE_NAME</span></span>|<span data-ttu-id="e4722-437">String</span><span class="sxs-lookup"><span data-stu-id="e4722-437">String</span></span>|  
|<span data-ttu-id="e4722-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-438">TABLE_TYPE</span></span>|<span data-ttu-id="e4722-439">String</span><span class="sxs-lookup"><span data-stu-id="e4722-439">String</span></span>|  
|<span data-ttu-id="e4722-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-440">REMARKS</span></span>|<span data-ttu-id="e4722-441">String</span><span class="sxs-lookup"><span data-stu-id="e4722-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e4722-442">Columns</span><span class="sxs-lookup"><span data-stu-id="e4722-442">Columns</span></span>  
  
|<span data-ttu-id="e4722-443">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-443">ColumnName</span></span>|<span data-ttu-id="e4722-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e4722-446">String</span><span class="sxs-lookup"><span data-stu-id="e4722-446">String</span></span>|  
|<span data-ttu-id="e4722-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-447">TABLE_OWNER</span></span>|<span data-ttu-id="e4722-448">String</span><span class="sxs-lookup"><span data-stu-id="e4722-448">String</span></span>|  
|<span data-ttu-id="e4722-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-449">TABLE_NAME</span></span>|<span data-ttu-id="e4722-450">String</span><span class="sxs-lookup"><span data-stu-id="e4722-450">String</span></span>|  
|<span data-ttu-id="e4722-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-451">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-452">String</span><span class="sxs-lookup"><span data-stu-id="e4722-452">String</span></span>|  
|<span data-ttu-id="e4722-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-453">DATA_TYPE</span></span>|<span data-ttu-id="e4722-454">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-454">Int16</span></span>|  
|<span data-ttu-id="e4722-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-455">TYPE_NAME</span></span>|<span data-ttu-id="e4722-456">String</span><span class="sxs-lookup"><span data-stu-id="e4722-456">String</span></span>|  
|<span data-ttu-id="e4722-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e4722-457">PRECISION</span></span>|<span data-ttu-id="e4722-458">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-458">Int32</span></span>|  
|<span data-ttu-id="e4722-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-459">LENGTH</span></span>|<span data-ttu-id="e4722-460">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-460">Int32</span></span>|  
|<span data-ttu-id="e4722-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="e4722-461">SCALE</span></span>|<span data-ttu-id="e4722-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-462">Int16</span></span>|  
|<span data-ttu-id="e4722-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-463">RADIX</span></span>|<span data-ttu-id="e4722-464">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-464">Int16</span></span>|  
|<span data-ttu-id="e4722-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-465">NULLABLE</span></span>|<span data-ttu-id="e4722-466">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-466">Int16</span></span>|  
|<span data-ttu-id="e4722-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-467">REMARKS</span></span>|<span data-ttu-id="e4722-468">String</span><span class="sxs-lookup"><span data-stu-id="e4722-468">String</span></span>|  
|<span data-ttu-id="e4722-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-470">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e4722-471">过程</span><span class="sxs-lookup"><span data-stu-id="e4722-471">Procedures</span></span>  
  
|<span data-ttu-id="e4722-472">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-472">ColumnName</span></span>|<span data-ttu-id="e4722-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e4722-475">String</span><span class="sxs-lookup"><span data-stu-id="e4722-475">String</span></span>|  
|<span data-ttu-id="e4722-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e4722-477">String</span><span class="sxs-lookup"><span data-stu-id="e4722-477">String</span></span>|  
|<span data-ttu-id="e4722-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-479">String</span><span class="sxs-lookup"><span data-stu-id="e4722-479">String</span></span>|  
|<span data-ttu-id="e4722-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e4722-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e4722-481">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-481">Int16</span></span>|  
|<span data-ttu-id="e4722-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e4722-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e4722-483">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-483">Int16</span></span>|  
|<span data-ttu-id="e4722-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e4722-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e4722-485">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-485">Int16</span></span>|  
|<span data-ttu-id="e4722-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-486">REMARKS</span></span>|<span data-ttu-id="e4722-487">String</span><span class="sxs-lookup"><span data-stu-id="e4722-487">String</span></span>|  
|<span data-ttu-id="e4722-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e4722-489">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e4722-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e4722-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e4722-491">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-491">ColumnName</span></span>|<span data-ttu-id="e4722-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e4722-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e4722-494">String</span><span class="sxs-lookup"><span data-stu-id="e4722-494">String</span></span>|  
|<span data-ttu-id="e4722-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4722-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e4722-496">String</span><span class="sxs-lookup"><span data-stu-id="e4722-496">String</span></span>|  
|<span data-ttu-id="e4722-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-498">String</span><span class="sxs-lookup"><span data-stu-id="e4722-498">String</span></span>|  
|<span data-ttu-id="e4722-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-499">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-500">String</span><span class="sxs-lookup"><span data-stu-id="e4722-500">String</span></span>|  
|<span data-ttu-id="e4722-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-501">COLUMN_TYPE</span></span>|<span data-ttu-id="e4722-502">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-502">Int16</span></span>|  
|<span data-ttu-id="e4722-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-503">DATA_TYPE</span></span>|<span data-ttu-id="e4722-504">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-504">Int16</span></span>|  
|<span data-ttu-id="e4722-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-505">TYPE_NAME</span></span>|<span data-ttu-id="e4722-506">String</span><span class="sxs-lookup"><span data-stu-id="e4722-506">String</span></span>|  
|<span data-ttu-id="e4722-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e4722-507">PRECISION</span></span>|<span data-ttu-id="e4722-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-508">Int32</span></span>|  
|<span data-ttu-id="e4722-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-509">LENGTH</span></span>|<span data-ttu-id="e4722-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-510">Int32</span></span>|  
|<span data-ttu-id="e4722-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="e4722-511">SCALE</span></span>|<span data-ttu-id="e4722-512">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-512">Int16</span></span>|  
|<span data-ttu-id="e4722-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-513">RADIX</span></span>|<span data-ttu-id="e4722-514">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-514">Int16</span></span>|  
|<span data-ttu-id="e4722-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-515">NULLABLE</span></span>|<span data-ttu-id="e4722-516">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-516">Int16</span></span>|  
|<span data-ttu-id="e4722-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-517">REMARKS</span></span>|<span data-ttu-id="e4722-518">String</span><span class="sxs-lookup"><span data-stu-id="e4722-518">String</span></span>|  
|<span data-ttu-id="e4722-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e4722-519">OVERLOAD</span></span>|<span data-ttu-id="e4722-520">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-520">Int32</span></span>|  
|<span data-ttu-id="e4722-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-522">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e4722-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e4722-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e4722-524">列名</span><span class="sxs-lookup"><span data-stu-id="e4722-524">ColumnName</span></span>|<span data-ttu-id="e4722-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4722-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e4722-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e4722-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="e4722-527">String</span><span class="sxs-lookup"><span data-stu-id="e4722-527">String</span></span>|  
|<span data-ttu-id="e4722-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e4722-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e4722-529">String</span><span class="sxs-lookup"><span data-stu-id="e4722-529">String</span></span>|  
|<span data-ttu-id="e4722-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="e4722-531">String</span><span class="sxs-lookup"><span data-stu-id="e4722-531">String</span></span>|  
|<span data-ttu-id="e4722-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-532">COLUMN_NAME</span></span>|<span data-ttu-id="e4722-533">String</span><span class="sxs-lookup"><span data-stu-id="e4722-533">String</span></span>|  
|<span data-ttu-id="e4722-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-534">COLUMN_TYPE</span></span>|<span data-ttu-id="e4722-535">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-535">Int16</span></span>|  
|<span data-ttu-id="e4722-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-536">DATA_TYPE</span></span>|<span data-ttu-id="e4722-537">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-537">Int16</span></span>|  
|<span data-ttu-id="e4722-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e4722-538">TYPE_NAME</span></span>|<span data-ttu-id="e4722-539">String</span><span class="sxs-lookup"><span data-stu-id="e4722-539">String</span></span>|  
|<span data-ttu-id="e4722-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e4722-540">COLUMN_SIZE</span></span>|<span data-ttu-id="e4722-541">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-541">Int32</span></span>|  
|<span data-ttu-id="e4722-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="e4722-543">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-543">Int32</span></span>|  
|<span data-ttu-id="e4722-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e4722-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e4722-545">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-545">Int16</span></span>|  
|<span data-ttu-id="e4722-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e4722-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e4722-547">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-547">Int16</span></span>|  
|<span data-ttu-id="e4722-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-548">NULLABLE</span></span>|<span data-ttu-id="e4722-549">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-549">Int16</span></span>|  
|<span data-ttu-id="e4722-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e4722-550">REMARKS</span></span>|<span data-ttu-id="e4722-551">String</span><span class="sxs-lookup"><span data-stu-id="e4722-551">String</span></span>|  
|<span data-ttu-id="e4722-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e4722-552">COLUMN_DEF</span></span>|<span data-ttu-id="e4722-553">String</span><span class="sxs-lookup"><span data-stu-id="e4722-553">String</span></span>|  
|<span data-ttu-id="e4722-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e4722-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e4722-555">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-555">Int16</span></span>|  
|<span data-ttu-id="e4722-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e4722-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e4722-557">Int16</span><span class="sxs-lookup"><span data-stu-id="e4722-557">Int16</span></span>|  
|<span data-ttu-id="e4722-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e4722-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e4722-559">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-559">Int32</span></span>|  
|<span data-ttu-id="e4722-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e4722-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="e4722-561">Int32</span><span class="sxs-lookup"><span data-stu-id="e4722-561">Int32</span></span>|  
|<span data-ttu-id="e4722-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e4722-562">IS_NULLABLE</span></span>|<span data-ttu-id="e4722-563">String</span><span class="sxs-lookup"><span data-stu-id="e4722-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4722-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4722-564">See Also</span></span>  
 [<span data-ttu-id="e4722-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e4722-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
