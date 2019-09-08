---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794717"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="5d155-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="5d155-102">ODBC Schema Collections</span></span>

<span data-ttu-id="5d155-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="5d155-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="5d155-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="5d155-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="5d155-105">除了通用架构集合之外，Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="5d155-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="5d155-106">表</span><span class="sxs-lookup"><span data-stu-id="5d155-106">Tables</span></span>

- <span data-ttu-id="5d155-107">索引</span><span class="sxs-lookup"><span data-stu-id="5d155-107">Indexes</span></span>

- <span data-ttu-id="5d155-108">列</span><span class="sxs-lookup"><span data-stu-id="5d155-108">Columns</span></span>

- <span data-ttu-id="5d155-109">过程</span><span class="sxs-lookup"><span data-stu-id="5d155-109">Procedures</span></span>

- <span data-ttu-id="5d155-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5d155-110">ProcedureColumns</span></span>

- <span data-ttu-id="5d155-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5d155-111">ProcedureParameters</span></span>

- <span data-ttu-id="5d155-112">Views</span><span class="sxs-lookup"><span data-stu-id="5d155-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="5d155-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="5d155-113">Tables and Views</span></span>

|<span data-ttu-id="5d155-114">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-114">ColumnName</span></span>|<span data-ttu-id="5d155-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="5d155-116">TABLE_CAT</span></span>|<span data-ttu-id="5d155-117">String</span><span class="sxs-lookup"><span data-stu-id="5d155-117">String</span></span>|
|<span data-ttu-id="5d155-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="5d155-118">TABLE_SCHEM</span></span>|<span data-ttu-id="5d155-119">String</span><span class="sxs-lookup"><span data-stu-id="5d155-119">String</span></span>|
|<span data-ttu-id="5d155-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-120">TABLE_NAME</span></span>|<span data-ttu-id="5d155-121">String</span><span class="sxs-lookup"><span data-stu-id="5d155-121">String</span></span>|
|<span data-ttu-id="5d155-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-122">TABLE_TYPE</span></span>|<span data-ttu-id="5d155-123">String</span><span class="sxs-lookup"><span data-stu-id="5d155-123">String</span></span>|
|<span data-ttu-id="5d155-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-124">REMARKS</span></span>|<span data-ttu-id="5d155-125">String</span><span class="sxs-lookup"><span data-stu-id="5d155-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="5d155-126">索引</span><span class="sxs-lookup"><span data-stu-id="5d155-126">Indexes</span></span>

|<span data-ttu-id="5d155-127">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-127">ColumnName</span></span>|<span data-ttu-id="5d155-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="5d155-129">TABLE_CAT</span></span>|<span data-ttu-id="5d155-130">String</span><span class="sxs-lookup"><span data-stu-id="5d155-130">String</span></span>|
|<span data-ttu-id="5d155-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="5d155-131">TABLE_SCHEM</span></span>|<span data-ttu-id="5d155-132">String</span><span class="sxs-lookup"><span data-stu-id="5d155-132">String</span></span>|
|<span data-ttu-id="5d155-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-133">TABLE_NAME</span></span>|<span data-ttu-id="5d155-134">String</span><span class="sxs-lookup"><span data-stu-id="5d155-134">String</span></span>|
|<span data-ttu-id="5d155-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5d155-135">NON_UNIQUE</span></span>|<span data-ttu-id="5d155-136">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-136">Int16</span></span>|
|<span data-ttu-id="5d155-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="5d155-138">String</span><span class="sxs-lookup"><span data-stu-id="5d155-138">String</span></span>|
|<span data-ttu-id="5d155-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-139">INDEX_NAME</span></span>|<span data-ttu-id="5d155-140">String</span><span class="sxs-lookup"><span data-stu-id="5d155-140">String</span></span>|
|<span data-ttu-id="5d155-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-141">TYPE</span></span>|<span data-ttu-id="5d155-142">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-142">Int16</span></span>|
|<span data-ttu-id="5d155-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-144">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-144">Int16</span></span>|
|<span data-ttu-id="5d155-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-145">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-146">String</span><span class="sxs-lookup"><span data-stu-id="5d155-146">String</span></span>|
|<span data-ttu-id="5d155-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="5d155-147">ASC_OR_DESC</span></span>|<span data-ttu-id="5d155-148">String</span><span class="sxs-lookup"><span data-stu-id="5d155-148">String</span></span>|
|<span data-ttu-id="5d155-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="5d155-149">CARDINALITY</span></span>|<span data-ttu-id="5d155-150">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-150">Int32</span></span>|
|<span data-ttu-id="5d155-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="5d155-151">PAGES</span></span>|<span data-ttu-id="5d155-152">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-152">Int32</span></span>|
|<span data-ttu-id="5d155-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="5d155-153">FILTER_CONDITION</span></span>|<span data-ttu-id="5d155-154">String</span><span class="sxs-lookup"><span data-stu-id="5d155-154">String</span></span>|
|<span data-ttu-id="5d155-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5d155-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="5d155-156">String</span><span class="sxs-lookup"><span data-stu-id="5d155-156">String</span></span>|
|<span data-ttu-id="5d155-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="5d155-158">Byte</span><span class="sxs-lookup"><span data-stu-id="5d155-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="5d155-159">列</span><span class="sxs-lookup"><span data-stu-id="5d155-159">Columns</span></span>

