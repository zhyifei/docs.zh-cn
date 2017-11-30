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
ms.openlocfilehash: 889e84db39af1257d709ef049e18d4397ea700d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="d7c6e-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="d7c6e-102">ODBC Schema Collections</span></span>
<span data-ttu-id="d7c6e-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="d7c6e-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="d7c6e-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="d7c6e-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="d7c6e-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="d7c6e-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d7c6e-106">表</span><span class="sxs-lookup"><span data-stu-id="d7c6e-106">Tables</span></span>  
  
-   <span data-ttu-id="d7c6e-107">索引</span><span class="sxs-lookup"><span data-stu-id="d7c6e-107">Indexes</span></span>  
  
-   <span data-ttu-id="d7c6e-108">Columns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-108">Columns</span></span>  
  
-   <span data-ttu-id="d7c6e-109">过程</span><span class="sxs-lookup"><span data-stu-id="d7c6e-109">Procedures</span></span>  
  
-   <span data-ttu-id="d7c6e-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d7c6e-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d7c6e-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d7c6e-112">视图</span><span class="sxs-lookup"><span data-stu-id="d7c6e-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="d7c6e-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="d7c6e-113">Tables and Views</span></span>  
  
|<span data-ttu-id="d7c6e-114">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-114">ColumnName</span></span>|<span data-ttu-id="d7c6e-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d7c6e-116">TABLE_CAT</span></span>|<span data-ttu-id="d7c6e-117">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-117">String</span></span>|  
|<span data-ttu-id="d7c6e-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d7c6e-118">TABLE_SCHEM</span></span>|<span data-ttu-id="d7c6e-119">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-119">String</span></span>|  
|<span data-ttu-id="d7c6e-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-120">TABLE_NAME</span></span>|<span data-ttu-id="d7c6e-121">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-121">String</span></span>|  
|<span data-ttu-id="d7c6e-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-122">TABLE_TYPE</span></span>|<span data-ttu-id="d7c6e-123">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-123">String</span></span>|  
|<span data-ttu-id="d7c6e-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-124">REMARKS</span></span>|<span data-ttu-id="d7c6e-125">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d7c6e-126">索引</span><span class="sxs-lookup"><span data-stu-id="d7c6e-126">Indexes</span></span>  
  
|<span data-ttu-id="d7c6e-127">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-127">ColumnName</span></span>|<span data-ttu-id="d7c6e-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d7c6e-129">TABLE_CAT</span></span>|<span data-ttu-id="d7c6e-130">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-130">String</span></span>|  
|<span data-ttu-id="d7c6e-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d7c6e-131">TABLE_SCHEM</span></span>|<span data-ttu-id="d7c6e-132">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-132">String</span></span>|  
|<span data-ttu-id="d7c6e-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-133">TABLE_NAME</span></span>|<span data-ttu-id="d7c6e-134">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-134">String</span></span>|  
|<span data-ttu-id="d7c6e-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-135">NON_UNIQUE</span></span>|<span data-ttu-id="d7c6e-136">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-136">Int16</span></span>|  
|<span data-ttu-id="d7c6e-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-138">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-138">String</span></span>|  
|<span data-ttu-id="d7c6e-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-139">INDEX_NAME</span></span>|<span data-ttu-id="d7c6e-140">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-140">String</span></span>|  
|<span data-ttu-id="d7c6e-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-141">TYPE</span></span>|<span data-ttu-id="d7c6e-142">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-142">Int16</span></span>|  
|<span data-ttu-id="d7c6e-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-144">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-144">Int16</span></span>|  
|<span data-ttu-id="d7c6e-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-145">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-146">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-146">String</span></span>|  
|<span data-ttu-id="d7c6e-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="d7c6e-147">ASC_OR_DESC</span></span>|<span data-ttu-id="d7c6e-148">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-148">String</span></span>|  
|<span data-ttu-id="d7c6e-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="d7c6e-149">CARDINATLITY</span></span>|<span data-ttu-id="d7c6e-150">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-150">Int32</span></span>|  
|<span data-ttu-id="d7c6e-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="d7c6e-151">PAGES</span></span>|<span data-ttu-id="d7c6e-152">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-152">Int32</span></span>|  
|<span data-ttu-id="d7c6e-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-153">FILTER_CONDITION</span></span>|<span data-ttu-id="d7c6e-154">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-154">String</span></span>|  
|<span data-ttu-id="d7c6e-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d7c6e-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d7c6e-156">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-156">String</span></span>|  
|<span data-ttu-id="d7c6e-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-158">Byte</span><span class="sxs-lookup"><span data-stu-id="d7c6e-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d7c6e-159">Columns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-159">Columns</span></span>  
  
