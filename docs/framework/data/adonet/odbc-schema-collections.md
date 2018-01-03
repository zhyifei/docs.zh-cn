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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b8c31f4e8b1463c184c9a8ff1cf64808783f030d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="75317-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="75317-102">ODBC Schema Collections</span></span>
<span data-ttu-id="75317-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="75317-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="75317-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="75317-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="75317-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="75317-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="75317-106">表</span><span class="sxs-lookup"><span data-stu-id="75317-106">Tables</span></span>  
  
-   <span data-ttu-id="75317-107">索引</span><span class="sxs-lookup"><span data-stu-id="75317-107">Indexes</span></span>  
  
-   <span data-ttu-id="75317-108">Columns</span><span class="sxs-lookup"><span data-stu-id="75317-108">Columns</span></span>  
  
-   <span data-ttu-id="75317-109">过程</span><span class="sxs-lookup"><span data-stu-id="75317-109">Procedures</span></span>  
  
-   <span data-ttu-id="75317-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="75317-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="75317-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="75317-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="75317-112">视图</span><span class="sxs-lookup"><span data-stu-id="75317-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="75317-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="75317-113">Tables and Views</span></span>  
  
|<span data-ttu-id="75317-114">列名</span><span class="sxs-lookup"><span data-stu-id="75317-114">ColumnName</span></span>|<span data-ttu-id="75317-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="75317-116">TABLE_CAT</span></span>|<span data-ttu-id="75317-117">String</span><span class="sxs-lookup"><span data-stu-id="75317-117">String</span></span>|  
|<span data-ttu-id="75317-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="75317-118">TABLE_SCHEM</span></span>|<span data-ttu-id="75317-119">String</span><span class="sxs-lookup"><span data-stu-id="75317-119">String</span></span>|  
|<span data-ttu-id="75317-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-120">TABLE_NAME</span></span>|<span data-ttu-id="75317-121">String</span><span class="sxs-lookup"><span data-stu-id="75317-121">String</span></span>|  
|<span data-ttu-id="75317-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-122">TABLE_TYPE</span></span>|<span data-ttu-id="75317-123">String</span><span class="sxs-lookup"><span data-stu-id="75317-123">String</span></span>|  
|<span data-ttu-id="75317-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-124">REMARKS</span></span>|<span data-ttu-id="75317-125">String</span><span class="sxs-lookup"><span data-stu-id="75317-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="75317-126">索引</span><span class="sxs-lookup"><span data-stu-id="75317-126">Indexes</span></span>  
  
|<span data-ttu-id="75317-127">列名</span><span class="sxs-lookup"><span data-stu-id="75317-127">ColumnName</span></span>|<span data-ttu-id="75317-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="75317-129">TABLE_CAT</span></span>|<span data-ttu-id="75317-130">String</span><span class="sxs-lookup"><span data-stu-id="75317-130">String</span></span>|  
|<span data-ttu-id="75317-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="75317-131">TABLE_SCHEM</span></span>|<span data-ttu-id="75317-132">String</span><span class="sxs-lookup"><span data-stu-id="75317-132">String</span></span>|  
|<span data-ttu-id="75317-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-133">TABLE_NAME</span></span>|<span data-ttu-id="75317-134">String</span><span class="sxs-lookup"><span data-stu-id="75317-134">String</span></span>|  
|<span data-ttu-id="75317-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="75317-135">NON_UNIQUE</span></span>|<span data-ttu-id="75317-136">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-136">Int16</span></span>|  
|<span data-ttu-id="75317-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="75317-138">String</span><span class="sxs-lookup"><span data-stu-id="75317-138">String</span></span>|  
|<span data-ttu-id="75317-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-139">INDEX_NAME</span></span>|<span data-ttu-id="75317-140">String</span><span class="sxs-lookup"><span data-stu-id="75317-140">String</span></span>|  
|<span data-ttu-id="75317-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-141">TYPE</span></span>|<span data-ttu-id="75317-142">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-142">Int16</span></span>|  
|<span data-ttu-id="75317-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-144">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-144">Int16</span></span>|  
|<span data-ttu-id="75317-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-145">COLUMN_NAME</span></span>|<span data-ttu-id="75317-146">String</span><span class="sxs-lookup"><span data-stu-id="75317-146">String</span></span>|  
|<span data-ttu-id="75317-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="75317-147">ASC_OR_DESC</span></span>|<span data-ttu-id="75317-148">String</span><span class="sxs-lookup"><span data-stu-id="75317-148">String</span></span>|  
|<span data-ttu-id="75317-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="75317-149">CARDINATLITY</span></span>|<span data-ttu-id="75317-150">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-150">Int32</span></span>|  
|<span data-ttu-id="75317-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="75317-151">PAGES</span></span>|<span data-ttu-id="75317-152">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-152">Int32</span></span>|  
|<span data-ttu-id="75317-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="75317-153">FILTER_CONDITION</span></span>|<span data-ttu-id="75317-154">String</span><span class="sxs-lookup"><span data-stu-id="75317-154">String</span></span>|  
|<span data-ttu-id="75317-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="75317-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="75317-156">String</span><span class="sxs-lookup"><span data-stu-id="75317-156">String</span></span>|  
|<span data-ttu-id="75317-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="75317-158">Byte</span><span class="sxs-lookup"><span data-stu-id="75317-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="75317-159">Columns</span><span class="sxs-lookup"><span data-stu-id="75317-159">Columns</span></span>  
  