|<span data-ttu-id="5d155-160">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-160">ColumnName</span></span>|<span data-ttu-id="5d155-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="5d155-162">TABLE_CAT</span></span>|<span data-ttu-id="5d155-163">String</span><span class="sxs-lookup"><span data-stu-id="5d155-163">String</span></span>|
|<span data-ttu-id="5d155-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="5d155-164">TABLE_SCHEM</span></span>|<span data-ttu-id="5d155-165">String</span><span class="sxs-lookup"><span data-stu-id="5d155-165">String</span></span>|
|<span data-ttu-id="5d155-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-166">TABLE_NAME</span></span>|<span data-ttu-id="5d155-167">String</span><span class="sxs-lookup"><span data-stu-id="5d155-167">String</span></span>|
|<span data-ttu-id="5d155-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-168">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-169">String</span><span class="sxs-lookup"><span data-stu-id="5d155-169">String</span></span>|
|<span data-ttu-id="5d155-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-170">DATA_TYPE</span></span>|<span data-ttu-id="5d155-171">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-171">Int16</span></span>|
|<span data-ttu-id="5d155-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-172">TYPE_NAME</span></span>|<span data-ttu-id="5d155-173">String</span><span class="sxs-lookup"><span data-stu-id="5d155-173">String</span></span>|
|<span data-ttu-id="5d155-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="5d155-174">COLUMN_SIZE</span></span>|<span data-ttu-id="5d155-175">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-175">Int32</span></span>|
|<span data-ttu-id="5d155-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="5d155-177">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-177">Int32</span></span>|
|<span data-ttu-id="5d155-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="5d155-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="5d155-179">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-179">Int16</span></span>|
|<span data-ttu-id="5d155-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="5d155-181">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-181">Int16</span></span>|
|<span data-ttu-id="5d155-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-182">NULLABLE</span></span>|<span data-ttu-id="5d155-183">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-183">Int16</span></span>|
|<span data-ttu-id="5d155-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-184">REMARKS</span></span>|<span data-ttu-id="5d155-185">String</span><span class="sxs-lookup"><span data-stu-id="5d155-185">String</span></span>|
|<span data-ttu-id="5d155-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="5d155-186">COLUMN_DEF</span></span>|<span data-ttu-id="5d155-187">String</span><span class="sxs-lookup"><span data-stu-id="5d155-187">String</span></span>|
|<span data-ttu-id="5d155-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="5d155-189">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-189">Int16</span></span>|
|<span data-ttu-id="5d155-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="5d155-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="5d155-191">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-191">Int16</span></span>|
|<span data-ttu-id="5d155-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="5d155-193">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-193">Int32</span></span>|
|<span data-ttu-id="5d155-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-195">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-195">Int32</span></span>|
|<span data-ttu-id="5d155-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-196">IS_NULLABLE</span></span>|<span data-ttu-id="5d155-197">String</span><span class="sxs-lookup"><span data-stu-id="5d155-197">String</span></span>|
|<span data-ttu-id="5d155-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5d155-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="5d155-199">String</span><span class="sxs-lookup"><span data-stu-id="5d155-199">String</span></span>|
|<span data-ttu-id="5d155-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5d155-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="5d155-201">String</span><span class="sxs-lookup"><span data-stu-id="5d155-201">String</span></span>|
|<span data-ttu-id="5d155-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="5d155-203">Byte</span><span class="sxs-lookup"><span data-stu-id="5d155-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="5d155-204">过程</span><span class="sxs-lookup"><span data-stu-id="5d155-204">Procedures</span></span>