|<span data-ttu-id="d7c6e-160">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-160">ColumnName</span></span>|<span data-ttu-id="d7c6e-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d7c6e-162">TABLE_CAT</span></span>|<span data-ttu-id="d7c6e-163">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-163">String</span></span>|  
|<span data-ttu-id="d7c6e-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d7c6e-164">TABLE_SCHEM</span></span>|<span data-ttu-id="d7c6e-165">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-165">String</span></span>|  
|<span data-ttu-id="d7c6e-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-166">TABLE_NAME</span></span>|<span data-ttu-id="d7c6e-167">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-167">String</span></span>|  
|<span data-ttu-id="d7c6e-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-168">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-169">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-169">String</span></span>|  
|<span data-ttu-id="d7c6e-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-170">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-171">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-171">Int16</span></span>|  
|<span data-ttu-id="d7c6e-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-172">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-173">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-173">String</span></span>|  
|<span data-ttu-id="d7c6e-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-174">COLUMN_SIZE</span></span>|<span data-ttu-id="d7c6e-175">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-175">Int32</span></span>|  
|<span data-ttu-id="d7c6e-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="d7c6e-177">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-177">Int32</span></span>|  
|<span data-ttu-id="d7c6e-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d7c6e-179">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-179">Int16</span></span>|  
|<span data-ttu-id="d7c6e-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d7c6e-181">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-181">Int16</span></span>|  
|<span data-ttu-id="d7c6e-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-182">NULLABLE</span></span>|<span data-ttu-id="d7c6e-183">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-183">Int16</span></span>|  
|<span data-ttu-id="d7c6e-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-184">REMARKS</span></span>|<span data-ttu-id="d7c6e-185">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-185">String</span></span>|  
|<span data-ttu-id="d7c6e-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d7c6e-186">COLUMN_DEF</span></span>|<span data-ttu-id="d7c6e-187">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-187">String</span></span>|  
|<span data-ttu-id="d7c6e-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-189">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-189">Int16</span></span>|  
|<span data-ttu-id="d7c6e-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d7c6e-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d7c6e-191">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-191">Int16</span></span>|  
|<span data-ttu-id="d7c6e-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d7c6e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-193">Int32</span></span>|  
|<span data-ttu-id="d7c6e-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-195">Int32</span></span>|  
|<span data-ttu-id="d7c6e-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-196">IS_NULLABLE</span></span>|<span data-ttu-id="d7c6e-197">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-197">String</span></span>|  
|<span data-ttu-id="d7c6e-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d7c6e-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d7c6e-199">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-199">String</span></span>|  
|<span data-ttu-id="d7c6e-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d7c6e-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d7c6e-201">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-201">String</span></span>|  
|<span data-ttu-id="d7c6e-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-203">Byte</span><span class="sxs-lookup"><span data-stu-id="d7c6e-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d7c6e-204">过程</span><span class="sxs-lookup"><span data-stu-id="d7c6e-204">Procedures</span></span>  
  