|<span data-ttu-id="75317-160">列名</span><span class="sxs-lookup"><span data-stu-id="75317-160">ColumnName</span></span>|<span data-ttu-id="75317-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="75317-162">TABLE_CAT</span></span>|<span data-ttu-id="75317-163">String</span><span class="sxs-lookup"><span data-stu-id="75317-163">String</span></span>|  
|<span data-ttu-id="75317-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="75317-164">TABLE_SCHEM</span></span>|<span data-ttu-id="75317-165">String</span><span class="sxs-lookup"><span data-stu-id="75317-165">String</span></span>|  
|<span data-ttu-id="75317-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-166">TABLE_NAME</span></span>|<span data-ttu-id="75317-167">String</span><span class="sxs-lookup"><span data-stu-id="75317-167">String</span></span>|  
|<span data-ttu-id="75317-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-168">COLUMN_NAME</span></span>|<span data-ttu-id="75317-169">String</span><span class="sxs-lookup"><span data-stu-id="75317-169">String</span></span>|  
|<span data-ttu-id="75317-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-170">DATA_TYPE</span></span>|<span data-ttu-id="75317-171">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-171">Int16</span></span>|  
|<span data-ttu-id="75317-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-172">TYPE_NAME</span></span>|<span data-ttu-id="75317-173">String</span><span class="sxs-lookup"><span data-stu-id="75317-173">String</span></span>|  
|<span data-ttu-id="75317-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="75317-174">COLUMN_SIZE</span></span>|<span data-ttu-id="75317-175">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-175">Int32</span></span>|  
|<span data-ttu-id="75317-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="75317-177">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-177">Int32</span></span>|  
|<span data-ttu-id="75317-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="75317-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="75317-179">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-179">Int16</span></span>|  
|<span data-ttu-id="75317-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="75317-181">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-181">Int16</span></span>|  
|<span data-ttu-id="75317-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-182">NULLABLE</span></span>|<span data-ttu-id="75317-183">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-183">Int16</span></span>|  
|<span data-ttu-id="75317-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-184">REMARKS</span></span>|<span data-ttu-id="75317-185">String</span><span class="sxs-lookup"><span data-stu-id="75317-185">String</span></span>|  
|<span data-ttu-id="75317-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="75317-186">COLUMN_DEF</span></span>|<span data-ttu-id="75317-187">String</span><span class="sxs-lookup"><span data-stu-id="75317-187">String</span></span>|  
|<span data-ttu-id="75317-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="75317-189">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-189">Int16</span></span>|  
|<span data-ttu-id="75317-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="75317-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="75317-191">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-191">Int16</span></span>|  
|<span data-ttu-id="75317-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="75317-193">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-193">Int32</span></span>|  
|<span data-ttu-id="75317-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-195">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-195">Int32</span></span>|  
|<span data-ttu-id="75317-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-196">IS_NULLABLE</span></span>|<span data-ttu-id="75317-197">String</span><span class="sxs-lookup"><span data-stu-id="75317-197">String</span></span>|  
|<span data-ttu-id="75317-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="75317-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="75317-199">String</span><span class="sxs-lookup"><span data-stu-id="75317-199">String</span></span>|  
|<span data-ttu-id="75317-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="75317-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="75317-201">String</span><span class="sxs-lookup"><span data-stu-id="75317-201">String</span></span>|  
|<span data-ttu-id="75317-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="75317-203">Byte</span><span class="sxs-lookup"><span data-stu-id="75317-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="75317-204">过程</span><span class="sxs-lookup"><span data-stu-id="75317-204">Procedures</span></span>  
  