|<span data-ttu-id="5d155-205">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-205">ColumnName</span></span>|<span data-ttu-id="5d155-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="5d155-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="5d155-208">String</span><span class="sxs-lookup"><span data-stu-id="5d155-208">String</span></span>|
|<span data-ttu-id="5d155-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="5d155-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="5d155-210">String</span><span class="sxs-lookup"><span data-stu-id="5d155-210">String</span></span>|
|<span data-ttu-id="5d155-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-212">String</span><span class="sxs-lookup"><span data-stu-id="5d155-212">String</span></span>|
|<span data-ttu-id="5d155-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="5d155-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="5d155-214">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-214">Int32</span></span>|
|<span data-ttu-id="5d155-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="5d155-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="5d155-216">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-216">Int32</span></span>|
|<span data-ttu-id="5d155-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="5d155-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="5d155-218">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-218">Int32</span></span>|
|<span data-ttu-id="5d155-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-219">REMARKS</span></span>|<span data-ttu-id="5d155-220">String</span><span class="sxs-lookup"><span data-stu-id="5d155-220">String</span></span>|
|<span data-ttu-id="5d155-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5d155-222">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="5d155-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5d155-223">ProcedureColumns</span></span>

|<span data-ttu-id="5d155-224">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-224">ColumnName</span></span>|<span data-ttu-id="5d155-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="5d155-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="5d155-227">String</span><span class="sxs-lookup"><span data-stu-id="5d155-227">String</span></span>|
|<span data-ttu-id="5d155-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="5d155-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="5d155-229">String</span><span class="sxs-lookup"><span data-stu-id="5d155-229">String</span></span>|
|<span data-ttu-id="5d155-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-231">String</span><span class="sxs-lookup"><span data-stu-id="5d155-231">String</span></span>|
|<span data-ttu-id="5d155-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-232">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-233">String</span><span class="sxs-lookup"><span data-stu-id="5d155-233">String</span></span>|
|<span data-ttu-id="5d155-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-234">COLUMN_TYPE</span></span>|<span data-ttu-id="5d155-235">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-235">Int16</span></span>|
|<span data-ttu-id="5d155-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-236">DATA_TYPE</span></span>|<span data-ttu-id="5d155-237">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-237">Int16</span></span>|
|<span data-ttu-id="5d155-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-238">TYPE_NAME</span></span>|<span data-ttu-id="5d155-239">String</span><span class="sxs-lookup"><span data-stu-id="5d155-239">String</span></span>|
|<span data-ttu-id="5d155-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="5d155-240">COLUMN_SIZE</span></span>|<span data-ttu-id="5d155-241">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-241">Int32</span></span>|
|<span data-ttu-id="5d155-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="5d155-243">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-243">Int32</span></span>|
|<span data-ttu-id="5d155-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="5d155-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="5d155-245">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-245">Int16</span></span>|
|<span data-ttu-id="5d155-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="5d155-247">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-247">Int16</span></span>|
|<span data-ttu-id="5d155-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-248">NULLABLE</span></span>|<span data-ttu-id="5d155-249">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-249">Int16</span></span>|
|<span data-ttu-id="5d155-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-250">REMARKS</span></span>|<span data-ttu-id="5d155-251">String</span><span class="sxs-lookup"><span data-stu-id="5d155-251">String</span></span>|
|<span data-ttu-id="5d155-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="5d155-252">COLUMN_DEF</span></span>|<span data-ttu-id="5d155-253">String</span><span class="sxs-lookup"><span data-stu-id="5d155-253">String</span></span>|
|<span data-ttu-id="5d155-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="5d155-255">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-255">Int16</span></span>|
|<span data-ttu-id="5d155-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="5d155-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="5d155-257">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-257">Int16</span></span>|
|<span data-ttu-id="5d155-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="5d155-259">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-259">Int32</span></span>|
|<span data-ttu-id="5d155-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-261">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-261">Int32</span></span>|
|<span data-ttu-id="5d155-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-262">IS_NULLABLE</span></span>|<span data-ttu-id="5d155-263">String</span><span class="sxs-lookup"><span data-stu-id="5d155-263">String</span></span>|
|<span data-ttu-id="5d155-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5d155-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="5d155-265">String</span><span class="sxs-lookup"><span data-stu-id="5d155-265">String</span></span>|
|<span data-ttu-id="5d155-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5d155-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="5d155-267">String</span><span class="sxs-lookup"><span data-stu-id="5d155-267">String</span></span>|
|<span data-ttu-id="5d155-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="5d155-269">Byte</span><span class="sxs-lookup"><span data-stu-id="5d155-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="5d155-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5d155-270">ProcedureParameters</span></span>