|<span data-ttu-id="d7c6e-205">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-205">ColumnName</span></span>|<span data-ttu-id="d7c6e-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d7c6e-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="d7c6e-208">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-208">String</span></span>|  
|<span data-ttu-id="d7c6e-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d7c6e-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d7c6e-210">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-210">String</span></span>|  
|<span data-ttu-id="d7c6e-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-212">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-212">String</span></span>|  
|<span data-ttu-id="d7c6e-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d7c6e-214">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-214">Int32</span></span>|  
|<span data-ttu-id="d7c6e-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d7c6e-216">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-216">Int32</span></span>|  
|<span data-ttu-id="d7c6e-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d7c6e-218">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-218">Int32</span></span>|  
|<span data-ttu-id="d7c6e-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-219">REMARKS</span></span>|<span data-ttu-id="d7c6e-220">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-220">String</span></span>|  
|<span data-ttu-id="d7c6e-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d7c6e-222">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d7c6e-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d7c6e-224">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-224">ColumnName</span></span>|<span data-ttu-id="d7c6e-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d7c6e-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="d7c6e-227">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-227">String</span></span>|  
|<span data-ttu-id="d7c6e-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d7c6e-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d7c6e-229">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-229">String</span></span>|  
|<span data-ttu-id="d7c6e-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-231">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-231">String</span></span>|  
|<span data-ttu-id="d7c6e-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-232">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-233">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-233">String</span></span>|  
|<span data-ttu-id="d7c6e-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-234">COLUMN_TYPE</span></span>|<span data-ttu-id="d7c6e-235">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-235">Int16</span></span>|  
|<span data-ttu-id="d7c6e-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-236">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-237">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-237">Int16</span></span>|  
|<span data-ttu-id="d7c6e-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-238">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-239">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-239">String</span></span>|  
|<span data-ttu-id="d7c6e-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-240">COLUMN_SIZE</span></span>|<span data-ttu-id="d7c6e-241">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-241">Int32</span></span>|  
|<span data-ttu-id="d7c6e-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="d7c6e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-243">Int32</span></span>|  
|<span data-ttu-id="d7c6e-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d7c6e-245">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-245">Int16</span></span>|  
|<span data-ttu-id="d7c6e-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d7c6e-247">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-247">Int16</span></span>|  
|<span data-ttu-id="d7c6e-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-248">NULLABLE</span></span>|<span data-ttu-id="d7c6e-249">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-249">Int16</span></span>|  
|<span data-ttu-id="d7c6e-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-250">REMARKS</span></span>|<span data-ttu-id="d7c6e-251">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-251">String</span></span>|  
|<span data-ttu-id="d7c6e-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d7c6e-252">COLUMN_DEF</span></span>|<span data-ttu-id="d7c6e-253">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-253">String</span></span>|  
|<span data-ttu-id="d7c6e-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-255">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-255">Int16</span></span>|  
|<span data-ttu-id="d7c6e-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d7c6e-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d7c6e-257">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-257">Int16</span></span>|  
|<span data-ttu-id="d7c6e-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d7c6e-259">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-259">Int32</span></span>|  
|<span data-ttu-id="d7c6e-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-261">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-261">Int32</span></span>|  
|<span data-ttu-id="d7c6e-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-262">IS_NULLABLE</span></span>|<span data-ttu-id="d7c6e-263">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-263">String</span></span>|  
|<span data-ttu-id="d7c6e-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d7c6e-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d7c6e-265">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-265">String</span></span>|  
|<span data-ttu-id="d7c6e-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d7c6e-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d7c6e-267">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-267">String</span></span>|  
|<span data-ttu-id="d7c6e-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-269">Byte</span><span class="sxs-lookup"><span data-stu-id="d7c6e-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d7c6e-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d7c6e-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d7c6e-271">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-271">ColumnName</span></span>|<span data-ttu-id="d7c6e-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d7c6e-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="d7c6e-274">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-274">String</span></span>|  
|<span data-ttu-id="d7c6e-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d7c6e-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d7c6e-276">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-276">String</span></span>|  
|<span data-ttu-id="d7c6e-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-278">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-278">String</span></span>|  
|<span data-ttu-id="d7c6e-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-279">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-280">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-280">String</span></span>|  
|<span data-ttu-id="d7c6e-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-281">COLUMN_TYPE</span></span>|<span data-ttu-id="d7c6e-282">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-282">Int16</span></span>|  
|<span data-ttu-id="d7c6e-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-283">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-284">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-284">Int16</span></span>|  
|<span data-ttu-id="d7c6e-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-285">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-286">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-286">String</span></span>|  
|<span data-ttu-id="d7c6e-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-287">COLUMN_SIZE</span></span>|<span data-ttu-id="d7c6e-288">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-288">Int32</span></span>|  
|<span data-ttu-id="d7c6e-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="d7c6e-290">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-290">Int32</span></span>|  
|<span data-ttu-id="d7c6e-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d7c6e-292">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-292">Int16</span></span>|  
|<span data-ttu-id="d7c6e-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d7c6e-294">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-294">Int16</span></span>|  
|<span data-ttu-id="d7c6e-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-295">NULLABLE</span></span>|<span data-ttu-id="d7c6e-296">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-296">Int16</span></span>|  
|<span data-ttu-id="d7c6e-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-297">REMARKS</span></span>|<span data-ttu-id="d7c6e-298">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-298">String</span></span>|  
|<span data-ttu-id="d7c6e-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d7c6e-299">COLUMN_DEF</span></span>|<span data-ttu-id="d7c6e-300">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-300">String</span></span>|  
|<span data-ttu-id="d7c6e-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-302">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-302">Int16</span></span>|  
|<span data-ttu-id="d7c6e-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d7c6e-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d7c6e-304">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-304">Int16</span></span>|  
|<span data-ttu-id="d7c6e-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d7c6e-306">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-306">Int32</span></span>|  
|<span data-ttu-id="d7c6e-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-308">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-308">Int32</span></span>|  
|<span data-ttu-id="d7c6e-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-309">IS_NULLABLE</span></span>|<span data-ttu-id="d7c6e-310">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-310">String</span></span>|  
|<span data-ttu-id="d7c6e-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d7c6e-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d7c6e-312">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-312">String</span></span>|  
|<span data-ttu-id="d7c6e-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d7c6e-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d7c6e-314">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-314">String</span></span>|  
|<span data-ttu-id="d7c6e-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-316">Byte</span><span class="sxs-lookup"><span data-stu-id="d7c6e-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="d7c6e-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="d7c6e-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="d7c6e-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="d7c6e-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d7c6e-319">表</span><span class="sxs-lookup"><span data-stu-id="d7c6e-319">Tables</span></span>  
  