|<span data-ttu-id="75317-205">列名</span><span class="sxs-lookup"><span data-stu-id="75317-205">ColumnName</span></span>|<span data-ttu-id="75317-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="75317-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="75317-208">String</span><span class="sxs-lookup"><span data-stu-id="75317-208">String</span></span>|  
|<span data-ttu-id="75317-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="75317-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="75317-210">String</span><span class="sxs-lookup"><span data-stu-id="75317-210">String</span></span>|  
|<span data-ttu-id="75317-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-212">String</span><span class="sxs-lookup"><span data-stu-id="75317-212">String</span></span>|  
|<span data-ttu-id="75317-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="75317-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="75317-214">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-214">Int32</span></span>|  
|<span data-ttu-id="75317-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="75317-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="75317-216">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-216">Int32</span></span>|  
|<span data-ttu-id="75317-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="75317-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="75317-218">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-218">Int32</span></span>|  
|<span data-ttu-id="75317-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-219">REMARKS</span></span>|<span data-ttu-id="75317-220">String</span><span class="sxs-lookup"><span data-stu-id="75317-220">String</span></span>|  
|<span data-ttu-id="75317-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="75317-222">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="75317-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="75317-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="75317-224">列名</span><span class="sxs-lookup"><span data-stu-id="75317-224">ColumnName</span></span>|<span data-ttu-id="75317-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="75317-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="75317-227">String</span><span class="sxs-lookup"><span data-stu-id="75317-227">String</span></span>|  
|<span data-ttu-id="75317-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="75317-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="75317-229">String</span><span class="sxs-lookup"><span data-stu-id="75317-229">String</span></span>|  
|<span data-ttu-id="75317-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-231">String</span><span class="sxs-lookup"><span data-stu-id="75317-231">String</span></span>|  
|<span data-ttu-id="75317-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-232">COLUMN_NAME</span></span>|<span data-ttu-id="75317-233">String</span><span class="sxs-lookup"><span data-stu-id="75317-233">String</span></span>|  
|<span data-ttu-id="75317-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-234">COLUMN_TYPE</span></span>|<span data-ttu-id="75317-235">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-235">Int16</span></span>|  
|<span data-ttu-id="75317-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-236">DATA_TYPE</span></span>|<span data-ttu-id="75317-237">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-237">Int16</span></span>|  
|<span data-ttu-id="75317-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-238">TYPE_NAME</span></span>|<span data-ttu-id="75317-239">String</span><span class="sxs-lookup"><span data-stu-id="75317-239">String</span></span>|  
|<span data-ttu-id="75317-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="75317-240">COLUMN_SIZE</span></span>|<span data-ttu-id="75317-241">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-241">Int32</span></span>|  
|<span data-ttu-id="75317-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="75317-243">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-243">Int32</span></span>|  
|<span data-ttu-id="75317-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="75317-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="75317-245">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-245">Int16</span></span>|  
|<span data-ttu-id="75317-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="75317-247">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-247">Int16</span></span>|  
|<span data-ttu-id="75317-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-248">NULLABLE</span></span>|<span data-ttu-id="75317-249">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-249">Int16</span></span>|  
|<span data-ttu-id="75317-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-250">REMARKS</span></span>|<span data-ttu-id="75317-251">String</span><span class="sxs-lookup"><span data-stu-id="75317-251">String</span></span>|  
|<span data-ttu-id="75317-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="75317-252">COLUMN_DEF</span></span>|<span data-ttu-id="75317-253">String</span><span class="sxs-lookup"><span data-stu-id="75317-253">String</span></span>|  
|<span data-ttu-id="75317-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="75317-255">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-255">Int16</span></span>|  
|<span data-ttu-id="75317-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="75317-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="75317-257">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-257">Int16</span></span>|  
|<span data-ttu-id="75317-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="75317-259">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-259">Int32</span></span>|  
|<span data-ttu-id="75317-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-261">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-261">Int32</span></span>|  
|<span data-ttu-id="75317-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-262">IS_NULLABLE</span></span>|<span data-ttu-id="75317-263">String</span><span class="sxs-lookup"><span data-stu-id="75317-263">String</span></span>|  
|<span data-ttu-id="75317-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="75317-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="75317-265">String</span><span class="sxs-lookup"><span data-stu-id="75317-265">String</span></span>|  
|<span data-ttu-id="75317-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="75317-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="75317-267">String</span><span class="sxs-lookup"><span data-stu-id="75317-267">String</span></span>|  
|<span data-ttu-id="75317-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="75317-269">Byte</span><span class="sxs-lookup"><span data-stu-id="75317-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="75317-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="75317-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="75317-271">列名</span><span class="sxs-lookup"><span data-stu-id="75317-271">ColumnName</span></span>|<span data-ttu-id="75317-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="75317-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="75317-274">String</span><span class="sxs-lookup"><span data-stu-id="75317-274">String</span></span>|  
|<span data-ttu-id="75317-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="75317-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="75317-276">String</span><span class="sxs-lookup"><span data-stu-id="75317-276">String</span></span>|  
|<span data-ttu-id="75317-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-278">String</span><span class="sxs-lookup"><span data-stu-id="75317-278">String</span></span>|  
|<span data-ttu-id="75317-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-279">COLUMN_NAME</span></span>|<span data-ttu-id="75317-280">String</span><span class="sxs-lookup"><span data-stu-id="75317-280">String</span></span>|  
|<span data-ttu-id="75317-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-281">COLUMN_TYPE</span></span>|<span data-ttu-id="75317-282">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-282">Int16</span></span>|  
|<span data-ttu-id="75317-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-283">DATA_TYPE</span></span>|<span data-ttu-id="75317-284">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-284">Int16</span></span>|  
|<span data-ttu-id="75317-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-285">TYPE_NAME</span></span>|<span data-ttu-id="75317-286">String</span><span class="sxs-lookup"><span data-stu-id="75317-286">String</span></span>|  
|<span data-ttu-id="75317-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="75317-287">COLUMN_SIZE</span></span>|<span data-ttu-id="75317-288">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-288">Int32</span></span>|  
|<span data-ttu-id="75317-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="75317-290">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-290">Int32</span></span>|  
|<span data-ttu-id="75317-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="75317-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="75317-292">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-292">Int16</span></span>|  
|<span data-ttu-id="75317-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="75317-294">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-294">Int16</span></span>|  
|<span data-ttu-id="75317-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-295">NULLABLE</span></span>|<span data-ttu-id="75317-296">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-296">Int16</span></span>|  
|<span data-ttu-id="75317-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-297">REMARKS</span></span>|<span data-ttu-id="75317-298">String</span><span class="sxs-lookup"><span data-stu-id="75317-298">String</span></span>|  
|<span data-ttu-id="75317-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="75317-299">COLUMN_DEF</span></span>|<span data-ttu-id="75317-300">String</span><span class="sxs-lookup"><span data-stu-id="75317-300">String</span></span>|  
|<span data-ttu-id="75317-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="75317-302">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-302">Int16</span></span>|  
|<span data-ttu-id="75317-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="75317-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="75317-304">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-304">Int16</span></span>|  
|<span data-ttu-id="75317-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="75317-306">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-306">Int32</span></span>|  
|<span data-ttu-id="75317-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-308">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-308">Int32</span></span>|  
|<span data-ttu-id="75317-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-309">IS_NULLABLE</span></span>|<span data-ttu-id="75317-310">String</span><span class="sxs-lookup"><span data-stu-id="75317-310">String</span></span>|  
|<span data-ttu-id="75317-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="75317-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="75317-312">String</span><span class="sxs-lookup"><span data-stu-id="75317-312">String</span></span>|  
|<span data-ttu-id="75317-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="75317-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="75317-314">String</span><span class="sxs-lookup"><span data-stu-id="75317-314">String</span></span>|  
|<span data-ttu-id="75317-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="75317-316">Byte</span><span class="sxs-lookup"><span data-stu-id="75317-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="75317-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="75317-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="75317-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="75317-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="75317-319">表</span><span class="sxs-lookup"><span data-stu-id="75317-319">Tables</span></span>  
  
