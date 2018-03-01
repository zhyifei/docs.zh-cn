---
title: "基本编程生命周期"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f5c45cad0b1e4ae1aa6b1963e9acdab47cd9203
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="basic-programming-lifecycle"></a>基本编程生命周期
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 可让应用程序通报它们是在同一台计算机上、分布在 Internet 上还是在不同的应用程序平台上。 本主题概述了生成 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序所需的任务。 有关工作示例应用程序，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)。  
  
## <a name="the-basic-tasks"></a>基本任务  
 要执行的基本任务依次为：  
  
1.  定义服务协定。 服务协定指定服务的签名、服务交换的数据和其他协定要求的数据。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][设计服务协定](../../../docs/framework/wcf/designing-service-contracts.md)。  
  
2.  实现协定。 若要实现服务协定，请创建实现协定的类并指定运行时应具有的自定义行为。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][实现服务协定](../../../docs/framework/wcf/implementing-service-contracts.md)。  
  
3.  通过指定终结点和其他行为信息来配置服务。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][配置服务](../../../docs/framework/wcf/configuring-services.md)。  
  
4.  承载服务。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][托管服务](../../../docs/framework/wcf/hosting-services.md)。  
  
5.  生成客户端应用程序。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][生成客户端](../../../docs/framework/wcf/building-clients.md)。  
  
 尽管本节中的主题遵循此顺序，但是一些方案并不会从头开始。 例如，如果想要为预先存在的服务生成客户端，则从步骤 5 开始。 或者，如果您是在生成其他人要使用的服务，则可以跳过步骤 5。  
  
 一旦你熟悉开发服务协定，您还可以阅读[扩展性介绍](../../../docs/framework/wcf/introduction-to-extensibility.md)。 如果存在与您的服务的问题，请检查[WCF 疑难解答快速入门](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)以查看是否其他具有相同或类似问题。  
  
## <a name="see-also"></a>请参阅  
 [实现服务协定](../../../docs/framework/wcf/implementing-service-contracts.md)