-   <span data-ttu-id="d7c6e-320">Columns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-320">Columns</span></span>  
  
-   <span data-ttu-id="d7c6e-321">过程</span><span class="sxs-lookup"><span data-stu-id="d7c6e-321">Procedures</span></span>  
  
-   <span data-ttu-id="d7c6e-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d7c6e-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d7c6e-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d7c6e-324">视图</span><span class="sxs-lookup"><span data-stu-id="d7c6e-324">Views</span></span>  
  
-   <span data-ttu-id="d7c6e-325">索引</span><span class="sxs-lookup"><span data-stu-id="d7c6e-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="d7c6e-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="d7c6e-326">Tables and Views</span></span>  
  
|<span data-ttu-id="d7c6e-327">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-327">ColumnName</span></span>|<span data-ttu-id="d7c6e-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-330">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-330">String</span></span>|  
|<span data-ttu-id="d7c6e-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-331">TABLE_OWNER</span></span>|<span data-ttu-id="d7c6e-332">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-332">String</span></span>|  
|<span data-ttu-id="d7c6e-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-333">TABLE_NAME</span></span>|<span data-ttu-id="d7c6e-334">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-334">String</span></span>|  
|<span data-ttu-id="d7c6e-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-335">TABLE_TYPE</span></span>|<span data-ttu-id="d7c6e-336">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-336">String</span></span>|  
|<span data-ttu-id="d7c6e-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-337">REMARKS</span></span>|<span data-ttu-id="d7c6e-338">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d7c6e-339">Columns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-339">Columns</span></span>  
  
|<span data-ttu-id="d7c6e-340">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-340">ColumnName</span></span>|<span data-ttu-id="d7c6e-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-343">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-343">String</span></span>|  
|<span data-ttu-id="d7c6e-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-344">TABLE_OWNER</span></span>|<span data-ttu-id="d7c6e-345">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-345">String</span></span>|  
|<span data-ttu-id="d7c6e-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-346">TABLE_NAME</span></span>|<span data-ttu-id="d7c6e-347">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-347">String</span></span>|  
|<span data-ttu-id="d7c6e-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-348">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-349">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-349">String</span></span>|  
|<span data-ttu-id="d7c6e-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-350">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-351">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-351">Int16</span></span>|  
|<span data-ttu-id="d7c6e-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-352">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-353">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-353">String</span></span>|  
|<span data-ttu-id="d7c6e-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-354">PRECISION</span></span>|<span data-ttu-id="d7c6e-355">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-355">Int32</span></span>|  
|<span data-ttu-id="d7c6e-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-356">LENGTH</span></span>|<span data-ttu-id="d7c6e-357">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-357">Int32</span></span>|  
|<span data-ttu-id="d7c6e-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-358">SCALE</span></span>|<span data-ttu-id="d7c6e-359">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-359">Int16</span></span>|  
|<span data-ttu-id="d7c6e-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-360">RADIX</span></span>|<span data-ttu-id="d7c6e-361">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-361">Int16</span></span>|  
|<span data-ttu-id="d7c6e-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-362">NULLABLE</span></span>|<span data-ttu-id="d7c6e-363">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-363">Int16</span></span>|  
|<span data-ttu-id="d7c6e-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-364">REMARKS</span></span>|<span data-ttu-id="d7c6e-365">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-365">String</span></span>|  
|<span data-ttu-id="d7c6e-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-367">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d7c6e-368">过程</span><span class="sxs-lookup"><span data-stu-id="d7c6e-368">Procedures</span></span>  
  
