---
title: 如何：将现有实体添加到 DataServiceContext（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 7c8355ea9e9823e7cab6f43c0f3f901948d1d539
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569383"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>如何：将现有实体添加到 DataServiceContext（WCF 数据服务）
当某个实体已存在于数据服务中时，WCF 数据服务的客户端库可将表示该实体的对象直接附加到 <xref:System.Data.Services.Client.DataServiceContext>，而无需首先执行查询。 有关详细信息，请参阅[更新数据服务](updating-the-data-service-wcf-data-services.md)。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 此服务和客户端数据类是在完成[WCF 数据服务快速入门](quickstart-wcf-data-services.md)时创建的。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建一个现有 `Customer` 对象，该对象包含将保存到数据服务的更改。 该对象附加到上下文中，并调用 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> 方法将附加的对象标记为 <xref:System.Data.Services.Client.EntityStates.Modified>，然后再调用 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 方法。  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>另请参阅

- [WCF Data Services 客户端库](wcf-data-services-client-library.md)