-   <span data-ttu-id="75317-320">Columns</span><span class="sxs-lookup"><span data-stu-id="75317-320">Columns</span></span>  
  
-   <span data-ttu-id="75317-321">过程</span><span class="sxs-lookup"><span data-stu-id="75317-321">Procedures</span></span>  
  
-   <span data-ttu-id="75317-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="75317-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="75317-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="75317-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="75317-324">视图</span><span class="sxs-lookup"><span data-stu-id="75317-324">Views</span></span>  
  
-   <span data-ttu-id="75317-325">索引</span><span class="sxs-lookup"><span data-stu-id="75317-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="75317-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="75317-326">Tables and Views</span></span>  
  
|<span data-ttu-id="75317-327">列名</span><span class="sxs-lookup"><span data-stu-id="75317-327">ColumnName</span></span>|<span data-ttu-id="75317-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="75317-330">String</span><span class="sxs-lookup"><span data-stu-id="75317-330">String</span></span>|  
|<span data-ttu-id="75317-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-331">TABLE_OWNER</span></span>|<span data-ttu-id="75317-332">String</span><span class="sxs-lookup"><span data-stu-id="75317-332">String</span></span>|  
|<span data-ttu-id="75317-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-333">TABLE_NAME</span></span>|<span data-ttu-id="75317-334">String</span><span class="sxs-lookup"><span data-stu-id="75317-334">String</span></span>|  
|<span data-ttu-id="75317-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-335">TABLE_TYPE</span></span>|<span data-ttu-id="75317-336">String</span><span class="sxs-lookup"><span data-stu-id="75317-336">String</span></span>|  
|<span data-ttu-id="75317-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-337">REMARKS</span></span>|<span data-ttu-id="75317-338">String</span><span class="sxs-lookup"><span data-stu-id="75317-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="75317-339">Columns</span><span class="sxs-lookup"><span data-stu-id="75317-339">Columns</span></span>  
  
