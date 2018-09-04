---
title: SqlTypes 和数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: fe00e669449d40320a2038697976423db83ade5b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511542"
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="80a40-102">SqlTypes 和数据集</span><span class="sxs-lookup"><span data-stu-id="80a40-102">SqlTypes and the DataSet</span></span>
<span data-ttu-id="80a40-103">ADO.NET 2.0 通过 `DataSet` 命名空间引入了对 <xref:System.Data.SqlTypes> 的增强类型支持。</span><span class="sxs-lookup"><span data-stu-id="80a40-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="80a40-104"><xref:System.Data.SqlTypes> 中的类型旨在提供具有与 SQL Server 数据库中的数据类型相同的语义和精度的数据类型。</span><span class="sxs-lookup"><span data-stu-id="80a40-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="80a40-105"><xref:System.Data.SqlTypes> 中的每个数据类型在 SQL Server 中都具有等效的数据类型，并具有相同的基础数据表示形式。</span><span class="sxs-lookup"><span data-stu-id="80a40-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="80a40-106">在使用 SQL Server 数据类型时，在 <xref:System.Data.SqlTypes> 中直接使用 <xref:System.Data.DataSet> 具有多个优点。</span><span class="sxs-lookup"><span data-stu-id="80a40-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="80a40-107"><xref:System.Data.SqlTypes> 支持与 SQL Server 本机数据类型相同的语义。</span><span class="sxs-lookup"><span data-stu-id="80a40-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="80a40-108">通过在 <xref:System.Data.SqlTypes> 的定义中指定 <xref:System.Data.DataColumn> 之一，可避免在将 decimal 或 numeric 数据类型转换为公共语言运行库 (CLR) 数据类型之一时可能造成的精度损失。</span><span class="sxs-lookup"><span data-stu-id="80a40-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a40-109">示例</span><span class="sxs-lookup"><span data-stu-id="80a40-109">Example</span></span>  
 <span data-ttu-id="80a40-110">以下示例创建 <xref:System.Data.DataTable> 对象，并使用 <xref:System.Data.DataColumn> 而非 CLR 类型来显式定义 <xref:System.Data.SqlTypes> 数据类型。</span><span class="sxs-lookup"><span data-stu-id="80a40-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="80a40-111">代码将用 SQL Server 中的 AdventureWorks 数据库的 Sales.SalesOrderDetail 表中的数据填充 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="80a40-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="80a40-112">控制台窗口中显示的输出显示每个列的数据类型以及从 SQL Server 检索的值。</span><span class="sxs-lookup"><span data-stu-id="80a40-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="80a40-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="80a40-113">See Also</span></span>  
 [<span data-ttu-id="80a40-114">SQL Server 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="80a40-114">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="80a40-115">配置参数和参数数据类型</span><span class="sxs-lookup"><span data-stu-id="80a40-115">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="80a40-116">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="80a40-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
