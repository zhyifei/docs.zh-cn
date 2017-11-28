---
title: "SQL XML 列值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c974749ee84bf64d1912ed71ea0817227b1ea514
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="e1426-102">SQL XML 列值</span><span class="sxs-lookup"><span data-stu-id="e1426-102">SQL XML Column Values</span></span>
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="e1426-103"> 支持 `xml` 数据类型，开发人员可以使用 <xref:System.Data.SqlClient.SqlCommand> 类的标准行为检索包括此类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="e1426-103"> supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="e1426-104">`xml` 列可以像任意列一样进行检索（例如检索到 <xref:System.Data.SqlClient.SqlDataReader> 中），但是如果要以 XML 的形式使用列内容，必须使用 <xref:System.Xml.XmlReader>。</span><span class="sxs-lookup"><span data-stu-id="e1426-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1426-105">示例</span><span class="sxs-lookup"><span data-stu-id="e1426-105">Example</span></span>  
 <span data-ttu-id="e1426-106">以下控制台应用程序选择两个行，每个包含`xml`列中，从**Sales.Store**表中**AdventureWorks**数据库到<xref:System.Data.SqlClient.SqlDataReader>实例。</span><span class="sxs-lookup"><span data-stu-id="e1426-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="e1426-107">对于每一行，`xml` 列的值使用 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> 的 <xref:System.Data.SqlClient.SqlDataReader> 方法读取。</span><span class="sxs-lookup"><span data-stu-id="e1426-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="e1426-108">该值存储在 <xref:System.Xml.XmlReader> 中。</span><span class="sxs-lookup"><span data-stu-id="e1426-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="e1426-109">注意，如果要将内容设置为 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> 变量，必须使用 <xref:System.Data.IDataRecord.GetValue%2A> 方法，而不要使用 <xref:System.Data.SqlTypes.SqlXml> 方法；<xref:System.Data.IDataRecord.GetValue%2A> 以字符串的形式返回 `xml` 列的值。</span><span class="sxs-lookup"><span data-stu-id="e1426-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1426-110">**AdventureWorks**示例数据库未安装默认情况下，当你安装时[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e1426-110">The **AdventureWorks** sample database is not installed by default when you install [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e1426-111">可以通过运行 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 安装程序来安装它。</span><span class="sxs-lookup"><span data-stu-id="e1426-111">You can install it by running [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e1426-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1426-112">See Also</span></span>  
 <xref:System.Data.SqlTypes.SqlXml>  
 [<span data-ttu-id="e1426-113">SQL Server 中的 XML 数据</span><span class="sxs-lookup"><span data-stu-id="e1426-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [<span data-ttu-id="e1426-114">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e1426-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