|<span data-ttu-id="75317-340">列名</span><span class="sxs-lookup"><span data-stu-id="75317-340">ColumnName</span></span>|<span data-ttu-id="75317-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="75317-343">String</span><span class="sxs-lookup"><span data-stu-id="75317-343">String</span></span>|  
|<span data-ttu-id="75317-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-344">TABLE_OWNER</span></span>|<span data-ttu-id="75317-345">String</span><span class="sxs-lookup"><span data-stu-id="75317-345">String</span></span>|  
|<span data-ttu-id="75317-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-346">TABLE_NAME</span></span>|<span data-ttu-id="75317-347">String</span><span class="sxs-lookup"><span data-stu-id="75317-347">String</span></span>|  
|<span data-ttu-id="75317-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-348">COLUMN_NAME</span></span>|<span data-ttu-id="75317-349">String</span><span class="sxs-lookup"><span data-stu-id="75317-349">String</span></span>|  
|<span data-ttu-id="75317-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-350">DATA_TYPE</span></span>|<span data-ttu-id="75317-351">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-351">Int16</span></span>|  
|<span data-ttu-id="75317-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-352">TYPE_NAME</span></span>|<span data-ttu-id="75317-353">String</span><span class="sxs-lookup"><span data-stu-id="75317-353">String</span></span>|  
|<span data-ttu-id="75317-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="75317-354">PRECISION</span></span>|<span data-ttu-id="75317-355">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-355">Int32</span></span>|  
|<span data-ttu-id="75317-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-356">LENGTH</span></span>|<span data-ttu-id="75317-357">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-357">Int32</span></span>|  
|<span data-ttu-id="75317-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="75317-358">SCALE</span></span>|<span data-ttu-id="75317-359">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-359">Int16</span></span>|  
|<span data-ttu-id="75317-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-360">RADIX</span></span>|<span data-ttu-id="75317-361">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-361">Int16</span></span>|  
|<span data-ttu-id="75317-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-362">NULLABLE</span></span>|<span data-ttu-id="75317-363">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-363">Int16</span></span>|  
|<span data-ttu-id="75317-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-364">REMARKS</span></span>|<span data-ttu-id="75317-365">String</span><span class="sxs-lookup"><span data-stu-id="75317-365">String</span></span>|  
|<span data-ttu-id="75317-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-367">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="75317-368">过程</span><span class="sxs-lookup"><span data-stu-id="75317-368">Procedures</span></span>  
  
