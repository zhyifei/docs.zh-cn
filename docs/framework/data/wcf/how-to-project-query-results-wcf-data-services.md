---
title: 如何：项目查询结果（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
ms.openlocfilehash: 758bb01764fcfe195d4f940705316e7579be95ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780006"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>如何：项目查询结果（WCF 数据服务）
投影提供减少查询返回的数据量的机制，方法是指定在响应中仅返回某个实体的某些属性。 您可以通过`$select`使用查询选项或在 LINQ [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]查询中使用[select](../../../csharp/language-reference/keywords/select-clause.md)子句（在 Visual Basic 中[选择](../../../visual-basic/language-reference/queries/select-clause.md)）对查询结果执行投影。 有关详细信息，请参阅[查询数据服务](querying-the-data-service-wcf-data-services.md)。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 此服务和客户端数据类是在完成[WCF 数据服务快速入门](quickstart-wcf-data-services.md)时创建的。  
  
## <a name="example"></a>示例  
 下面的示例演示一个 LINQ 查询，该查询将 Customers 实体投影到新的 CustomerAddress 类型，该类型仅包含特定地址属性以及标识属性。 此 `CustomerAddress` 类是在客户端上定义的并且具有客户端库可将它识别为实体类型的特性。  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>示例  
 下面的示例演示一个 LINQ 查询，该查询将返回的 Customers 实体投影到新的 CustomerAddressNonEntity 类型，该类型仅包含特定地址属性，不包含标识属性。 此 `CustomerAddressNonEntity` 类是在客户端上定义的，但不具有作为实体类型的特性。  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>示例  
 下面的示例演示前面的示例中`CustomerAddress`使用`CustomerAddressNonEntity`的和类型的定义。  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customeraddress.vb#customeraddressdefinition)]