|<span data-ttu-id="5d155-271">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-271">ColumnName</span></span>|<span data-ttu-id="5d155-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="5d155-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="5d155-274">String</span><span class="sxs-lookup"><span data-stu-id="5d155-274">String</span></span>|
|<span data-ttu-id="5d155-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="5d155-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="5d155-276">String</span><span class="sxs-lookup"><span data-stu-id="5d155-276">String</span></span>|
|<span data-ttu-id="5d155-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-278">String</span><span class="sxs-lookup"><span data-stu-id="5d155-278">String</span></span>|
|<span data-ttu-id="5d155-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-279">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-280">String</span><span class="sxs-lookup"><span data-stu-id="5d155-280">String</span></span>|
|<span data-ttu-id="5d155-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-281">COLUMN_TYPE</span></span>|<span data-ttu-id="5d155-282">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-282">Int16</span></span>|
|<span data-ttu-id="5d155-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-283">DATA_TYPE</span></span>|<span data-ttu-id="5d155-284">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-284">Int16</span></span>|
|<span data-ttu-id="5d155-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-285">TYPE_NAME</span></span>|<span data-ttu-id="5d155-286">String</span><span class="sxs-lookup"><span data-stu-id="5d155-286">String</span></span>|
|<span data-ttu-id="5d155-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="5d155-287">COLUMN_SIZE</span></span>|<span data-ttu-id="5d155-288">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-288">Int32</span></span>|
|<span data-ttu-id="5d155-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="5d155-290">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-290">Int32</span></span>|
|<span data-ttu-id="5d155-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="5d155-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="5d155-292">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-292">Int16</span></span>|
|<span data-ttu-id="5d155-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="5d155-294">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-294">Int16</span></span>|
|<span data-ttu-id="5d155-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-295">NULLABLE</span></span>|<span data-ttu-id="5d155-296">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-296">Int16</span></span>|
|<span data-ttu-id="5d155-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-297">REMARKS</span></span>|<span data-ttu-id="5d155-298">String</span><span class="sxs-lookup"><span data-stu-id="5d155-298">String</span></span>|
|<span data-ttu-id="5d155-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="5d155-299">COLUMN_DEF</span></span>|<span data-ttu-id="5d155-300">String</span><span class="sxs-lookup"><span data-stu-id="5d155-300">String</span></span>|
|<span data-ttu-id="5d155-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="5d155-302">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-302">Int16</span></span>|
|<span data-ttu-id="5d155-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="5d155-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="5d155-304">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-304">Int16</span></span>|
|<span data-ttu-id="5d155-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="5d155-306">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-306">Int32</span></span>|
|<span data-ttu-id="5d155-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-308">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-308">Int32</span></span>|
|<span data-ttu-id="5d155-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-309">IS_NULLABLE</span></span>|<span data-ttu-id="5d155-310">String</span><span class="sxs-lookup"><span data-stu-id="5d155-310">String</span></span>|
|<span data-ttu-id="5d155-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5d155-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="5d155-312">String</span><span class="sxs-lookup"><span data-stu-id="5d155-312">String</span></span>|
|<span data-ttu-id="5d155-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5d155-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="5d155-314">String</span><span class="sxs-lookup"><span data-stu-id="5d155-314">String</span></span>|
|<span data-ttu-id="5d155-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="5d155-316">Byte</span><span class="sxs-lookup"><span data-stu-id="5d155-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="5d155-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="5d155-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="5d155-318">除了通用架构集合之外，Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="5d155-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="5d155-319">表</span><span class="sxs-lookup"><span data-stu-id="5d155-319">Tables</span></span>

- <span data-ttu-id="5d155-320">列</span><span class="sxs-lookup"><span data-stu-id="5d155-320">Columns</span></span>

- <span data-ttu-id="5d155-321">过程</span><span class="sxs-lookup"><span data-stu-id="5d155-321">Procedures</span></span>

- <span data-ttu-id="5d155-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5d155-322">ProcedureColumns</span></span>

- <span data-ttu-id="5d155-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5d155-323">ProcedureParameters</span></span>

- <span data-ttu-id="5d155-324">Views</span><span class="sxs-lookup"><span data-stu-id="5d155-324">Views</span></span>

- <span data-ttu-id="5d155-325">索引</span><span class="sxs-lookup"><span data-stu-id="5d155-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="5d155-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="5d155-326">Tables and Views</span></span>