|<span data-ttu-id="75317-369">列名</span><span class="sxs-lookup"><span data-stu-id="75317-369">ColumnName</span></span>|<span data-ttu-id="75317-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="75317-372">String</span><span class="sxs-lookup"><span data-stu-id="75317-372">String</span></span>|  
|<span data-ttu-id="75317-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="75317-374">String</span><span class="sxs-lookup"><span data-stu-id="75317-374">String</span></span>|  
|<span data-ttu-id="75317-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-376">String</span><span class="sxs-lookup"><span data-stu-id="75317-376">String</span></span>|  
|<span data-ttu-id="75317-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="75317-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="75317-378">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-378">Int16</span></span>|  
|<span data-ttu-id="75317-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="75317-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="75317-380">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-380">Int16</span></span>|  
|<span data-ttu-id="75317-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="75317-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="75317-382">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-382">Int16</span></span>|  
|<span data-ttu-id="75317-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-383">REMARKS</span></span>|<span data-ttu-id="75317-384">String</span><span class="sxs-lookup"><span data-stu-id="75317-384">String</span></span>|  
|<span data-ttu-id="75317-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="75317-386">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="75317-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="75317-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="75317-388">列名</span><span class="sxs-lookup"><span data-stu-id="75317-388">ColumnName</span></span>|<span data-ttu-id="75317-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="75317-391">String</span><span class="sxs-lookup"><span data-stu-id="75317-391">String</span></span>|  
|<span data-ttu-id="75317-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="75317-393">String</span><span class="sxs-lookup"><span data-stu-id="75317-393">String</span></span>|  
|<span data-ttu-id="75317-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-395">String</span><span class="sxs-lookup"><span data-stu-id="75317-395">String</span></span>|  
|<span data-ttu-id="75317-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-396">COLUMN_NAME</span></span>|<span data-ttu-id="75317-397">String</span><span class="sxs-lookup"><span data-stu-id="75317-397">String</span></span>|  
|<span data-ttu-id="75317-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-398">COLUMN_TYPE</span></span>|<span data-ttu-id="75317-399">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-399">Int16</span></span>|  
|<span data-ttu-id="75317-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-400">DATA_TYPE</span></span>|<span data-ttu-id="75317-401">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-401">Int16</span></span>|  
|<span data-ttu-id="75317-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-402">TYPE_NAME</span></span>|<span data-ttu-id="75317-403">String</span><span class="sxs-lookup"><span data-stu-id="75317-403">String</span></span>|  
|<span data-ttu-id="75317-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="75317-404">PRECISION</span></span>|<span data-ttu-id="75317-405">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-405">Int32</span></span>|  
|<span data-ttu-id="75317-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-406">LENGTH</span></span>|<span data-ttu-id="75317-407">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-407">Int32</span></span>|  
|<span data-ttu-id="75317-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="75317-408">SCALE</span></span>|<span data-ttu-id="75317-409">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-409">Int16</span></span>|  
|<span data-ttu-id="75317-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-410">RADIX</span></span>|<span data-ttu-id="75317-411">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-411">Int16</span></span>|  
|<span data-ttu-id="75317-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-412">NULLABLE</span></span>|<span data-ttu-id="75317-413">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-413">Int16</span></span>|  
|<span data-ttu-id="75317-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-414">REMARKS</span></span>|<span data-ttu-id="75317-415">String</span><span class="sxs-lookup"><span data-stu-id="75317-415">String</span></span>|  
|<span data-ttu-id="75317-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="75317-416">OVERLOAD</span></span>|<span data-ttu-id="75317-417">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-417">Int32</span></span>|  
|<span data-ttu-id="75317-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-419">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="75317-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="75317-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="75317-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="75317-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="75317-422">表</span><span class="sxs-lookup"><span data-stu-id="75317-422">Tables</span></span>  
  
-   <span data-ttu-id="75317-423">索引</span><span class="sxs-lookup"><span data-stu-id="75317-423">Indexes</span></span>  
  
-   <span data-ttu-id="75317-424">Columns</span><span class="sxs-lookup"><span data-stu-id="75317-424">Columns</span></span>  
  
-   <span data-ttu-id="75317-425">过程</span><span class="sxs-lookup"><span data-stu-id="75317-425">Procedures</span></span>  
  
-   <span data-ttu-id="75317-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="75317-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="75317-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="75317-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="75317-428">视图</span><span class="sxs-lookup"><span data-stu-id="75317-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="75317-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="75317-429">Tables and Views</span></span>  
  
|<span data-ttu-id="75317-430">列名</span><span class="sxs-lookup"><span data-stu-id="75317-430">ColumnName</span></span>|<span data-ttu-id="75317-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="75317-433">String</span><span class="sxs-lookup"><span data-stu-id="75317-433">String</span></span>|  
|<span data-ttu-id="75317-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-434">TABLE_OWNER</span></span>|<span data-ttu-id="75317-435">String</span><span class="sxs-lookup"><span data-stu-id="75317-435">String</span></span>|  
|<span data-ttu-id="75317-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-436">TABLE_NAME</span></span>|<span data-ttu-id="75317-437">String</span><span class="sxs-lookup"><span data-stu-id="75317-437">String</span></span>|  
|<span data-ttu-id="75317-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-438">TABLE_TYPE</span></span>|<span data-ttu-id="75317-439">String</span><span class="sxs-lookup"><span data-stu-id="75317-439">String</span></span>|  
|<span data-ttu-id="75317-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-440">REMARKS</span></span>|<span data-ttu-id="75317-441">String</span><span class="sxs-lookup"><span data-stu-id="75317-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="75317-442">Columns</span><span class="sxs-lookup"><span data-stu-id="75317-442">Columns</span></span>  
  
