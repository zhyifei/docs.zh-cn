---
title: SQL XML 列值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 03b09d3a53c725bb0e84ba6b5d98944267bc564c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780803"
---
# <a name="sql-xml-column-values"></a>SQL XML 列值
SQL Server 支持`xml`数据类型，开发人员可以使用<xref:System.Data.SqlClient.SqlCommand>类的标准行为检索包括此类型的结果集。 `xml` 列可以像任意列一样进行检索（例如检索到 <xref:System.Data.SqlClient.SqlDataReader> 中），但是如果要以 XML 的形式使用列内容，必须使用 <xref:System.Xml.XmlReader>。  
  
## <a name="example"></a>示例  
 下面的控制台应用程序选择两个行，每`xml`个行包含一个列，从**AdventureWorks**数据库中的**存储**表到<xref:System.Data.SqlClient.SqlDataReader>一个实例。 对于每一行，`xml` 列的值使用 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> 的 <xref:System.Data.SqlClient.SqlDataReader> 方法读取。 该值存储在 <xref:System.Xml.XmlReader> 中。 注意，如果要将内容设置为 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> 变量，必须使用 <xref:System.Data.IDataRecord.GetValue%2A> 方法，而不要使用 <xref:System.Data.SqlTypes.SqlXml> 方法；<xref:System.Data.IDataRecord.GetValue%2A> 以字符串的形式返回 `xml` 列的值。  
  
> [!NOTE]
> 默认情况下，在安装 SQL Server 时，不会安装**AdventureWorks**示例数据库。 可以通过运行 SQL Server 安装程序来安装。  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Data.SqlTypes.SqlXml>
- [SQL Server 中的 XML 数据](xml-data-in-sql-server.md)
- [ADO.NET 概述](../ado-net-overview.md)