|<span data-ttu-id="5d155-327">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-327">ColumnName</span></span>|<span data-ttu-id="5d155-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="5d155-330">String</span><span class="sxs-lookup"><span data-stu-id="5d155-330">String</span></span>|
|<span data-ttu-id="5d155-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-331">TABLE_OWNER</span></span>|<span data-ttu-id="5d155-332">String</span><span class="sxs-lookup"><span data-stu-id="5d155-332">String</span></span>|
|<span data-ttu-id="5d155-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-333">TABLE_NAME</span></span>|<span data-ttu-id="5d155-334">String</span><span class="sxs-lookup"><span data-stu-id="5d155-334">String</span></span>|
|<span data-ttu-id="5d155-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-335">TABLE_TYPE</span></span>|<span data-ttu-id="5d155-336">String</span><span class="sxs-lookup"><span data-stu-id="5d155-336">String</span></span>|
|<span data-ttu-id="5d155-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-337">REMARKS</span></span>|<span data-ttu-id="5d155-338">String</span><span class="sxs-lookup"><span data-stu-id="5d155-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="5d155-339">列</span><span class="sxs-lookup"><span data-stu-id="5d155-339">Columns</span></span>

|<span data-ttu-id="5d155-340">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-340">ColumnName</span></span>|<span data-ttu-id="5d155-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="5d155-343">String</span><span class="sxs-lookup"><span data-stu-id="5d155-343">String</span></span>|
|<span data-ttu-id="5d155-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-344">TABLE_OWNER</span></span>|<span data-ttu-id="5d155-345">String</span><span class="sxs-lookup"><span data-stu-id="5d155-345">String</span></span>|
|<span data-ttu-id="5d155-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-346">TABLE_NAME</span></span>|<span data-ttu-id="5d155-347">String</span><span class="sxs-lookup"><span data-stu-id="5d155-347">String</span></span>|
|<span data-ttu-id="5d155-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-348">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-349">String</span><span class="sxs-lookup"><span data-stu-id="5d155-349">String</span></span>|
|<span data-ttu-id="5d155-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-350">DATA_TYPE</span></span>|<span data-ttu-id="5d155-351">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-351">Int16</span></span>|
|<span data-ttu-id="5d155-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-352">TYPE_NAME</span></span>|<span data-ttu-id="5d155-353">String</span><span class="sxs-lookup"><span data-stu-id="5d155-353">String</span></span>|
|<span data-ttu-id="5d155-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="5d155-354">PRECISION</span></span>|<span data-ttu-id="5d155-355">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-355">Int32</span></span>|
|<span data-ttu-id="5d155-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-356">LENGTH</span></span>|<span data-ttu-id="5d155-357">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-357">Int32</span></span>|
|<span data-ttu-id="5d155-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="5d155-358">SCALE</span></span>|<span data-ttu-id="5d155-359">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-359">Int16</span></span>|
|<span data-ttu-id="5d155-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-360">RADIX</span></span>|<span data-ttu-id="5d155-361">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-361">Int16</span></span>|
|<span data-ttu-id="5d155-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-362">NULLABLE</span></span>|<span data-ttu-id="5d155-363">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-363">Int16</span></span>|
|<span data-ttu-id="5d155-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-364">REMARKS</span></span>|<span data-ttu-id="5d155-365">String</span><span class="sxs-lookup"><span data-stu-id="5d155-365">String</span></span>|
|<span data-ttu-id="5d155-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-367">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="5d155-368">过程</span><span class="sxs-lookup"><span data-stu-id="5d155-368">Procedures</span></span>

|<span data-ttu-id="5d155-369">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-369">ColumnName</span></span>|<span data-ttu-id="5d155-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="5d155-372">String</span><span class="sxs-lookup"><span data-stu-id="5d155-372">String</span></span>|
|<span data-ttu-id="5d155-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="5d155-374">String</span><span class="sxs-lookup"><span data-stu-id="5d155-374">String</span></span>|
|<span data-ttu-id="5d155-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-376">String</span><span class="sxs-lookup"><span data-stu-id="5d155-376">String</span></span>|
|<span data-ttu-id="5d155-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="5d155-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="5d155-378">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-378">Int16</span></span>|
|<span data-ttu-id="5d155-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="5d155-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="5d155-380">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-380">Int16</span></span>|
|<span data-ttu-id="5d155-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="5d155-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="5d155-382">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-382">Int16</span></span>|
|<span data-ttu-id="5d155-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-383">REMARKS</span></span>|<span data-ttu-id="5d155-384">String</span><span class="sxs-lookup"><span data-stu-id="5d155-384">String</span></span>|
|<span data-ttu-id="5d155-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5d155-386">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="5d155-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5d155-387">ProcedureColumns</span></span>

