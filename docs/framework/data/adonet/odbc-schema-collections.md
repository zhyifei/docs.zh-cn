---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877526"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="a326a-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="a326a-102">ODBC Schema Collections</span></span>
<span data-ttu-id="a326a-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="a326a-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="a326a-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="a326a-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="a326a-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="a326a-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="a326a-106">表</span><span class="sxs-lookup"><span data-stu-id="a326a-106">Tables</span></span>  
  
-   <span data-ttu-id="a326a-107">索引</span><span class="sxs-lookup"><span data-stu-id="a326a-107">Indexes</span></span>  
  
-   <span data-ttu-id="a326a-108">Columns</span><span class="sxs-lookup"><span data-stu-id="a326a-108">Columns</span></span>  
  
-   <span data-ttu-id="a326a-109">过程</span><span class="sxs-lookup"><span data-stu-id="a326a-109">Procedures</span></span>  
  
-   <span data-ttu-id="a326a-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a326a-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="a326a-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a326a-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="a326a-112">视图</span><span class="sxs-lookup"><span data-stu-id="a326a-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="a326a-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="a326a-113">Tables and Views</span></span>  
  
|<span data-ttu-id="a326a-114">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-114">ColumnName</span></span>|<span data-ttu-id="a326a-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="a326a-116">TABLE_CAT</span></span>|<span data-ttu-id="a326a-117">String</span><span class="sxs-lookup"><span data-stu-id="a326a-117">String</span></span>|  
|<span data-ttu-id="a326a-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="a326a-118">TABLE_SCHEM</span></span>|<span data-ttu-id="a326a-119">String</span><span class="sxs-lookup"><span data-stu-id="a326a-119">String</span></span>|  
|<span data-ttu-id="a326a-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-120">TABLE_NAME</span></span>|<span data-ttu-id="a326a-121">String</span><span class="sxs-lookup"><span data-stu-id="a326a-121">String</span></span>|  
|<span data-ttu-id="a326a-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-122">TABLE_TYPE</span></span>|<span data-ttu-id="a326a-123">String</span><span class="sxs-lookup"><span data-stu-id="a326a-123">String</span></span>|  
|<span data-ttu-id="a326a-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-124">REMARKS</span></span>|<span data-ttu-id="a326a-125">String</span><span class="sxs-lookup"><span data-stu-id="a326a-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="a326a-126">索引</span><span class="sxs-lookup"><span data-stu-id="a326a-126">Indexes</span></span>  
  
|<span data-ttu-id="a326a-127">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-127">ColumnName</span></span>|<span data-ttu-id="a326a-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="a326a-129">TABLE_CAT</span></span>|<span data-ttu-id="a326a-130">String</span><span class="sxs-lookup"><span data-stu-id="a326a-130">String</span></span>|  
|<span data-ttu-id="a326a-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="a326a-131">TABLE_SCHEM</span></span>|<span data-ttu-id="a326a-132">String</span><span class="sxs-lookup"><span data-stu-id="a326a-132">String</span></span>|  
|<span data-ttu-id="a326a-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-133">TABLE_NAME</span></span>|<span data-ttu-id="a326a-134">String</span><span class="sxs-lookup"><span data-stu-id="a326a-134">String</span></span>|  
|<span data-ttu-id="a326a-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="a326a-135">NON_UNIQUE</span></span>|<span data-ttu-id="a326a-136">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-136">Int16</span></span>|  
|<span data-ttu-id="a326a-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="a326a-138">String</span><span class="sxs-lookup"><span data-stu-id="a326a-138">String</span></span>|  
|<span data-ttu-id="a326a-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-139">INDEX_NAME</span></span>|<span data-ttu-id="a326a-140">String</span><span class="sxs-lookup"><span data-stu-id="a326a-140">String</span></span>|  
|<span data-ttu-id="a326a-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-141">TYPE</span></span>|<span data-ttu-id="a326a-142">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-142">Int16</span></span>|  
|<span data-ttu-id="a326a-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-144">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-144">Int16</span></span>|  
|<span data-ttu-id="a326a-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-145">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-146">String</span><span class="sxs-lookup"><span data-stu-id="a326a-146">String</span></span>|  
|<span data-ttu-id="a326a-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="a326a-147">ASC_OR_DESC</span></span>|<span data-ttu-id="a326a-148">String</span><span class="sxs-lookup"><span data-stu-id="a326a-148">String</span></span>|  
|<span data-ttu-id="a326a-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="a326a-149">CARDINATLITY</span></span>|<span data-ttu-id="a326a-150">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-150">Int32</span></span>|  
|<span data-ttu-id="a326a-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="a326a-151">PAGES</span></span>|<span data-ttu-id="a326a-152">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-152">Int32</span></span>|  
|<span data-ttu-id="a326a-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="a326a-153">FILTER_CONDITION</span></span>|<span data-ttu-id="a326a-154">String</span><span class="sxs-lookup"><span data-stu-id="a326a-154">String</span></span>|  
|<span data-ttu-id="a326a-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a326a-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="a326a-156">String</span><span class="sxs-lookup"><span data-stu-id="a326a-156">String</span></span>|  
|<span data-ttu-id="a326a-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="a326a-158">Byte</span><span class="sxs-lookup"><span data-stu-id="a326a-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a326a-159">Columns</span><span class="sxs-lookup"><span data-stu-id="a326a-159">Columns</span></span>  
  