|<span data-ttu-id="75317-443">列名</span><span class="sxs-lookup"><span data-stu-id="75317-443">ColumnName</span></span>|<span data-ttu-id="75317-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="75317-446">String</span><span class="sxs-lookup"><span data-stu-id="75317-446">String</span></span>|  
|<span data-ttu-id="75317-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-447">TABLE_OWNER</span></span>|<span data-ttu-id="75317-448">String</span><span class="sxs-lookup"><span data-stu-id="75317-448">String</span></span>|  
|<span data-ttu-id="75317-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-449">TABLE_NAME</span></span>|<span data-ttu-id="75317-450">String</span><span class="sxs-lookup"><span data-stu-id="75317-450">String</span></span>|  
|<span data-ttu-id="75317-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-451">COLUMN_NAME</span></span>|<span data-ttu-id="75317-452">String</span><span class="sxs-lookup"><span data-stu-id="75317-452">String</span></span>|  
|<span data-ttu-id="75317-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-453">DATA_TYPE</span></span>|<span data-ttu-id="75317-454">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-454">Int16</span></span>|  
|<span data-ttu-id="75317-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-455">TYPE_NAME</span></span>|<span data-ttu-id="75317-456">String</span><span class="sxs-lookup"><span data-stu-id="75317-456">String</span></span>|  
|<span data-ttu-id="75317-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="75317-457">PRECISION</span></span>|<span data-ttu-id="75317-458">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-458">Int32</span></span>|  
|<span data-ttu-id="75317-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-459">LENGTH</span></span>|<span data-ttu-id="75317-460">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-460">Int32</span></span>|  
|<span data-ttu-id="75317-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="75317-461">SCALE</span></span>|<span data-ttu-id="75317-462">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-462">Int16</span></span>|  
|<span data-ttu-id="75317-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-463">RADIX</span></span>|<span data-ttu-id="75317-464">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-464">Int16</span></span>|  
|<span data-ttu-id="75317-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-465">NULLABLE</span></span>|<span data-ttu-id="75317-466">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-466">Int16</span></span>|  
|<span data-ttu-id="75317-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-467">REMARKS</span></span>|<span data-ttu-id="75317-468">String</span><span class="sxs-lookup"><span data-stu-id="75317-468">String</span></span>|  
|<span data-ttu-id="75317-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-470">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="75317-471">过程</span><span class="sxs-lookup"><span data-stu-id="75317-471">Procedures</span></span>  
  