|<span data-ttu-id="5d155-388">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-388">ColumnName</span></span>|<span data-ttu-id="5d155-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="5d155-391">String</span><span class="sxs-lookup"><span data-stu-id="5d155-391">String</span></span>|
|<span data-ttu-id="5d155-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="5d155-393">String</span><span class="sxs-lookup"><span data-stu-id="5d155-393">String</span></span>|
|<span data-ttu-id="5d155-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-395">String</span><span class="sxs-lookup"><span data-stu-id="5d155-395">String</span></span>|
|<span data-ttu-id="5d155-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-396">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-397">String</span><span class="sxs-lookup"><span data-stu-id="5d155-397">String</span></span>|
|<span data-ttu-id="5d155-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-398">COLUMN_TYPE</span></span>|<span data-ttu-id="5d155-399">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-399">Int16</span></span>|
|<span data-ttu-id="5d155-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-400">DATA_TYPE</span></span>|<span data-ttu-id="5d155-401">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-401">Int16</span></span>|
|<span data-ttu-id="5d155-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-402">TYPE_NAME</span></span>|<span data-ttu-id="5d155-403">String</span><span class="sxs-lookup"><span data-stu-id="5d155-403">String</span></span>|
|<span data-ttu-id="5d155-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="5d155-404">PRECISION</span></span>|<span data-ttu-id="5d155-405">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-405">Int32</span></span>|
|<span data-ttu-id="5d155-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-406">LENGTH</span></span>|<span data-ttu-id="5d155-407">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-407">Int32</span></span>|
|<span data-ttu-id="5d155-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="5d155-408">SCALE</span></span>|<span data-ttu-id="5d155-409">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-409">Int16</span></span>|
|<span data-ttu-id="5d155-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-410">RADIX</span></span>|<span data-ttu-id="5d155-411">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-411">Int16</span></span>|
|<span data-ttu-id="5d155-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-412">NULLABLE</span></span>|<span data-ttu-id="5d155-413">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-413">Int16</span></span>|
|<span data-ttu-id="5d155-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-414">REMARKS</span></span>|<span data-ttu-id="5d155-415">String</span><span class="sxs-lookup"><span data-stu-id="5d155-415">String</span></span>|
|<span data-ttu-id="5d155-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="5d155-416">OVERLOAD</span></span>|<span data-ttu-id="5d155-417">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-417">Int32</span></span>|
|<span data-ttu-id="5d155-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-419">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="5d155-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="5d155-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="5d155-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="5d155-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="5d155-422">表</span><span class="sxs-lookup"><span data-stu-id="5d155-422">Tables</span></span>

- <span data-ttu-id="5d155-423">索引</span><span class="sxs-lookup"><span data-stu-id="5d155-423">Indexes</span></span>

- <span data-ttu-id="5d155-424">列</span><span class="sxs-lookup"><span data-stu-id="5d155-424">Columns</span></span>

- <span data-ttu-id="5d155-425">过程</span><span class="sxs-lookup"><span data-stu-id="5d155-425">Procedures</span></span>

- <span data-ttu-id="5d155-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5d155-426">ProcedureColumns</span></span>

- <span data-ttu-id="5d155-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5d155-427">ProcedureParameters</span></span>

- <span data-ttu-id="5d155-428">Views</span><span class="sxs-lookup"><span data-stu-id="5d155-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="5d155-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="5d155-429">Tables and Views</span></span>

|<span data-ttu-id="5d155-430">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-430">ColumnName</span></span>|<span data-ttu-id="5d155-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="5d155-433">String</span><span class="sxs-lookup"><span data-stu-id="5d155-433">String</span></span>|
|<span data-ttu-id="5d155-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-434">TABLE_OWNER</span></span>|<span data-ttu-id="5d155-435">String</span><span class="sxs-lookup"><span data-stu-id="5d155-435">String</span></span>|
|<span data-ttu-id="5d155-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-436">TABLE_NAME</span></span>|<span data-ttu-id="5d155-437">String</span><span class="sxs-lookup"><span data-stu-id="5d155-437">String</span></span>|
|<span data-ttu-id="5d155-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-438">TABLE_TYPE</span></span>|<span data-ttu-id="5d155-439">String</span><span class="sxs-lookup"><span data-stu-id="5d155-439">String</span></span>|
|<span data-ttu-id="5d155-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-440">REMARKS</span></span>|<span data-ttu-id="5d155-441">String</span><span class="sxs-lookup"><span data-stu-id="5d155-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="5d155-442">列</span><span class="sxs-lookup"><span data-stu-id="5d155-442">Columns</span></span>