|<span data-ttu-id="a326a-160">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-160">ColumnName</span></span>|<span data-ttu-id="a326a-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="a326a-162">TABLE_CAT</span></span>|<span data-ttu-id="a326a-163">String</span><span class="sxs-lookup"><span data-stu-id="a326a-163">String</span></span>|  
|<span data-ttu-id="a326a-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="a326a-164">TABLE_SCHEM</span></span>|<span data-ttu-id="a326a-165">String</span><span class="sxs-lookup"><span data-stu-id="a326a-165">String</span></span>|  
|<span data-ttu-id="a326a-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-166">TABLE_NAME</span></span>|<span data-ttu-id="a326a-167">String</span><span class="sxs-lookup"><span data-stu-id="a326a-167">String</span></span>|  
|<span data-ttu-id="a326a-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-168">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-169">String</span><span class="sxs-lookup"><span data-stu-id="a326a-169">String</span></span>|  
|<span data-ttu-id="a326a-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-170">DATA_TYPE</span></span>|<span data-ttu-id="a326a-171">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-171">Int16</span></span>|  
|<span data-ttu-id="a326a-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-172">TYPE_NAME</span></span>|<span data-ttu-id="a326a-173">String</span><span class="sxs-lookup"><span data-stu-id="a326a-173">String</span></span>|  
|<span data-ttu-id="a326a-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="a326a-174">COLUMN_SIZE</span></span>|<span data-ttu-id="a326a-175">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-175">Int32</span></span>|  
|<span data-ttu-id="a326a-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="a326a-177">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-177">Int32</span></span>|  
|<span data-ttu-id="a326a-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="a326a-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="a326a-179">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-179">Int16</span></span>|  
|<span data-ttu-id="a326a-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="a326a-181">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-181">Int16</span></span>|  
|<span data-ttu-id="a326a-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-182">NULLABLE</span></span>|<span data-ttu-id="a326a-183">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-183">Int16</span></span>|  
|<span data-ttu-id="a326a-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-184">REMARKS</span></span>|<span data-ttu-id="a326a-185">String</span><span class="sxs-lookup"><span data-stu-id="a326a-185">String</span></span>|  
|<span data-ttu-id="a326a-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="a326a-186">COLUMN_DEF</span></span>|<span data-ttu-id="a326a-187">String</span><span class="sxs-lookup"><span data-stu-id="a326a-187">String</span></span>|  
|<span data-ttu-id="a326a-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="a326a-189">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-189">Int16</span></span>|  
|<span data-ttu-id="a326a-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="a326a-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="a326a-191">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-191">Int16</span></span>|  
|<span data-ttu-id="a326a-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="a326a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-193">Int32</span></span>|  
|<span data-ttu-id="a326a-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-195">Int32</span></span>|  
|<span data-ttu-id="a326a-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-196">IS_NULLABLE</span></span>|<span data-ttu-id="a326a-197">String</span><span class="sxs-lookup"><span data-stu-id="a326a-197">String</span></span>|  
|<span data-ttu-id="a326a-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a326a-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="a326a-199">String</span><span class="sxs-lookup"><span data-stu-id="a326a-199">String</span></span>|  
|<span data-ttu-id="a326a-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a326a-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="a326a-201">String</span><span class="sxs-lookup"><span data-stu-id="a326a-201">String</span></span>|  
|<span data-ttu-id="a326a-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="a326a-203">Byte</span><span class="sxs-lookup"><span data-stu-id="a326a-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a326a-204">过程</span><span class="sxs-lookup"><span data-stu-id="a326a-204">Procedures</span></span>  
  
