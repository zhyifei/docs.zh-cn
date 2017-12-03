---
title: "如何：将现有实体添加到 DataServiceContext（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bed0eaed0daea30d7546dd0728091d93aa3bab32
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>如何：将现有实体添加到 DataServiceContext（WCF 数据服务）
当在数据服务中，已存在实体[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]客户端库允许你将直接表示实体对象附加<xref:System.Data.Services.Client.DataServiceContext>而不必首先执行查询。 有关详细信息，请参阅[更新数据服务](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 在完成时创建此服务和客户端数据类[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建一个现有 `Customer` 对象，该对象包含将保存到数据服务的更改。 该对象附加到上下文中，并调用 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> 方法将附加的对象标记为 <xref:System.Data.Services.Client.EntityStates.Modified>，然后再调用 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 方法。  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>另请参阅  
 [WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