|<span data-ttu-id="5d155-443">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-443">ColumnName</span></span>|<span data-ttu-id="5d155-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="5d155-446">String</span><span class="sxs-lookup"><span data-stu-id="5d155-446">String</span></span>|
|<span data-ttu-id="5d155-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-447">TABLE_OWNER</span></span>|<span data-ttu-id="5d155-448">String</span><span class="sxs-lookup"><span data-stu-id="5d155-448">String</span></span>|
|<span data-ttu-id="5d155-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-449">TABLE_NAME</span></span>|<span data-ttu-id="5d155-450">String</span><span class="sxs-lookup"><span data-stu-id="5d155-450">String</span></span>|
|<span data-ttu-id="5d155-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-451">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-452">String</span><span class="sxs-lookup"><span data-stu-id="5d155-452">String</span></span>|
|<span data-ttu-id="5d155-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-453">DATA_TYPE</span></span>|<span data-ttu-id="5d155-454">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-454">Int16</span></span>|
|<span data-ttu-id="5d155-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-455">TYPE_NAME</span></span>|<span data-ttu-id="5d155-456">String</span><span class="sxs-lookup"><span data-stu-id="5d155-456">String</span></span>|
|<span data-ttu-id="5d155-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="5d155-457">PRECISION</span></span>|<span data-ttu-id="5d155-458">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-458">Int32</span></span>|
|<span data-ttu-id="5d155-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-459">LENGTH</span></span>|<span data-ttu-id="5d155-460">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-460">Int32</span></span>|
|<span data-ttu-id="5d155-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="5d155-461">SCALE</span></span>|<span data-ttu-id="5d155-462">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-462">Int16</span></span>|
|<span data-ttu-id="5d155-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-463">RADIX</span></span>|<span data-ttu-id="5d155-464">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-464">Int16</span></span>|
|<span data-ttu-id="5d155-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-465">NULLABLE</span></span>|<span data-ttu-id="5d155-466">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-466">Int16</span></span>|
|<span data-ttu-id="5d155-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-467">REMARKS</span></span>|<span data-ttu-id="5d155-468">String</span><span class="sxs-lookup"><span data-stu-id="5d155-468">String</span></span>|
|<span data-ttu-id="5d155-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-470">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="5d155-471">过程</span><span class="sxs-lookup"><span data-stu-id="5d155-471">Procedures</span></span>

|<span data-ttu-id="5d155-472">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-472">ColumnName</span></span>|<span data-ttu-id="5d155-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="5d155-475">String</span><span class="sxs-lookup"><span data-stu-id="5d155-475">String</span></span>|
|<span data-ttu-id="5d155-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="5d155-477">String</span><span class="sxs-lookup"><span data-stu-id="5d155-477">String</span></span>|
|<span data-ttu-id="5d155-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-479">String</span><span class="sxs-lookup"><span data-stu-id="5d155-479">String</span></span>|
|<span data-ttu-id="5d155-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="5d155-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="5d155-481">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-481">Int16</span></span>|
|<span data-ttu-id="5d155-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="5d155-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="5d155-483">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-483">Int16</span></span>|
|<span data-ttu-id="5d155-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="5d155-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="5d155-485">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-485">Int16</span></span>|
|<span data-ttu-id="5d155-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-486">REMARKS</span></span>|<span data-ttu-id="5d155-487">String</span><span class="sxs-lookup"><span data-stu-id="5d155-487">String</span></span>|
|<span data-ttu-id="5d155-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5d155-489">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="5d155-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5d155-490">ProcedureColumns</span></span>

|<span data-ttu-id="5d155-491">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-491">ColumnName</span></span>|<span data-ttu-id="5d155-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="5d155-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="5d155-494">String</span><span class="sxs-lookup"><span data-stu-id="5d155-494">String</span></span>|
|<span data-ttu-id="5d155-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d155-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="5d155-496">String</span><span class="sxs-lookup"><span data-stu-id="5d155-496">String</span></span>|
|<span data-ttu-id="5d155-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-498">String</span><span class="sxs-lookup"><span data-stu-id="5d155-498">String</span></span>|
|<span data-ttu-id="5d155-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-499">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-500">String</span><span class="sxs-lookup"><span data-stu-id="5d155-500">String</span></span>|
|<span data-ttu-id="5d155-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-501">COLUMN_TYPE</span></span>|<span data-ttu-id="5d155-502">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-502">Int16</span></span>|
|<span data-ttu-id="5d155-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-503">DATA_TYPE</span></span>|<span data-ttu-id="5d155-504">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-504">Int16</span></span>|
|<span data-ttu-id="5d155-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-505">TYPE_NAME</span></span>|<span data-ttu-id="5d155-506">String</span><span class="sxs-lookup"><span data-stu-id="5d155-506">String</span></span>|
|<span data-ttu-id="5d155-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="5d155-507">PRECISION</span></span>|<span data-ttu-id="5d155-508">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-508">Int32</span></span>|
|<span data-ttu-id="5d155-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-509">LENGTH</span></span>|<span data-ttu-id="5d155-510">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-510">Int32</span></span>|
|<span data-ttu-id="5d155-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="5d155-511">SCALE</span></span>|<span data-ttu-id="5d155-512">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-512">Int16</span></span>|
|<span data-ttu-id="5d155-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-513">RADIX</span></span>|<span data-ttu-id="5d155-514">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-514">Int16</span></span>|
|<span data-ttu-id="5d155-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-515">NULLABLE</span></span>|<span data-ttu-id="5d155-516">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-516">Int16</span></span>|
|<span data-ttu-id="5d155-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-517">REMARKS</span></span>|<span data-ttu-id="5d155-518">String</span><span class="sxs-lookup"><span data-stu-id="5d155-518">String</span></span>|
|<span data-ttu-id="5d155-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="5d155-519">OVERLOAD</span></span>|<span data-ttu-id="5d155-520">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-520">Int32</span></span>|
|<span data-ttu-id="5d155-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-522">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="5d155-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5d155-523">ProcedureParameters</span></span>