|<span data-ttu-id="a326a-205">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-205">ColumnName</span></span>|<span data-ttu-id="a326a-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="a326a-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="a326a-208">String</span><span class="sxs-lookup"><span data-stu-id="a326a-208">String</span></span>|  
|<span data-ttu-id="a326a-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="a326a-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="a326a-210">String</span><span class="sxs-lookup"><span data-stu-id="a326a-210">String</span></span>|  
|<span data-ttu-id="a326a-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-212">String</span><span class="sxs-lookup"><span data-stu-id="a326a-212">String</span></span>|  
|<span data-ttu-id="a326a-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="a326a-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="a326a-214">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-214">Int32</span></span>|  
|<span data-ttu-id="a326a-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="a326a-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="a326a-216">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-216">Int32</span></span>|  
|<span data-ttu-id="a326a-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="a326a-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="a326a-218">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-218">Int32</span></span>|  
|<span data-ttu-id="a326a-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-219">REMARKS</span></span>|<span data-ttu-id="a326a-220">String</span><span class="sxs-lookup"><span data-stu-id="a326a-220">String</span></span>|  
|<span data-ttu-id="a326a-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="a326a-222">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="a326a-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a326a-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="a326a-224">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-224">ColumnName</span></span>|<span data-ttu-id="a326a-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="a326a-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="a326a-227">String</span><span class="sxs-lookup"><span data-stu-id="a326a-227">String</span></span>|  
|<span data-ttu-id="a326a-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="a326a-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="a326a-229">String</span><span class="sxs-lookup"><span data-stu-id="a326a-229">String</span></span>|  
|<span data-ttu-id="a326a-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-231">String</span><span class="sxs-lookup"><span data-stu-id="a326a-231">String</span></span>|  
|<span data-ttu-id="a326a-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-232">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-233">String</span><span class="sxs-lookup"><span data-stu-id="a326a-233">String</span></span>|  
|<span data-ttu-id="a326a-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-234">COLUMN_TYPE</span></span>|<span data-ttu-id="a326a-235">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-235">Int16</span></span>|  
|<span data-ttu-id="a326a-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-236">DATA_TYPE</span></span>|<span data-ttu-id="a326a-237">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-237">Int16</span></span>|  
|<span data-ttu-id="a326a-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-238">TYPE_NAME</span></span>|<span data-ttu-id="a326a-239">String</span><span class="sxs-lookup"><span data-stu-id="a326a-239">String</span></span>|  
|<span data-ttu-id="a326a-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="a326a-240">COLUMN_SIZE</span></span>|<span data-ttu-id="a326a-241">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-241">Int32</span></span>|  
|<span data-ttu-id="a326a-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="a326a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-243">Int32</span></span>|  
|<span data-ttu-id="a326a-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="a326a-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="a326a-245">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-245">Int16</span></span>|  
|<span data-ttu-id="a326a-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="a326a-247">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-247">Int16</span></span>|  
|<span data-ttu-id="a326a-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-248">NULLABLE</span></span>|<span data-ttu-id="a326a-249">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-249">Int16</span></span>|  
|<span data-ttu-id="a326a-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-250">REMARKS</span></span>|<span data-ttu-id="a326a-251">String</span><span class="sxs-lookup"><span data-stu-id="a326a-251">String</span></span>|  
|<span data-ttu-id="a326a-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="a326a-252">COLUMN_DEF</span></span>|<span data-ttu-id="a326a-253">String</span><span class="sxs-lookup"><span data-stu-id="a326a-253">String</span></span>|  
|<span data-ttu-id="a326a-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="a326a-255">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-255">Int16</span></span>|  
|<span data-ttu-id="a326a-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="a326a-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="a326a-257">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-257">Int16</span></span>|  
|<span data-ttu-id="a326a-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="a326a-259">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-259">Int32</span></span>|  
|<span data-ttu-id="a326a-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-261">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-261">Int32</span></span>|  
|<span data-ttu-id="a326a-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-262">IS_NULLABLE</span></span>|<span data-ttu-id="a326a-263">String</span><span class="sxs-lookup"><span data-stu-id="a326a-263">String</span></span>|  
|<span data-ttu-id="a326a-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a326a-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="a326a-265">String</span><span class="sxs-lookup"><span data-stu-id="a326a-265">String</span></span>|  
|<span data-ttu-id="a326a-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a326a-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="a326a-267">String</span><span class="sxs-lookup"><span data-stu-id="a326a-267">String</span></span>|  
|<span data-ttu-id="a326a-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="a326a-269">Byte</span><span class="sxs-lookup"><span data-stu-id="a326a-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="a326a-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a326a-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="a326a-271">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-271">ColumnName</span></span>|<span data-ttu-id="a326a-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="a326a-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="a326a-274">String</span><span class="sxs-lookup"><span data-stu-id="a326a-274">String</span></span>|  
|<span data-ttu-id="a326a-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="a326a-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="a326a-276">String</span><span class="sxs-lookup"><span data-stu-id="a326a-276">String</span></span>|  
|<span data-ttu-id="a326a-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-278">String</span><span class="sxs-lookup"><span data-stu-id="a326a-278">String</span></span>|  
|<span data-ttu-id="a326a-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-279">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-280">String</span><span class="sxs-lookup"><span data-stu-id="a326a-280">String</span></span>|  
|<span data-ttu-id="a326a-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-281">COLUMN_TYPE</span></span>|<span data-ttu-id="a326a-282">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-282">Int16</span></span>|  
|<span data-ttu-id="a326a-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-283">DATA_TYPE</span></span>|<span data-ttu-id="a326a-284">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-284">Int16</span></span>|  
|<span data-ttu-id="a326a-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-285">TYPE_NAME</span></span>|<span data-ttu-id="a326a-286">String</span><span class="sxs-lookup"><span data-stu-id="a326a-286">String</span></span>|  
|<span data-ttu-id="a326a-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="a326a-287">COLUMN_SIZE</span></span>|<span data-ttu-id="a326a-288">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-288">Int32</span></span>|  
|<span data-ttu-id="a326a-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="a326a-290">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-290">Int32</span></span>|  
|<span data-ttu-id="a326a-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="a326a-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="a326a-292">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-292">Int16</span></span>|  
|<span data-ttu-id="a326a-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="a326a-294">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-294">Int16</span></span>|  
|<span data-ttu-id="a326a-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-295">NULLABLE</span></span>|<span data-ttu-id="a326a-296">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-296">Int16</span></span>|  
|<span data-ttu-id="a326a-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-297">REMARKS</span></span>|<span data-ttu-id="a326a-298">String</span><span class="sxs-lookup"><span data-stu-id="a326a-298">String</span></span>|  
|<span data-ttu-id="a326a-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="a326a-299">COLUMN_DEF</span></span>|<span data-ttu-id="a326a-300">String</span><span class="sxs-lookup"><span data-stu-id="a326a-300">String</span></span>|  
|<span data-ttu-id="a326a-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="a326a-302">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-302">Int16</span></span>|  
|<span data-ttu-id="a326a-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="a326a-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="a326a-304">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-304">Int16</span></span>|  
|<span data-ttu-id="a326a-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="a326a-306">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-306">Int32</span></span>|  
|<span data-ttu-id="a326a-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-308">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-308">Int32</span></span>|  
|<span data-ttu-id="a326a-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-309">IS_NULLABLE</span></span>|<span data-ttu-id="a326a-310">String</span><span class="sxs-lookup"><span data-stu-id="a326a-310">String</span></span>|  
|<span data-ttu-id="a326a-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a326a-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="a326a-312">String</span><span class="sxs-lookup"><span data-stu-id="a326a-312">String</span></span>|  
|<span data-ttu-id="a326a-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a326a-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="a326a-314">String</span><span class="sxs-lookup"><span data-stu-id="a326a-314">String</span></span>|  
|<span data-ttu-id="a326a-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="a326a-316">Byte</span><span class="sxs-lookup"><span data-stu-id="a326a-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="a326a-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="a326a-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="a326a-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="a326a-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="a326a-319">表</span><span class="sxs-lookup"><span data-stu-id="a326a-319">Tables</span></span>  
  
