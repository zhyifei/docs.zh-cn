---
title: Oracle REF CURSOR
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 0a98bfd401aaabfb754c422cc753bc5092f9f76c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64633343"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="9af02-102">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="9af02-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="9af02-103">Oracle.NET Framework 数据提供程序支持 Oracle **REF CURSOR**数据类型。</span><span class="sxs-lookup"><span data-stu-id="9af02-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="9af02-104">在通过数据提供程序使用 Oracle REF CURSOR 时，应考虑下列行为。</span><span class="sxs-lookup"><span data-stu-id="9af02-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9af02-105">有些行为与 Microsoft Oracle OLE DB 提供程序 (MSDAORA) 的行为不同。</span><span class="sxs-lookup"><span data-stu-id="9af02-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
- <span data-ttu-id="9af02-106">出于性能原因，Oracle 数据提供程序不会自动绑定**REF CURSOR**数据类型，因为 MSDAORA 会这样做，除非显式指定。</span><span class="sxs-lookup"><span data-stu-id="9af02-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
- <span data-ttu-id="9af02-107">数据提供程序不支持任何 ODBC 转义序列，包括用于指定 REF CURSOR 参数的 {resultset} 转义。</span><span class="sxs-lookup"><span data-stu-id="9af02-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="9af02-108">若要执行返回 REF Cursor 的存储的过程，必须定义中的参数<xref:System.Data.OracleClient.OracleParameterCollection>与<xref:System.Data.OracleClient.OracleType>的**光标**和一个<xref:System.Data.OracleClient.OracleParameter.Direction%2A>的**输出**。</span><span class="sxs-lookup"><span data-stu-id="9af02-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="9af02-109">数据提供程序只支持作为输出参数绑定 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="9af02-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="9af02-110">提供程序不支持 REF CURSOR 作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="9af02-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
- <span data-ttu-id="9af02-111">不支持从参数值获取 <xref:System.Data.OracleClient.OracleDataReader>。</span><span class="sxs-lookup"><span data-stu-id="9af02-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="9af02-112">在执行命令后，值属于 <xref:System.DBNull> 类型。</span><span class="sxs-lookup"><span data-stu-id="9af02-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
- <span data-ttu-id="9af02-113">唯一**CommandBehavior**适用于 REF Cursor 的枚举值 (例如，当调用<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) 是**CloseConnection**; 忽略所有其他。</span><span class="sxs-lookup"><span data-stu-id="9af02-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
- <span data-ttu-id="9af02-114">中的 REF Cursor 的顺序**OracleDataReader**取决于中的参数顺序**OracleParameterCollection**。</span><span class="sxs-lookup"><span data-stu-id="9af02-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="9af02-115"><xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> 属性被忽略。</span><span class="sxs-lookup"><span data-stu-id="9af02-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
- <span data-ttu-id="9af02-116">PL/SQL**表**不支持数据类型。</span><span class="sxs-lookup"><span data-stu-id="9af02-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="9af02-117">但是，REF CURSOR 的效率更高。</span><span class="sxs-lookup"><span data-stu-id="9af02-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="9af02-118">如果必须使用**表**数据类型，使用 MSDAORA OLE DB.NET 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="9af02-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9af02-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="9af02-119">In This Section</span></span>  
 [<span data-ttu-id="9af02-120">REF CURSOR 示例</span><span class="sxs-lookup"><span data-stu-id="9af02-120">REF CURSOR Examples</span></span>](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 <span data-ttu-id="9af02-121">包含三个示例，演示如何使用 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="9af02-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="9af02-122">OracleDataReader 中的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="9af02-122">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="9af02-123">演示如何执行一个 PL/SQL 存储过程，返回 REF CURSOR 参数，并读取的值作为**OracleDataReader**。</span><span class="sxs-lookup"><span data-stu-id="9af02-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="9af02-124">使用 OracleDataReader 从多个 REF CURSOR 中检索数据</span><span class="sxs-lookup"><span data-stu-id="9af02-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="9af02-125">演示如何执行一个 PL/SQL 存储过程，返回两个 REF CURSOR 参数，并读取使用的值**OracleDataReader**。</span><span class="sxs-lookup"><span data-stu-id="9af02-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="9af02-126">使用一个或多个 REF CURSOR 填充数据集</span><span class="sxs-lookup"><span data-stu-id="9af02-126">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="9af02-127">演示如何执行一个 PL/SQL 存储过程，返回两个 REF CURSOR 参数，并使用返回的行填充 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="9af02-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af02-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9af02-128">See also</span></span>

- [<span data-ttu-id="9af02-129">Oracle 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9af02-129">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="9af02-130">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="9af02-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