|<span data-ttu-id="d7c6e-369">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-369">ColumnName</span></span>|<span data-ttu-id="d7c6e-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-372">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-372">String</span></span>|  
|<span data-ttu-id="d7c6e-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d7c6e-374">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-374">String</span></span>|  
|<span data-ttu-id="d7c6e-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-376">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-376">String</span></span>|  
|<span data-ttu-id="d7c6e-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d7c6e-378">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-378">Int16</span></span>|  
|<span data-ttu-id="d7c6e-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d7c6e-380">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-380">Int16</span></span>|  
|<span data-ttu-id="d7c6e-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d7c6e-382">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-382">Int16</span></span>|  
|<span data-ttu-id="d7c6e-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-383">REMARKS</span></span>|<span data-ttu-id="d7c6e-384">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-384">String</span></span>|  
|<span data-ttu-id="d7c6e-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d7c6e-386">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d7c6e-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d7c6e-388">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-388">ColumnName</span></span>|<span data-ttu-id="d7c6e-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-391">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-391">String</span></span>|  
|<span data-ttu-id="d7c6e-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d7c6e-393">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-393">String</span></span>|  
|<span data-ttu-id="d7c6e-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-395">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-395">String</span></span>|  
|<span data-ttu-id="d7c6e-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-396">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-397">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-397">String</span></span>|  
|<span data-ttu-id="d7c6e-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-398">COLUMN_TYPE</span></span>|<span data-ttu-id="d7c6e-399">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-399">Int16</span></span>|  
|<span data-ttu-id="d7c6e-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-400">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-401">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-401">Int16</span></span>|  
|<span data-ttu-id="d7c6e-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-402">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-403">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-403">String</span></span>|  
|<span data-ttu-id="d7c6e-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-404">PRECISION</span></span>|<span data-ttu-id="d7c6e-405">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-405">Int32</span></span>|  
|<span data-ttu-id="d7c6e-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-406">LENGTH</span></span>|<span data-ttu-id="d7c6e-407">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-407">Int32</span></span>|  
|<span data-ttu-id="d7c6e-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-408">SCALE</span></span>|<span data-ttu-id="d7c6e-409">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-409">Int16</span></span>|  
|<span data-ttu-id="d7c6e-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-410">RADIX</span></span>|<span data-ttu-id="d7c6e-411">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-411">Int16</span></span>|  
|<span data-ttu-id="d7c6e-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-412">NULLABLE</span></span>|<span data-ttu-id="d7c6e-413">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-413">Int16</span></span>|  
|<span data-ttu-id="d7c6e-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-414">REMARKS</span></span>|<span data-ttu-id="d7c6e-415">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-415">String</span></span>|  
|<span data-ttu-id="d7c6e-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d7c6e-416">OVERLOAD</span></span>|<span data-ttu-id="d7c6e-417">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-417">Int32</span></span>|  
|<span data-ttu-id="d7c6e-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-419">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="d7c6e-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="d7c6e-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="d7c6e-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="d7c6e-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d7c6e-422">表</span><span class="sxs-lookup"><span data-stu-id="d7c6e-422">Tables</span></span>  
  
-   <span data-ttu-id="d7c6e-423">索引</span><span class="sxs-lookup"><span data-stu-id="d7c6e-423">Indexes</span></span>  
  
-   <span data-ttu-id="d7c6e-424">Columns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-424">Columns</span></span>  
  
-   <span data-ttu-id="d7c6e-425">过程</span><span class="sxs-lookup"><span data-stu-id="d7c6e-425">Procedures</span></span>  
  
-   <span data-ttu-id="d7c6e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d7c6e-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d7c6e-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d7c6e-428">视图</span><span class="sxs-lookup"><span data-stu-id="d7c6e-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="d7c6e-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="d7c6e-429">Tables and Views</span></span>  
  