-   <span data-ttu-id="a326a-320">Columns</span><span class="sxs-lookup"><span data-stu-id="a326a-320">Columns</span></span>  
  
-   <span data-ttu-id="a326a-321">过程</span><span class="sxs-lookup"><span data-stu-id="a326a-321">Procedures</span></span>  
  
-   <span data-ttu-id="a326a-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a326a-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="a326a-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a326a-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="a326a-324">视图</span><span class="sxs-lookup"><span data-stu-id="a326a-324">Views</span></span>  
  
-   <span data-ttu-id="a326a-325">索引</span><span class="sxs-lookup"><span data-stu-id="a326a-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="a326a-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="a326a-326">Tables and Views</span></span>  
  
|<span data-ttu-id="a326a-327">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-327">ColumnName</span></span>|<span data-ttu-id="a326a-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="a326a-330">String</span><span class="sxs-lookup"><span data-stu-id="a326a-330">String</span></span>|  
|<span data-ttu-id="a326a-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-331">TABLE_OWNER</span></span>|<span data-ttu-id="a326a-332">String</span><span class="sxs-lookup"><span data-stu-id="a326a-332">String</span></span>|  
|<span data-ttu-id="a326a-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-333">TABLE_NAME</span></span>|<span data-ttu-id="a326a-334">String</span><span class="sxs-lookup"><span data-stu-id="a326a-334">String</span></span>|  
|<span data-ttu-id="a326a-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-335">TABLE_TYPE</span></span>|<span data-ttu-id="a326a-336">String</span><span class="sxs-lookup"><span data-stu-id="a326a-336">String</span></span>|  
|<span data-ttu-id="a326a-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-337">REMARKS</span></span>|<span data-ttu-id="a326a-338">String</span><span class="sxs-lookup"><span data-stu-id="a326a-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a326a-339">Columns</span><span class="sxs-lookup"><span data-stu-id="a326a-339">Columns</span></span>  
  
