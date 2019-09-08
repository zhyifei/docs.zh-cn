---
title: 如何：将现有实体附加到 DataServiceContext （WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 160f0afc2e1baf033557b7114a51145a5c983e29
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791184"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>如何：将现有实体附加到 DataServiceContext （WCF 数据服务）
如果某个实体已存在于数据服务中，则[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]客户端库允许你将表示该实体的对象直接附加<xref:System.Data.Services.Client.DataServiceContext>到中，而无需首先执行查询。 有关详细信息，请参阅[更新数据服务](updating-the-data-service-wcf-data-services.md)。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 此服务和客户端数据类是在完成[WCF 数据服务快速入门](quickstart-wcf-data-services.md)时创建的。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建一个现有 `Customer` 对象，该对象包含将保存到数据服务的更改。 该对象附加到上下文中，并调用 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> 方法将附加的对象标记为 <xref:System.Data.Services.Client.EntityStates.Modified>，然后再调用 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 方法。  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>请参阅

- [WCF Data Services 客户端库](wcf-data-services-client-library.md)