|<span data-ttu-id="d7c6e-430">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-430">ColumnName</span></span>|<span data-ttu-id="d7c6e-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-433">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-433">String</span></span>|  
|<span data-ttu-id="d7c6e-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-434">TABLE_OWNER</span></span>|<span data-ttu-id="d7c6e-435">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-435">String</span></span>|  
|<span data-ttu-id="d7c6e-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-436">TABLE_NAME</span></span>|<span data-ttu-id="d7c6e-437">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-437">String</span></span>|  
|<span data-ttu-id="d7c6e-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-438">TABLE_TYPE</span></span>|<span data-ttu-id="d7c6e-439">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-439">String</span></span>|  
|<span data-ttu-id="d7c6e-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-440">REMARKS</span></span>|<span data-ttu-id="d7c6e-441">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d7c6e-442">Columns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-442">Columns</span></span>  
  
|<span data-ttu-id="d7c6e-443">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-443">ColumnName</span></span>|<span data-ttu-id="d7c6e-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-446">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-446">String</span></span>|  
|<span data-ttu-id="d7c6e-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-447">TABLE_OWNER</span></span>|<span data-ttu-id="d7c6e-448">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-448">String</span></span>|  
|<span data-ttu-id="d7c6e-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-449">TABLE_NAME</span></span>|<span data-ttu-id="d7c6e-450">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-450">String</span></span>|  
|<span data-ttu-id="d7c6e-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-451">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-452">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-452">String</span></span>|  
|<span data-ttu-id="d7c6e-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-453">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-454">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-454">Int16</span></span>|  
|<span data-ttu-id="d7c6e-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-455">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-456">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-456">String</span></span>|  
|<span data-ttu-id="d7c6e-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-457">PRECISION</span></span>|<span data-ttu-id="d7c6e-458">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-458">Int32</span></span>|  
|<span data-ttu-id="d7c6e-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-459">LENGTH</span></span>|<span data-ttu-id="d7c6e-460">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-460">Int32</span></span>|  
|<span data-ttu-id="d7c6e-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-461">SCALE</span></span>|<span data-ttu-id="d7c6e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-462">Int16</span></span>|  
|<span data-ttu-id="d7c6e-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-463">RADIX</span></span>|<span data-ttu-id="d7c6e-464">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-464">Int16</span></span>|  
|<span data-ttu-id="d7c6e-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-465">NULLABLE</span></span>|<span data-ttu-id="d7c6e-466">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-466">Int16</span></span>|  
|<span data-ttu-id="d7c6e-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-467">REMARKS</span></span>|<span data-ttu-id="d7c6e-468">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-468">String</span></span>|  
|<span data-ttu-id="d7c6e-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-470">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d7c6e-471">过程</span><span class="sxs-lookup"><span data-stu-id="d7c6e-471">Procedures</span></span>  
  