|<span data-ttu-id="a326a-340">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-340">ColumnName</span></span>|<span data-ttu-id="a326a-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="a326a-343">String</span><span class="sxs-lookup"><span data-stu-id="a326a-343">String</span></span>|  
|<span data-ttu-id="a326a-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-344">TABLE_OWNER</span></span>|<span data-ttu-id="a326a-345">String</span><span class="sxs-lookup"><span data-stu-id="a326a-345">String</span></span>|  
|<span data-ttu-id="a326a-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-346">TABLE_NAME</span></span>|<span data-ttu-id="a326a-347">String</span><span class="sxs-lookup"><span data-stu-id="a326a-347">String</span></span>|  
|<span data-ttu-id="a326a-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-348">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-349">String</span><span class="sxs-lookup"><span data-stu-id="a326a-349">String</span></span>|  
|<span data-ttu-id="a326a-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-350">DATA_TYPE</span></span>|<span data-ttu-id="a326a-351">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-351">Int16</span></span>|  
|<span data-ttu-id="a326a-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-352">TYPE_NAME</span></span>|<span data-ttu-id="a326a-353">String</span><span class="sxs-lookup"><span data-stu-id="a326a-353">String</span></span>|  
|<span data-ttu-id="a326a-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="a326a-354">PRECISION</span></span>|<span data-ttu-id="a326a-355">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-355">Int32</span></span>|  
|<span data-ttu-id="a326a-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-356">LENGTH</span></span>|<span data-ttu-id="a326a-357">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-357">Int32</span></span>|  
|<span data-ttu-id="a326a-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="a326a-358">SCALE</span></span>|<span data-ttu-id="a326a-359">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-359">Int16</span></span>|  
|<span data-ttu-id="a326a-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-360">RADIX</span></span>|<span data-ttu-id="a326a-361">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-361">Int16</span></span>|  
|<span data-ttu-id="a326a-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-362">NULLABLE</span></span>|<span data-ttu-id="a326a-363">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-363">Int16</span></span>|  
|<span data-ttu-id="a326a-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-364">REMARKS</span></span>|<span data-ttu-id="a326a-365">String</span><span class="sxs-lookup"><span data-stu-id="a326a-365">String</span></span>|  
|<span data-ttu-id="a326a-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-367">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a326a-368">过程</span><span class="sxs-lookup"><span data-stu-id="a326a-368">Procedures</span></span>  
  