|<span data-ttu-id="5d155-524">列名</span><span class="sxs-lookup"><span data-stu-id="5d155-524">ColumnName</span></span>|<span data-ttu-id="5d155-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d155-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="5d155-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="5d155-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="5d155-527">String</span><span class="sxs-lookup"><span data-stu-id="5d155-527">String</span></span>|
|<span data-ttu-id="5d155-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="5d155-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="5d155-529">String</span><span class="sxs-lookup"><span data-stu-id="5d155-529">String</span></span>|
|<span data-ttu-id="5d155-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="5d155-531">String</span><span class="sxs-lookup"><span data-stu-id="5d155-531">String</span></span>|
|<span data-ttu-id="5d155-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-532">COLUMN_NAME</span></span>|<span data-ttu-id="5d155-533">String</span><span class="sxs-lookup"><span data-stu-id="5d155-533">String</span></span>|
|<span data-ttu-id="5d155-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-534">COLUMN_TYPE</span></span>|<span data-ttu-id="5d155-535">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-535">Int16</span></span>|
|<span data-ttu-id="5d155-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-536">DATA_TYPE</span></span>|<span data-ttu-id="5d155-537">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-537">Int16</span></span>|
|<span data-ttu-id="5d155-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5d155-538">TYPE_NAME</span></span>|<span data-ttu-id="5d155-539">String</span><span class="sxs-lookup"><span data-stu-id="5d155-539">String</span></span>|
|<span data-ttu-id="5d155-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="5d155-540">COLUMN_SIZE</span></span>|<span data-ttu-id="5d155-541">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-541">Int32</span></span>|
|<span data-ttu-id="5d155-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="5d155-543">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-543">Int32</span></span>|
|<span data-ttu-id="5d155-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="5d155-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="5d155-545">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-545">Int16</span></span>|
|<span data-ttu-id="5d155-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="5d155-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="5d155-547">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-547">Int16</span></span>|
|<span data-ttu-id="5d155-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-548">NULLABLE</span></span>|<span data-ttu-id="5d155-549">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-549">Int16</span></span>|
|<span data-ttu-id="5d155-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="5d155-550">REMARKS</span></span>|<span data-ttu-id="5d155-551">String</span><span class="sxs-lookup"><span data-stu-id="5d155-551">String</span></span>|
|<span data-ttu-id="5d155-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="5d155-552">COLUMN_DEF</span></span>|<span data-ttu-id="5d155-553">String</span><span class="sxs-lookup"><span data-stu-id="5d155-553">String</span></span>|
|<span data-ttu-id="5d155-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5d155-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="5d155-555">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-555">Int16</span></span>|
|<span data-ttu-id="5d155-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="5d155-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="5d155-557">Int16</span><span class="sxs-lookup"><span data-stu-id="5d155-557">Int16</span></span>|
|<span data-ttu-id="5d155-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5d155-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="5d155-559">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-559">Int32</span></span>|
|<span data-ttu-id="5d155-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d155-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="5d155-561">Int32</span><span class="sxs-lookup"><span data-stu-id="5d155-561">Int32</span></span>|
|<span data-ttu-id="5d155-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5d155-562">IS_NULLABLE</span></span>|<span data-ttu-id="5d155-563">String</span><span class="sxs-lookup"><span data-stu-id="5d155-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="5d155-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d155-564">See also</span></span>

- [<span data-ttu-id="5d155-565">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="5d155-565">ADO.NET Overview</span></span>](ado-net-overview.md)