|<span data-ttu-id="75317-472">列名</span><span class="sxs-lookup"><span data-stu-id="75317-472">ColumnName</span></span>|<span data-ttu-id="75317-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="75317-475">String</span><span class="sxs-lookup"><span data-stu-id="75317-475">String</span></span>|  
|<span data-ttu-id="75317-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="75317-477">String</span><span class="sxs-lookup"><span data-stu-id="75317-477">String</span></span>|  
|<span data-ttu-id="75317-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-479">String</span><span class="sxs-lookup"><span data-stu-id="75317-479">String</span></span>|  
|<span data-ttu-id="75317-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="75317-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="75317-481">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-481">Int16</span></span>|  
|<span data-ttu-id="75317-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="75317-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="75317-483">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-483">Int16</span></span>|  
|<span data-ttu-id="75317-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="75317-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="75317-485">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-485">Int16</span></span>|  
|<span data-ttu-id="75317-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-486">REMARKS</span></span>|<span data-ttu-id="75317-487">String</span><span class="sxs-lookup"><span data-stu-id="75317-487">String</span></span>|  
|<span data-ttu-id="75317-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="75317-489">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="75317-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="75317-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="75317-491">列名</span><span class="sxs-lookup"><span data-stu-id="75317-491">ColumnName</span></span>|<span data-ttu-id="75317-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="75317-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="75317-494">String</span><span class="sxs-lookup"><span data-stu-id="75317-494">String</span></span>|  
|<span data-ttu-id="75317-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="75317-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="75317-496">String</span><span class="sxs-lookup"><span data-stu-id="75317-496">String</span></span>|  
|<span data-ttu-id="75317-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-498">String</span><span class="sxs-lookup"><span data-stu-id="75317-498">String</span></span>|  
|<span data-ttu-id="75317-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-499">COLUMN_NAME</span></span>|<span data-ttu-id="75317-500">String</span><span class="sxs-lookup"><span data-stu-id="75317-500">String</span></span>|  
|<span data-ttu-id="75317-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-501">COLUMN_TYPE</span></span>|<span data-ttu-id="75317-502">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-502">Int16</span></span>|  
|<span data-ttu-id="75317-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-503">DATA_TYPE</span></span>|<span data-ttu-id="75317-504">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-504">Int16</span></span>|  
|<span data-ttu-id="75317-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-505">TYPE_NAME</span></span>|<span data-ttu-id="75317-506">String</span><span class="sxs-lookup"><span data-stu-id="75317-506">String</span></span>|  
|<span data-ttu-id="75317-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="75317-507">PRECISION</span></span>|<span data-ttu-id="75317-508">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-508">Int32</span></span>|  
|<span data-ttu-id="75317-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-509">LENGTH</span></span>|<span data-ttu-id="75317-510">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-510">Int32</span></span>|  
|<span data-ttu-id="75317-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="75317-511">SCALE</span></span>|<span data-ttu-id="75317-512">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-512">Int16</span></span>|  
|<span data-ttu-id="75317-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-513">RADIX</span></span>|<span data-ttu-id="75317-514">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-514">Int16</span></span>|  
|<span data-ttu-id="75317-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-515">NULLABLE</span></span>|<span data-ttu-id="75317-516">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-516">Int16</span></span>|  
|<span data-ttu-id="75317-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-517">REMARKS</span></span>|<span data-ttu-id="75317-518">String</span><span class="sxs-lookup"><span data-stu-id="75317-518">String</span></span>|  
|<span data-ttu-id="75317-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="75317-519">OVERLOAD</span></span>|<span data-ttu-id="75317-520">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-520">Int32</span></span>|  
|<span data-ttu-id="75317-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-522">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="75317-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="75317-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="75317-524">列名</span><span class="sxs-lookup"><span data-stu-id="75317-524">ColumnName</span></span>|<span data-ttu-id="75317-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="75317-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="75317-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="75317-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="75317-527">String</span><span class="sxs-lookup"><span data-stu-id="75317-527">String</span></span>|  
|<span data-ttu-id="75317-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="75317-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="75317-529">String</span><span class="sxs-lookup"><span data-stu-id="75317-529">String</span></span>|  
|<span data-ttu-id="75317-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="75317-531">String</span><span class="sxs-lookup"><span data-stu-id="75317-531">String</span></span>|  
|<span data-ttu-id="75317-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-532">COLUMN_NAME</span></span>|<span data-ttu-id="75317-533">String</span><span class="sxs-lookup"><span data-stu-id="75317-533">String</span></span>|  
|<span data-ttu-id="75317-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-534">COLUMN_TYPE</span></span>|<span data-ttu-id="75317-535">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-535">Int16</span></span>|  
|<span data-ttu-id="75317-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-536">DATA_TYPE</span></span>|<span data-ttu-id="75317-537">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-537">Int16</span></span>|  
|<span data-ttu-id="75317-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="75317-538">TYPE_NAME</span></span>|<span data-ttu-id="75317-539">String</span><span class="sxs-lookup"><span data-stu-id="75317-539">String</span></span>|  
|<span data-ttu-id="75317-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="75317-540">COLUMN_SIZE</span></span>|<span data-ttu-id="75317-541">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-541">Int32</span></span>|  
|<span data-ttu-id="75317-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="75317-543">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-543">Int32</span></span>|  
|<span data-ttu-id="75317-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="75317-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="75317-545">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-545">Int16</span></span>|  
|<span data-ttu-id="75317-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="75317-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="75317-547">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-547">Int16</span></span>|  
|<span data-ttu-id="75317-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-548">NULLABLE</span></span>|<span data-ttu-id="75317-549">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-549">Int16</span></span>|  
|<span data-ttu-id="75317-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="75317-550">REMARKS</span></span>|<span data-ttu-id="75317-551">String</span><span class="sxs-lookup"><span data-stu-id="75317-551">String</span></span>|  
|<span data-ttu-id="75317-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="75317-552">COLUMN_DEF</span></span>|<span data-ttu-id="75317-553">String</span><span class="sxs-lookup"><span data-stu-id="75317-553">String</span></span>|  
|<span data-ttu-id="75317-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="75317-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="75317-555">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-555">Int16</span></span>|  
|<span data-ttu-id="75317-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="75317-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="75317-557">Int16</span><span class="sxs-lookup"><span data-stu-id="75317-557">Int16</span></span>|  
|<span data-ttu-id="75317-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="75317-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="75317-559">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-559">Int32</span></span>|  
|<span data-ttu-id="75317-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="75317-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="75317-561">Int32</span><span class="sxs-lookup"><span data-stu-id="75317-561">Int32</span></span>|  
|<span data-ttu-id="75317-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="75317-562">IS_NULLABLE</span></span>|<span data-ttu-id="75317-563">String</span><span class="sxs-lookup"><span data-stu-id="75317-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75317-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="75317-564">See Also</span></span>  
 [<span data-ttu-id="75317-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="75317-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