|<span data-ttu-id="a326a-369">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-369">ColumnName</span></span>|<span data-ttu-id="a326a-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="a326a-372">String</span><span class="sxs-lookup"><span data-stu-id="a326a-372">String</span></span>|  
|<span data-ttu-id="a326a-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="a326a-374">String</span><span class="sxs-lookup"><span data-stu-id="a326a-374">String</span></span>|  
|<span data-ttu-id="a326a-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-376">String</span><span class="sxs-lookup"><span data-stu-id="a326a-376">String</span></span>|  
|<span data-ttu-id="a326a-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="a326a-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="a326a-378">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-378">Int16</span></span>|  
|<span data-ttu-id="a326a-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="a326a-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="a326a-380">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-380">Int16</span></span>|  
|<span data-ttu-id="a326a-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="a326a-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="a326a-382">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-382">Int16</span></span>|  
|<span data-ttu-id="a326a-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-383">REMARKS</span></span>|<span data-ttu-id="a326a-384">String</span><span class="sxs-lookup"><span data-stu-id="a326a-384">String</span></span>|  
|<span data-ttu-id="a326a-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="a326a-386">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="a326a-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a326a-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="a326a-388">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-388">ColumnName</span></span>|<span data-ttu-id="a326a-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="a326a-391">String</span><span class="sxs-lookup"><span data-stu-id="a326a-391">String</span></span>|  
|<span data-ttu-id="a326a-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="a326a-393">String</span><span class="sxs-lookup"><span data-stu-id="a326a-393">String</span></span>|  
|<span data-ttu-id="a326a-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-395">String</span><span class="sxs-lookup"><span data-stu-id="a326a-395">String</span></span>|  
|<span data-ttu-id="a326a-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-396">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-397">String</span><span class="sxs-lookup"><span data-stu-id="a326a-397">String</span></span>|  
|<span data-ttu-id="a326a-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-398">COLUMN_TYPE</span></span>|<span data-ttu-id="a326a-399">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-399">Int16</span></span>|  
|<span data-ttu-id="a326a-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-400">DATA_TYPE</span></span>|<span data-ttu-id="a326a-401">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-401">Int16</span></span>|  
|<span data-ttu-id="a326a-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-402">TYPE_NAME</span></span>|<span data-ttu-id="a326a-403">String</span><span class="sxs-lookup"><span data-stu-id="a326a-403">String</span></span>|  
|<span data-ttu-id="a326a-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="a326a-404">PRECISION</span></span>|<span data-ttu-id="a326a-405">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-405">Int32</span></span>|  
|<span data-ttu-id="a326a-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-406">LENGTH</span></span>|<span data-ttu-id="a326a-407">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-407">Int32</span></span>|  
|<span data-ttu-id="a326a-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="a326a-408">SCALE</span></span>|<span data-ttu-id="a326a-409">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-409">Int16</span></span>|  
|<span data-ttu-id="a326a-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-410">RADIX</span></span>|<span data-ttu-id="a326a-411">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-411">Int16</span></span>|  
|<span data-ttu-id="a326a-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-412">NULLABLE</span></span>|<span data-ttu-id="a326a-413">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-413">Int16</span></span>|  
|<span data-ttu-id="a326a-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-414">REMARKS</span></span>|<span data-ttu-id="a326a-415">String</span><span class="sxs-lookup"><span data-stu-id="a326a-415">String</span></span>|  
|<span data-ttu-id="a326a-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="a326a-416">OVERLOAD</span></span>|<span data-ttu-id="a326a-417">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-417">Int32</span></span>|  
|<span data-ttu-id="a326a-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-419">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="a326a-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="a326a-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="a326a-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="a326a-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="a326a-422">表</span><span class="sxs-lookup"><span data-stu-id="a326a-422">Tables</span></span>  
  
-   <span data-ttu-id="a326a-423">索引</span><span class="sxs-lookup"><span data-stu-id="a326a-423">Indexes</span></span>  
  
-   <span data-ttu-id="a326a-424">Columns</span><span class="sxs-lookup"><span data-stu-id="a326a-424">Columns</span></span>  
  
-   <span data-ttu-id="a326a-425">过程</span><span class="sxs-lookup"><span data-stu-id="a326a-425">Procedures</span></span>  
  
-   <span data-ttu-id="a326a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a326a-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="a326a-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a326a-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="a326a-428">视图</span><span class="sxs-lookup"><span data-stu-id="a326a-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="a326a-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="a326a-429">Tables and Views</span></span>  
  
|<span data-ttu-id="a326a-430">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-430">ColumnName</span></span>|<span data-ttu-id="a326a-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="a326a-433">String</span><span class="sxs-lookup"><span data-stu-id="a326a-433">String</span></span>|  
|<span data-ttu-id="a326a-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-434">TABLE_OWNER</span></span>|<span data-ttu-id="a326a-435">String</span><span class="sxs-lookup"><span data-stu-id="a326a-435">String</span></span>|  
|<span data-ttu-id="a326a-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-436">TABLE_NAME</span></span>|<span data-ttu-id="a326a-437">String</span><span class="sxs-lookup"><span data-stu-id="a326a-437">String</span></span>|  
|<span data-ttu-id="a326a-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-438">TABLE_TYPE</span></span>|<span data-ttu-id="a326a-439">String</span><span class="sxs-lookup"><span data-stu-id="a326a-439">String</span></span>|  
|<span data-ttu-id="a326a-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-440">REMARKS</span></span>|<span data-ttu-id="a326a-441">String</span><span class="sxs-lookup"><span data-stu-id="a326a-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a326a-442">Columns</span><span class="sxs-lookup"><span data-stu-id="a326a-442">Columns</span></span>  
  
