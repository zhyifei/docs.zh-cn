---
title: 如何：投影查询结果（WCF 数据服务）
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
ms.openlocfilehash: c1eb2618e14f0e02aa5e1a2e91aa93fe0831c7c7
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932972"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>如何：投影查询结果（WCF 数据服务）
投影提供减少查询返回的数据量的机制，方法是指定在响应中仅返回某个实体的某些属性。 可以执行的结果的投影[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]查询通过使用`$select`查询选项或使用[选择](~/docs/csharp/language-reference/keywords/select-clause.md)子句 ([选择](~/docs/visual-basic/language-reference/queries/select-clause.md)在 Visual Basic 中) 中的 LINQ 查询。 有关详细信息，请参阅[查询数据服务](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 完成后，将创建此服务和客户端数据类[WCF Data Services 快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示一个 LINQ 查询，该查询将 Customers 实体投影到新的 CustomerAddress 类型，该类型仅包含特定地址属性以及标识属性。 此 `CustomerAddress` 类是在客户端上定义的并且具有客户端库可将它识别为实体类型的特性。  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>示例  
 下面的示例演示一个 LINQ 查询，该查询将返回的 Customers 实体投影到新的 CustomerAddressNonEntity 类型，该类型仅包含特定地址属性，不包含标识属性。 此 `CustomerAddressNonEntity` 类是在客户端上定义的，但不具有作为实体类型的特性。  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>示例  
 下面的示例演示的定义`CustomerAddress`和`CustomerAddressNonEntity`在上一示例中使用的类型。  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]
