---
title: "如何：使用两个 Windows 窗体 DataGridView 控件创建一个主/从窗体 | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView 控件 [Windows 窗体], 主/详细信息窗体"
  - "主-详细信息列表, 创建"
  - "父-子表, 在 Windows 窗体上显示"
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 如何：使用两个 Windows 窗体 DataGridView 控件创建一个主/从窗体
以下代码示例使用绑定到两个 <xref:System.Windows.Forms.BindingSource> 组件的两个 <xref:System.Windows.Forms.DataGridView> 控件创建主窗体\/详细窗体。  数据源是一个 <xref:System.Data.DataSet>，其中包含来自 Northwind SQL Server 示例数据库的 `Customers` 和 `Orders` 表以及通过 `CustomerID` 列关联这两张表的 <xref:System.Data.DataRelation>。  
  
 一个 <xref:System.Windows.Forms.BindingSource> 被绑定到数据集中的父 `Customers` 表。  此数据在主 <xref:System.Windows.Forms.DataGridView> 控件中显示。  其他 <xref:System.Windows.Forms.BindingSource> 被绑定到第一个数据连接器。  第二个 <xref:System.Windows.Forms.BindingSource> 的 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 属性被设置为 <xref:System.Data.DataRelation> 名称。  这将导致相关联的详细 <xref:System.Windows.Forms.DataGridView> 控件显示子 `Orders` 表中与主 <xref:System.Windows.Forms.DataGridView> 控件中当前行相对应的行。  
  
 有关此代码示例的完整说明，请参阅[演练：使用两个 Windows 窗体 DataGridView 控件创建一个主\/从窗体](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagrids.md)。  
  
## 示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## 编译代码  
 此示例需要：  
  
-   引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。  
  
 有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 命令行生成此示例的信息，请参阅[从命令行生成](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 或[在命令行上使用 csc.exe 生成](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。  还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。  另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))  
  
## .NET Framework 安全性  
 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。  若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。  有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。  
  
## 请参阅  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [演练：使用两个 Windows 窗体 DataGridView 控件创建一个主\/从窗体](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagrids.md)   
 [在 Windows 窗体 DataGridView 控件中显示数据](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)