|<span data-ttu-id="a326a-443">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-443">ColumnName</span></span>|<span data-ttu-id="a326a-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="a326a-446">String</span><span class="sxs-lookup"><span data-stu-id="a326a-446">String</span></span>|  
|<span data-ttu-id="a326a-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-447">TABLE_OWNER</span></span>|<span data-ttu-id="a326a-448">String</span><span class="sxs-lookup"><span data-stu-id="a326a-448">String</span></span>|  
|<span data-ttu-id="a326a-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-449">TABLE_NAME</span></span>|<span data-ttu-id="a326a-450">String</span><span class="sxs-lookup"><span data-stu-id="a326a-450">String</span></span>|  
|<span data-ttu-id="a326a-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-451">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-452">String</span><span class="sxs-lookup"><span data-stu-id="a326a-452">String</span></span>|  
|<span data-ttu-id="a326a-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-453">DATA_TYPE</span></span>|<span data-ttu-id="a326a-454">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-454">Int16</span></span>|  
|<span data-ttu-id="a326a-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-455">TYPE_NAME</span></span>|<span data-ttu-id="a326a-456">String</span><span class="sxs-lookup"><span data-stu-id="a326a-456">String</span></span>|  
|<span data-ttu-id="a326a-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="a326a-457">PRECISION</span></span>|<span data-ttu-id="a326a-458">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-458">Int32</span></span>|  
|<span data-ttu-id="a326a-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-459">LENGTH</span></span>|<span data-ttu-id="a326a-460">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-460">Int32</span></span>|  
|<span data-ttu-id="a326a-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="a326a-461">SCALE</span></span>|<span data-ttu-id="a326a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-462">Int16</span></span>|  
|<span data-ttu-id="a326a-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-463">RADIX</span></span>|<span data-ttu-id="a326a-464">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-464">Int16</span></span>|  
|<span data-ttu-id="a326a-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-465">NULLABLE</span></span>|<span data-ttu-id="a326a-466">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-466">Int16</span></span>|  
|<span data-ttu-id="a326a-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-467">REMARKS</span></span>|<span data-ttu-id="a326a-468">String</span><span class="sxs-lookup"><span data-stu-id="a326a-468">String</span></span>|  
|<span data-ttu-id="a326a-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-470">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a326a-471">过程</span><span class="sxs-lookup"><span data-stu-id="a326a-471">Procedures</span></span>  
  