|<span data-ttu-id="d7c6e-472">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-472">ColumnName</span></span>|<span data-ttu-id="d7c6e-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-475">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-475">String</span></span>|  
|<span data-ttu-id="d7c6e-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d7c6e-477">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-477">String</span></span>|  
|<span data-ttu-id="d7c6e-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-479">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-479">String</span></span>|  
|<span data-ttu-id="d7c6e-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d7c6e-481">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-481">Int16</span></span>|  
|<span data-ttu-id="d7c6e-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d7c6e-483">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-483">Int16</span></span>|  
|<span data-ttu-id="d7c6e-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d7c6e-485">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-485">Int16</span></span>|  
|<span data-ttu-id="d7c6e-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-486">REMARKS</span></span>|<span data-ttu-id="d7c6e-487">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-487">String</span></span>|  
|<span data-ttu-id="d7c6e-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d7c6e-489">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d7c6e-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d7c6e-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d7c6e-491">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-491">ColumnName</span></span>|<span data-ttu-id="d7c6e-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d7c6e-494">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-494">String</span></span>|  
|<span data-ttu-id="d7c6e-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7c6e-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d7c6e-496">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-496">String</span></span>|  
|<span data-ttu-id="d7c6e-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-498">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-498">String</span></span>|  
|<span data-ttu-id="d7c6e-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-499">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-500">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-500">String</span></span>|  
|<span data-ttu-id="d7c6e-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-501">COLUMN_TYPE</span></span>|<span data-ttu-id="d7c6e-502">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-502">Int16</span></span>|  
|<span data-ttu-id="d7c6e-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-503">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-504">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-504">Int16</span></span>|  
|<span data-ttu-id="d7c6e-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-505">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-506">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-506">String</span></span>|  
|<span data-ttu-id="d7c6e-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-507">PRECISION</span></span>|<span data-ttu-id="d7c6e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-508">Int32</span></span>|  
|<span data-ttu-id="d7c6e-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-509">LENGTH</span></span>|<span data-ttu-id="d7c6e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-510">Int32</span></span>|  
|<span data-ttu-id="d7c6e-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-511">SCALE</span></span>|<span data-ttu-id="d7c6e-512">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-512">Int16</span></span>|  
|<span data-ttu-id="d7c6e-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-513">RADIX</span></span>|<span data-ttu-id="d7c6e-514">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-514">Int16</span></span>|  
|<span data-ttu-id="d7c6e-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-515">NULLABLE</span></span>|<span data-ttu-id="d7c6e-516">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-516">Int16</span></span>|  
|<span data-ttu-id="d7c6e-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-517">REMARKS</span></span>|<span data-ttu-id="d7c6e-518">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-518">String</span></span>|  
|<span data-ttu-id="d7c6e-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d7c6e-519">OVERLOAD</span></span>|<span data-ttu-id="d7c6e-520">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-520">Int32</span></span>|  
|<span data-ttu-id="d7c6e-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-522">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d7c6e-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d7c6e-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d7c6e-524">列名</span><span class="sxs-lookup"><span data-stu-id="d7c6e-524">ColumnName</span></span>|<span data-ttu-id="d7c6e-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7c6e-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d7c6e-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d7c6e-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="d7c6e-527">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-527">String</span></span>|  
|<span data-ttu-id="d7c6e-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d7c6e-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d7c6e-529">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-529">String</span></span>|  
|<span data-ttu-id="d7c6e-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="d7c6e-531">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-531">String</span></span>|  
|<span data-ttu-id="d7c6e-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-532">COLUMN_NAME</span></span>|<span data-ttu-id="d7c6e-533">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-533">String</span></span>|  
|<span data-ttu-id="d7c6e-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-534">COLUMN_TYPE</span></span>|<span data-ttu-id="d7c6e-535">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-535">Int16</span></span>|  
|<span data-ttu-id="d7c6e-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-536">DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-537">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-537">Int16</span></span>|  
|<span data-ttu-id="d7c6e-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d7c6e-538">TYPE_NAME</span></span>|<span data-ttu-id="d7c6e-539">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-539">String</span></span>|  
|<span data-ttu-id="d7c6e-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-540">COLUMN_SIZE</span></span>|<span data-ttu-id="d7c6e-541">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-541">Int32</span></span>|  
|<span data-ttu-id="d7c6e-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="d7c6e-543">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-543">Int32</span></span>|  
|<span data-ttu-id="d7c6e-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d7c6e-545">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-545">Int16</span></span>|  
|<span data-ttu-id="d7c6e-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d7c6e-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d7c6e-547">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-547">Int16</span></span>|  
|<span data-ttu-id="d7c6e-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-548">NULLABLE</span></span>|<span data-ttu-id="d7c6e-549">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-549">Int16</span></span>|  
|<span data-ttu-id="d7c6e-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d7c6e-550">REMARKS</span></span>|<span data-ttu-id="d7c6e-551">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-551">String</span></span>|  
|<span data-ttu-id="d7c6e-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d7c6e-552">COLUMN_DEF</span></span>|<span data-ttu-id="d7c6e-553">String</span><span class="sxs-lookup"><span data-stu-id="d7c6e-553">String</span></span>|  
|<span data-ttu-id="d7c6e-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d7c6e-555">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-555">Int16</span></span>|  
|<span data-ttu-id="d7c6e-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d7c6e-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d7c6e-557">Int16</span><span class="sxs-lookup"><span data-stu-id="d7c6e-557">Int16</span></span>|  
|<span data-ttu-id="d7c6e-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d7c6e-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d7c6e-559">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-559">Int32</span></span>|  
|<span data-ttu-id="d7c6e-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d7c6e-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="d7c6e-561">Int32</span><span class="sxs-lookup"><span data-stu-id="d7c6e-561">Int32</span></span>|  
|<span data-ttu-id="d7c6e-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d7c6e-562">IS_NULLABLE</span></span>|<span data-ttu-id="d7c6e-563">字符串</span><span class="sxs-lookup"><span data-stu-id="d7c6e-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7c6e-564">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7c6e-564">See Also</span></span>  
 [<span data-ttu-id="d7c6e-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d7c6e-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
