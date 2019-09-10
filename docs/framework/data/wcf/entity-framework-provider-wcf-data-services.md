---
title: 实体框架提供程序（WCF 数据服务）
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 5a40eeafafef56902a9ae5037e6bc946b598f752
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854079"
---
# <a name="entity-framework-provider-wcf-data-services"></a>实体框架提供程序（WCF 数据服务）
与 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 类似，ADO.NET 实体框架也基于实体数据模型（一种实体关系模型）。 实体框架将操作转换为其对实体数据模型（称为*概念模型*）的实现，以对数据源执行等效操作。 这使实体框架成为基于关系数据的数据服务的理想提供程序，任何具有支持实体框架的数据提供程序的数据库都可用于 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]。 有关当前支持实体框架的数据源的列表，请参阅实体框架的[第三方提供程序](https://go.microsoft.com/fwlink/?LinkId=143699)。  
  
 在概念模型中，实体容器是服务的根。 必须先在实体框架中定义一个概念模型，数据服务才能公开数据。 有关详细信息，请参阅[如何：使用 ADO.NET 实体框架数据源](create-a-data-service-using-an-adonet-ef-data-wcf.md)创建数据服务。  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]通过使您能够为实体定义并发标记，支持开放式并发模型。 这样一个包含一个或多个实体属性的并发标记由数据服务用来确定，正在请求、更新或删除的数据中是否发生了更改。 如果从请求的 eTag 中获取的标记值与实体的当前值不相同，则数据服务将引发异常。 若要指示某个属性是并发标记的一部分，必须在由实体框架提供程序`ConcurrencyMode="Fixed"`定义的数据模型中应用该属性。 并发标记不能包含键属性或导航属性。 有关详细信息，请参阅[更新数据服务](updating-the-data-service-wcf-data-services.md)。  
  
 若要详细了解实体框架，请参阅[实体框架概述](../adonet/ef/overview.md)。  
  
## <a name="see-also"></a>请参阅

- [数据服务提供程序](data-services-providers-wcf-data-services.md)
- [反射提供程序](reflection-provider-wcf-data-services.md)
- [实体数据模型](../adonet/entity-data-model.md)