|<span data-ttu-id="a326a-472">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-472">ColumnName</span></span>|<span data-ttu-id="a326a-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="a326a-475">String</span><span class="sxs-lookup"><span data-stu-id="a326a-475">String</span></span>|  
|<span data-ttu-id="a326a-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="a326a-477">String</span><span class="sxs-lookup"><span data-stu-id="a326a-477">String</span></span>|  
|<span data-ttu-id="a326a-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-479">String</span><span class="sxs-lookup"><span data-stu-id="a326a-479">String</span></span>|  
|<span data-ttu-id="a326a-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="a326a-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="a326a-481">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-481">Int16</span></span>|  
|<span data-ttu-id="a326a-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="a326a-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="a326a-483">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-483">Int16</span></span>|  
|<span data-ttu-id="a326a-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="a326a-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="a326a-485">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-485">Int16</span></span>|  
|<span data-ttu-id="a326a-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-486">REMARKS</span></span>|<span data-ttu-id="a326a-487">String</span><span class="sxs-lookup"><span data-stu-id="a326a-487">String</span></span>|  
|<span data-ttu-id="a326a-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="a326a-489">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="a326a-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a326a-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="a326a-491">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-491">ColumnName</span></span>|<span data-ttu-id="a326a-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="a326a-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="a326a-494">String</span><span class="sxs-lookup"><span data-stu-id="a326a-494">String</span></span>|  
|<span data-ttu-id="a326a-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="a326a-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="a326a-496">String</span><span class="sxs-lookup"><span data-stu-id="a326a-496">String</span></span>|  
|<span data-ttu-id="a326a-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-498">String</span><span class="sxs-lookup"><span data-stu-id="a326a-498">String</span></span>|  
|<span data-ttu-id="a326a-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-499">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-500">String</span><span class="sxs-lookup"><span data-stu-id="a326a-500">String</span></span>|  
|<span data-ttu-id="a326a-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-501">COLUMN_TYPE</span></span>|<span data-ttu-id="a326a-502">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-502">Int16</span></span>|  
|<span data-ttu-id="a326a-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-503">DATA_TYPE</span></span>|<span data-ttu-id="a326a-504">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-504">Int16</span></span>|  
|<span data-ttu-id="a326a-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-505">TYPE_NAME</span></span>|<span data-ttu-id="a326a-506">String</span><span class="sxs-lookup"><span data-stu-id="a326a-506">String</span></span>|  
|<span data-ttu-id="a326a-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="a326a-507">PRECISION</span></span>|<span data-ttu-id="a326a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-508">Int32</span></span>|  
|<span data-ttu-id="a326a-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-509">LENGTH</span></span>|<span data-ttu-id="a326a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-510">Int32</span></span>|  
|<span data-ttu-id="a326a-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="a326a-511">SCALE</span></span>|<span data-ttu-id="a326a-512">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-512">Int16</span></span>|  
|<span data-ttu-id="a326a-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-513">RADIX</span></span>|<span data-ttu-id="a326a-514">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-514">Int16</span></span>|  
|<span data-ttu-id="a326a-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-515">NULLABLE</span></span>|<span data-ttu-id="a326a-516">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-516">Int16</span></span>|  
|<span data-ttu-id="a326a-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-517">REMARKS</span></span>|<span data-ttu-id="a326a-518">String</span><span class="sxs-lookup"><span data-stu-id="a326a-518">String</span></span>|  
|<span data-ttu-id="a326a-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="a326a-519">OVERLOAD</span></span>|<span data-ttu-id="a326a-520">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-520">Int32</span></span>|  
|<span data-ttu-id="a326a-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-522">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="a326a-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a326a-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="a326a-524">列名</span><span class="sxs-lookup"><span data-stu-id="a326a-524">ColumnName</span></span>|<span data-ttu-id="a326a-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="a326a-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a326a-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="a326a-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="a326a-527">String</span><span class="sxs-lookup"><span data-stu-id="a326a-527">String</span></span>|  
|<span data-ttu-id="a326a-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="a326a-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="a326a-529">String</span><span class="sxs-lookup"><span data-stu-id="a326a-529">String</span></span>|  
|<span data-ttu-id="a326a-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="a326a-531">String</span><span class="sxs-lookup"><span data-stu-id="a326a-531">String</span></span>|  
|<span data-ttu-id="a326a-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-532">COLUMN_NAME</span></span>|<span data-ttu-id="a326a-533">String</span><span class="sxs-lookup"><span data-stu-id="a326a-533">String</span></span>|  
|<span data-ttu-id="a326a-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-534">COLUMN_TYPE</span></span>|<span data-ttu-id="a326a-535">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-535">Int16</span></span>|  
|<span data-ttu-id="a326a-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-536">DATA_TYPE</span></span>|<span data-ttu-id="a326a-537">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-537">Int16</span></span>|  
|<span data-ttu-id="a326a-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a326a-538">TYPE_NAME</span></span>|<span data-ttu-id="a326a-539">String</span><span class="sxs-lookup"><span data-stu-id="a326a-539">String</span></span>|  
|<span data-ttu-id="a326a-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="a326a-540">COLUMN_SIZE</span></span>|<span data-ttu-id="a326a-541">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-541">Int32</span></span>|  
|<span data-ttu-id="a326a-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="a326a-543">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-543">Int32</span></span>|  
|<span data-ttu-id="a326a-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="a326a-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="a326a-545">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-545">Int16</span></span>|  
|<span data-ttu-id="a326a-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="a326a-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="a326a-547">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-547">Int16</span></span>|  
|<span data-ttu-id="a326a-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-548">NULLABLE</span></span>|<span data-ttu-id="a326a-549">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-549">Int16</span></span>|  
|<span data-ttu-id="a326a-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a326a-550">REMARKS</span></span>|<span data-ttu-id="a326a-551">String</span><span class="sxs-lookup"><span data-stu-id="a326a-551">String</span></span>|  
|<span data-ttu-id="a326a-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="a326a-552">COLUMN_DEF</span></span>|<span data-ttu-id="a326a-553">String</span><span class="sxs-lookup"><span data-stu-id="a326a-553">String</span></span>|  
|<span data-ttu-id="a326a-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a326a-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="a326a-555">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-555">Int16</span></span>|  
|<span data-ttu-id="a326a-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="a326a-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="a326a-557">Int16</span><span class="sxs-lookup"><span data-stu-id="a326a-557">Int16</span></span>|  
|<span data-ttu-id="a326a-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a326a-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="a326a-559">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-559">Int32</span></span>|  
|<span data-ttu-id="a326a-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a326a-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="a326a-561">Int32</span><span class="sxs-lookup"><span data-stu-id="a326a-561">Int32</span></span>|  
|<span data-ttu-id="a326a-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a326a-562">IS_NULLABLE</span></span>|<span data-ttu-id="a326a-563">String</span><span class="sxs-lookup"><span data-stu-id="a326a-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a326a-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="a326a-564">See Also</span></span>  
 [<span data-ttu-id="a326a-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a326a-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
